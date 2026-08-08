---

title: "États commerciaux et cycle d'achat"
description: "Automate d'états commerciaux des références, principe selon lequel une commande n'est pas un verrouillage, et coût du changement après achat."
version: "1.0"
--------------

# États commerciaux et cycle d'achat

## 1. Objet

Ce document définit les états commerciaux qu'une référence traverse pendant la campagne d'achat, ainsi que les règles régissant le remplacement d'un achat déjà effectué par une meilleure offre survenue ultérieurement.

Ces états sont distincts des états de conception utilisés par le moteur de composition. Ils qualifient la situation d'achat d'une référence sur le marché, pas sa pertinence technique.

Toutes les règles générales du guide restent applicables.

---

# 2. Automate d'états commerciaux

Chaque référence candidate peut traverser les états suivants.

```text
SURVEILLÉE
   ↓
CANDIDATE
   ↓
ACHETABLE
   ↓
ACHAT RECOMMANDÉ
   ↓
ACHAT URGENT
   ↓
COMMANDÉE
   ↓
SÉCURISÉE
   ↓
DÉFINITIVE
```

## 2.1 Définition des états

**SURVEILLÉE** — la référence est suivie par le moteur (prix, stock) mais n'est pas encore un candidat validé.

**CANDIDATE** — la référence a passé les critères éliminatoires du moteur de composition et appartient à au moins une configuration candidate.

**ACHETABLE** — la référence est disponible à l'achat, sans considération de qualité de prix.

**ACHAT RECOMMANDÉ** — la `Valeur_attente` (`24-Regret-et-valeur-attente.md`) est négative ou proche de zéro : l'achat devient rationnel.

**ACHAT URGENT** — la priorité d'achat (`25-Dependances-et-priorite-achat.md`) est élevée et le risque de disponibilité est élevé ou critique : un délai supplémentaire menace directement l'accès à la référence.

**COMMANDÉE** — l'achat a été passé chez un vendeur.

**SÉCURISÉE** — le délai de rétractation ou d'annulation applicable est écoulé, ou la commande a été expédiée sans possibilité raisonnable de changement (voir section 4).

**DÉFINITIVE** — la référence est intégrée à la configuration finale, tous les composants critiques étant eux-mêmes sécurisés (`27-Budget-immobilise-et-risque-configuration.md`).

## 2.2 États d'exception

En complément de la chaîne principale, une référence peut basculer vers :

* **RUPTURE** — la référence n'est plus disponible chez aucun vendeur suivi ;
* **ABANDONNÉE** — la référence est retirée de la liste des candidats (remplacée avant tout achat) ;
* **REMPLACÉE** — une commande existante est annulée au profit d'une meilleure offre (voir section 4) ;
* **ANNULÉE** — une commande est annulée sans remplacement (erreur, changement de besoin).

---

# 3. Commandé ne signifie pas verrouillé

C'est un principe important : l'état `COMMANDÉE` n'est pas un état final. La référence reste surveillée tant qu'elle n'est pas `SÉCURISÉE`.

## 3.1 Exemple

```text
RTX 5080 achetée un lundi
ACHAT RECOMMANDÉ → COMMANDÉE

Elle reste surveillée.

Une meilleure offre B est détectée le vendredi
   ↓
comparaison du gain avec le coût de changement (C_switch, section 5)
   ↓
si le changement est rentable
   ↓
B est commandée
   ↓
A est annulée ou retournée
   ↓
B devient SÉCURISÉE
```

## 3.2 Condition d'application

Ce mécanisme ne s'applique que si les conditions contractuelles du premier achat permettent raisonnablement l'annulation ou la rétractation. Le moteur doit donc connaître, pour chaque commande :

* le vendeur ;
* la date d'achat ;
* le délai d'annulation ou de rétractation applicable ;
* les éventuels frais associés à une annulation ou un retour ;
* la date limite pour agir ;
* le statut d'expédition.

## 3.3 Garde-fou

Ce mécanisme sert de filet de sécurité, particulièrement pour les achats coûteux. Il ne doit pas être utilisé abusivement : chaque changement potentiel est soumis au calcul du coût de changement (section 5), qui empêche les allers-retours non rentables.

---

# 4. Passage à l'état SÉCURISÉE

Une référence passe de `COMMANDÉE` à `SÉCURISÉE` lorsque l'une des conditions suivantes est remplie :

* le délai d'annulation ou de rétractation applicable est écoulé sans qu'aucune meilleure offre rentable n'ait été détectée ;
* la commande a été expédiée dans des conditions rendant un changement déraisonnable (frais ou délai disproportionnés) ;
* le moteur a explicitement évalué et rejeté toutes les alternatives détectées avant l'échéance du délai.

Une référence `SÉCURISÉE` peut redevenir surveillée si une opportunité exceptionnelle apparaît et que les conditions de retour le permettent encore, mais ce cas doit rester rare et être signalé comme tel dans le rapport.

---

# 5. Coût du changement après achat

Une nouvelle offre moins chère qu'un achat déjà réalisé ne signifie pas automatiquement qu'il faille changer.

## 5.1 Exemple

GPU acheté : 1 200 €. Nouvelle offre : 1 180 €. Gain apparent : 20 €.

Mais changer implique :

* d'immobiliser 1 180 € supplémentaires en attendant le remboursement ;
* de préparer un retour ;
* d'attendre un remboursement ;
* de supporter éventuellement des frais ;
* de prendre un risque logistique.

Dans cet exemple, le moteur doit répondre : conserver l'achat initial.

## 5.2 Formule

```text
C_switch = coût financier + coût logistique + risque + temps nécessaire au changement
```

## 5.3 Règle de décision

```text
Changer uniquement si :
gain de la nouvelle offre > C_switch + marge minimale
```

La marge minimale évite les changements marginaux qui ne produisent qu'un gain théorique une fois les frictions prises en compte.

---

# 6. Traçabilité

Pour chaque référence, le rapport d'acquisition conserve :

* l'historique complet des états traversés, avec dates ;
* pour chaque commande : vendeur, date, délai applicable, frais, statut d'expédition ;
* chaque comparaison réalisée entre une commande existante et une meilleure offre détectée, avec le calcul de `C_switch` et la décision retenue ;
* le motif du passage à l'état `SÉCURISÉE` ou `DÉFINITIVE`.

---

# 7. Principe final

Un achat n'est pas un engagement figé tant que les conditions commerciales permettent raisonnablement d'en changer. Le moteur doit exploiter cette flexibilité comme un filet de sécurité contre les regrets d'achat trop précoces, sans jamais en abuser : chaque remise en cause d'un achat déjà réalisé doit être justifiée par un gain net, une fois le coût du changement intégralement décompté.
