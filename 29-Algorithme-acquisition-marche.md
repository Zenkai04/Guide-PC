---

title: "Algorithme d'acquisition"
description: "Boucle complète du moteur d'exécution du marché, décision d'achat multicritère et garde-fous anti-FOMO et anti-perfectionnisme."
version: "1.0"
--------------

# Algorithme d'acquisition

## 1. Objet

Ce document assemble les mécanismes définis dans les documents `21` à `28` en une boucle unique et exécutable.

Il joue, pour le moteur d'acquisition, le rôle que joue `18-Algorithme-global.md` pour le moteur de composition.

Toutes les règles générales du guide restent applicables.

---

# 2. Position dans le pipeline global

```text
Moteur d'ingénierie (01-03)
        ↓
Moteur de composition (04-20)
        ↓
Configurations candidates + rapport de décision
        ↓
Moteur d'acquisition (21-29)
        ↓
Achats
```

Le moteur d'acquisition démarre avec les configurations candidates produites par le moteur de composition. Il ne les remet en cause techniquement que dans le cadre strict de la recomposition définie en `28-Configurations-secours-et-checkpoints.md`.

---

# 3. Boucle complète

```text
SCAN MARCHÉ
     ↓
Collecter prix + stocks + promotions
     ↓
Vérifier qualité des données
     ↓
Mettre à jour l'historique (22-Temporalite-des-prix.md)
     ↓
Détecter changements significatifs
     ↓
Réévaluer candidats
     ↓
Vérifier compatibilités (16-Compatibilites-et-interactions.md)
     ↓
Recalculer configurations (28-Configurations-secours-et-checkpoints.md)
     ↓
Calculer :
  - qualité de l'offre (22-Temporalite-des-prix.md)
  - disponibilité (23-Disponibilite-et-substituabilite.md)
  - substituabilité (23-Disponibilite-et-substituabilite.md)
  - coût de substitution (23-Disponibilite-et-substituabilite.md)
  - gain potentiel d'attente (24-Regret-et-valeur-attente.md)
  - criticité structurelle (25-Dependances-et-priorite-achat.md)
  - risque de configuration incomplète (27-Budget-immobilise-et-risque-configuration.md)
     ↓
Calcul du regret attendu (24-Regret-et-valeur-attente.md)
     ↓
┌──────────────────────────────┐
│ Décision                     │
├──────────────────────────────┤
│ ATTENDRE                     │
│ SURVEILLER PRIORITAIREMENT   │
│ ACHETER                      │
│ ACHETER IMMÉDIATEMENT        │
└──────────────────────────────┘
     ↓
Si achat
     ↓
COMMANDÉE (26-Etats-commerciaux-et-cycle-achat.md)
     ↓
continuer surveillance
     ↓
meilleure offre détectée ?
   ↙       ↘
 non       oui
  ↓          ↓
garder   calcul de C_switch (26-Etats-commerciaux-et-cycle-achat.md)
            ↓
       changement rentable ?
         ↙          ↘
       non          oui
        ↓            ↓
      garder       changer
         \          /
          ↓        ↓
            SÉCURISÉE
               ↓
Tous les composants critiques sont-ils sécurisés ?
        ↙                ↘
      non                oui
       ↓                  ↓
nouveau scan       configuration viable
                          ↓
                     VERROUILLAGE
```

---

# 4. Les quatre catégories de décision

## 4.1 ATTENDRE

`Valeur_attente ≥ 0` et aucun facteur de la section 5 ne l'emporte.

Aucune action requise. La référence reste `CANDIDATE` ou `ACHETABLE`.

## 4.2 SURVEILLER PRIORITAIREMENT

`Valeur_attente` proche de zéro, ou risque de disponibilité en augmentation sans être encore élevé.

La fréquence de scan de cette référence spécifique peut être augmentée sans déclencher d'achat.

## 4.3 ACHETER

`Valeur_attente < 0`, ou le risque de configuration incomplète (`R_incomplet`, `27-Budget-immobilise-et-risque-configuration.md`) devient significatif pour ce composant.

La référence passe à `ACHAT RECOMMANDÉ` puis, si le budget disponible le permet, à `COMMANDÉE`.

## 4.4 ACHETER IMMÉDIATEMENT

Le prix est en zone vert foncé (`22-Temporalite-des-prix.md`) **et** le risque de disponibilité est élevé ou critique **et** la substituabilité est faible.

La référence passe à `ACHAT URGENT` puis `COMMANDÉE` sans délai d'observation supplémentaire.

---

# 5. Décision multicritère finale

La décision d'achat n'est jamais réduite à une seule variable.

```text
Décision achat = f(prix, historique, disponibilité, substituabilité,
                    criticité, dépendances, risque de hausse,
                    gain potentiel, budget immobilisé,
                    état global de la configuration)
```

Chacun de ces termes est défini et calculé dans un document dédié :

| Terme | Document |
| ----- | -------- |
| Prix, historique | `22-Temporalite-des-prix.md` |
| Disponibilité, substituabilité | `23-Disponibilite-et-substituabilite.md` |
| Gain potentiel, risque de hausse, regret | `24-Regret-et-valeur-attente.md` |
| Criticité, dépendances | `25-Dependances-et-priorite-achat.md` |
| Budget immobilisé, état global de la configuration | `27-Budget-immobilise-et-risque-configuration.md` |

Aucun de ces termes ne peut, seul, déclencher une décision d'achat ou d'attente sans que les autres aient été évalués. C'est la conséquence directe de la fonction objectif définie en `21-Moteur-dacquisition.md` : maximiser la qualité et l'économie tout en minimisant les risques de rupture, de configuration incomplète et de regret.

---

# 6. Règle anti-FOMO

Un stock faible ne doit jamais, à lui seul, suffire à déclencher un achat.

Il faut au minimum l'une des combinaisons suivantes :

```text
offre acceptable + risque de disponibilité avéré
ou
offre excellente
ou
composant indispensable + substituabilité très faible + risque élevé
```

« Plus que 2 en stock ! » ne suffit jamais. Cette règle prolonge le garde-fou défini en `23-Disponibilite-et-substituabilite.md`, section 2.3 : un indice de rareté non corroboré ne doit jamais, seul, faire basculer une référence vers `ACHAT URGENT`.

---

# 7. Règle anti-perfectionnisme

À l'inverse, le moteur doit empêcher la recherche indéfinie du dernier pourcent d'économie au prix d'un risque de rupture croissant.

Cette règle est développée en détail en `24-Regret-et-valeur-attente.md`, section 5 (loi des rendements décroissants). Elle s'applique ici comme garde-fou symétrique de la règle anti-FOMO : l'une empêche d'acheter trop tôt sous la pression d'une fausse urgence, l'autre empêche d'attendre trop longtemps par excès de prudence.

---

# 8. Verrouillage

La configuration atteint l'état `VERROUILLAGE` lorsque tous les composants dont la criticité structurelle est significative (`25-Dependances-et-priorite-achat.md`) sont `SÉCURISÉS` ou `DÉFINITIFS` (`26-Etats-commerciaux-et-cycle-achat.md`).

Le verrouillage n'empêche pas la conservation de composants secondaires encore en `CANDIDATE` ou `ACHETABLE`, dès lors que leur absence ne remet pas en cause la viabilité de la configuration.

---

# 9. Traçabilité

Le rapport d'acquisition final, produit à l'issue du verrouillage, doit reprendre pour chaque composant :

* l'historique des états commerciaux traversés ;
* les valeurs de chacun des termes de la décision multicritère au moment de l'achat ;
* le motif exact ayant déclenché le passage à `ACHETER` ou `ACHETER IMMÉDIATEMENT` ;
* le regret attendu estimé au moment de la décision ;
* les éventuels changements de commande réalisés, avec leur justification.

Ce rapport complète, sans le remplacer, le rapport de décision produit par le moteur de composition (`19-Rapport-de-decision.md`).

---

# 10. Principe final

Le moteur d'acquisition ne cherche ni le prix le plus bas ni l'achat le plus rapide. Il cherche le point rationnel entre le regret d'avoir acheté trop tôt et le regret d'avoir attendu trop longtemps, composant par composant, réévalué en continu à mesure que le marché change, jusqu'à ce que l'ensemble de la configuration soit sécurisé dans des conditions de coût et de risque acceptables.
