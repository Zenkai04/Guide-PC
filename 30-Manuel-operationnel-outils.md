# Manuel d'utilisation des outils — Projet PC Black Friday 2026

Version : 1.0  
Statut : opérationnel / à améliorer après simulations d'octobre

---

# 1. Objet

Ce document définit comment utiliser les différents outils et agents du projet d'achat PC Black Friday 2026.

Le système repose sur plusieurs acteurs spécialisés.

Aucun outil ne doit devenir une autorité universelle.

Principe général :

```text
Guide-PC
   ↓
Claude
   ↓
Configurations
   ↓
ChatGPT
   ↓
Contrôle contradictoire
   ↓
Recherche marché
   ↓
Dealabs / Amazon / marchands
   ↓
Comparaison
   ↓
Mino / Shoptimate
   ↓
Validation finale
   ↓
Achat
```

Le rôle de chaque outil doit rester distinct.

---

# 2. Hiérarchie des sources

Ordre de confiance général :

```text
1. Décisions approuvées du projet
2. Guide-PC
3. Caractéristiques constructeur
4. Prix réellement affiché chez le marchand
5. Tests techniques fiables
6. Données de marché observées
7. Comparateurs
8. Communauté / Dealabs
9. Estimations
10. Rumeurs
```

Une source de faible confiance ne doit jamais remplacer silencieusement une donnée de niveau supérieur.

---

# 3. Guide-PC / bibliothèque du projet

## Rôle

Le dépôt `Guide-PC` constitue la base normative du projet.

Organisation :

```text
00–03 : besoin, entrées, processus, règles
04–20 : moteur de composition
21–29 : moteur d'acquisition
Compositions/ : configurations et retours critiques
```

## Utilisation

Le guide sert à :

- construire les configurations ;
- vérifier les règles ;
- maintenir la cohérence du système ;
- définir le budget ;
- évaluer les compromis ;
- gérer le marché ;
- décider acheter / attendre ;
- préparer les configurations de secours.

## Règle importante

Une version récente d'une configuration n'est pas automatiquement correcte.

Toujours distinguer :

```text
PROPOSITION
RETOUR CRITIQUE
DÉCISION APPROUVÉE
```

## Interdiction

Ne jamais utiliser le guide comme une simple liste de composants.

Il définit une méthode.

---

# 4. Claude

## 4.1 Rôle

Claude est le :

**MOTEUR DE COMPOSITION ET DE RECOMPOSITION**

Il doit principalement :

- construire les configurations ;
- vérifier les compatibilités ;
- dimensionner les composants ;
- calculer les compromis ;
- appliquer le moteur Guide-PC ;
- produire C1–C5 ;
- recalculer après changement structurel ;
- préparer les configurations de secours.

Claude n'est pas le contrôleur final.

---

## 4.2 Quand utiliser Claude

Utiliser Claude lorsqu'il faut :

### MODE NORMAL

- générer les configurations ;
- refaire une étude complète ;
- intégrer un changement durable du besoin ;
- recalculer les architectures.

### MODE URGENCE

Lorsqu'un événement modifie potentiellement l'architecture :

- GPU très fortement remisé ;
- GPU cible indisponible ;
- changement CPU ;
- changement de résolution ;
- écran central différent ;
- budget modifié ;
- incompatibilité découverte ;
- composant directeur différent.

---

## 4.3 Quand NE PAS utiliser Claude

Ne pas relancer Claude pour :

- 5 € de différence sur un SSD ;
- un coupon ;
- un changement de vendeur ;
- une petite variation de RAM équivalente ;
- une livraison différente ;
- une alternative déjà prévalidée.

Ces cas doivent être traités localement par ChatGPT.

---

## 4.4 Prompt Claude — génération normale

```text
MODE : NORMAL

Applique le corpus Guide-PC disponible dans le projet.

OBJECTIF :
Produire les configurations candidates actuellement les plus cohérentes pour la mission.

Utilise les dernières décisions approuvées et distingue :
- données vérifiées ;
- hypothèses ;
- estimations.

Ne cherche pas à dépenser tout le budget.

Les critères éliminatoires précèdent les scores.

Les configurations doivent représenter de vraies stratégies différentes, pas des variantes artificielles.

Pour chaque configuration indique :
- objectif ;
- composants ;
- coût estimé ;
- réserve budgétaire ;
- points forts ;
- compromis ;
- risques ;
- évolutivité ;
- variables susceptibles de modifier la décision.

Termine par :
- classement ;
- front de solutions pertinentes ;
- niveau de confiance ;
- éléments devant être contrôlés par ChatGPT.
```

---

## 4.5 Prompt Claude — urgence

```text
MODE : URGENCE

CONFIGURATION ACTUELLE :
[configuration]

VARIABLE VÉRIFIÉE :
[variable]

RÉFÉRENCE :
[référence]

PRIX :
[prix]

VENDEUR :
[vendeur]

STOCK :
[stock]

IMPACT POTENTIEL :
[description]

Recalcule uniquement ce qui est affecté.

Commence obligatoirement par :

VERDICT :
IMPACT : FAIBLE / MOYEN / STRUCTUREL
RECOMPOSITION : OUI / NON

Si recomposition :
- nouvelle configuration ;
- composants modifiés ;
- coût avant/après ;
- conséquences PSU ;
- conséquences refroidissement ;
- conséquences boîtier ;
- conséquences écrans ;
- conséquences budget ;
- coût d'opportunité ;
- risques.

Termine par :

POINTS À CONTRÔLER PAR CHATGPT :
```

---

## 4.6 Sortie attendue de Claude

La sortie doit être facilement transmissible.

Exemple :

```text
MODE : URGENCE

VERDICT : RECOMPOSITION JUSTIFIÉE

RTX 5080 → RTX 5090

Budget avant : 5 880 €
Budget après : 5 990 €

PSU : modification nécessaire
Boîtier : compatible
CPU : inchangé
Écrans : inchangés

RISQUE :
faible

À CONTRÔLER PAR CHATGPT :
- prix réel
- fiabilité vendeur
- disponibilité
- modèle exact GPU
```

---

## 4.7 Erreurs à éviter

Claude ne doit pas :

- défendre automatiquement la configuration précédente ;
- inventer des prix ;
- inventer du stock ;
- transformer une estimation en fait ;
- dépasser le budget silencieusement ;
- reconstruire toute l'étude pour une petite variation ;
- devenir lui-même l'orchestrateur marché.

---

# 5. ChatGPT

## 5.1 Rôle

ChatGPT est :

**ORCHESTRATEUR + CONTRÔLEUR CONTRADICTOIRE + RECHERCHE MARCHÉ**

Il doit :

- contrôler Claude ;
- trouver les incohérences ;
- vérifier les deals ;
- rechercher en parallèle ;
- déterminer l'impact d'une nouvelle variable ;
- décider si Claude doit être relancé ;
- produire une décision exécutable.

---

## 5.2 Classification d'une nouvelle variable

À chaque nouvelle information :

```text
NOUVELLE INFORMATION
       ↓
Fiable ?
       ↓
Impact ?
```

### Impact faible

Traitement local.

### Impact moyen

Analyse plus poussée.

### Impact structurel

```text
CLAUDE URGENCE
```

---

## 5.3 Prompt ChatGPT — deal normal

```text
MODE : DEAL

CONFIGURATION :
[configuration]

PRODUIT :
[produit]

RÉFÉRENCE EXACTE :
[référence]

PRIX :
[prix]

VENDEUR :
[vendeur]

LIEN :
[lien]

STOCK :
[stock]

SOURCE :
Dealabs / Amazon / autre

Analyse le deal.

Vérifie :
- référence ;
- vendeur ;
- prix marché ;
- stock ;
- garantie ;
- livraison ;
- compatibilité ;
- alternatives.

Recherche également en parallèle les offres concurrentes pertinentes.

Réponds court :

VERDICT :
PRIX :
VENDEUR :
COMPATIBILITÉ :
IMPACT :
CLAUDE À RELANCER : OUI/NON
ACTION :
```

---

## 5.4 Prompt ChatGPT — variable structurelle

```text
MODE : IMPACT

CONFIGURATION ACTUELLE :
[configuration]

NOUVELLE VARIABLE :
[variable]

DÉTAILS :
[détails]

Détermine uniquement :

1. fiabilité de l'information ;
2. impact système ;
3. nécessité de relancer Claude.

Réponds :

IMPACT : FAIBLE / MOYEN / STRUCTUREL

CLAUDE URGENCE : OUI / NON

Si OUI :
génère immédiatement le paquet minimal à copier-coller à Claude.
```

---

## 5.5 Prompt ChatGPT — retour Claude

```text
MODE : CONTRÔLE CLAUDE

Voici la recomposition Claude :

[COLLER SORTIE CLAUDE]

Contrôle contradictoirement uniquement les changements importants.

Vérifie :
- compatibilité ;
- budget ;
- dimensionnement ;
- coût d'opportunité ;
- bruit ;
- refroidissement ;
- durée de vie ;
- cohérence écrans ;
- hypothèses non vérifiées.

Ne refais pas toute l'étude si elle n'est pas nécessaire.

Réponds :

VERDICT :
ERREURS :
RISQUES :
POINTS À VÉRIFIER :
ACTION :
```

---

## 5.6 Prompt ChatGPT — validation finale

```text
MODE : FINAL

CONFIGURATION :
[configuration]

PRIX FINAUX :

CPU :
GPU :
CM :
RAM :
SSD :
PSU :
REFROIDISSEMENT :
BOÎTIER :
ÉCRANS :
PÉRIPHÉRIQUES :

TOTAL :

VENDEURS :

Tous les prix sont ceux affichés au panier.

Effectue uniquement la validation finale :

- compatibilité ;
- budget ;
- vendeurs ;
- stock ;
- cohérence système ;
- anomalie évidente.

Réponds :

VERDICT : GO / NO-GO

ANOMALIE :
[si nécessaire]

ACTION :
```

---

## 5.7 Longueur attendue

### Deal simple

5–10 lignes.

### Deal important

10–20 lignes.

### Urgence

Verdict immédiatement visible.

### Conception

Réponse détaillée autorisée.

---

## 5.8 Erreurs à éviter

ChatGPT ne doit pas :

- relancer Claude pour tout ;
- refaire systématiquement toute la configuration ;
- chercher 20 deals simultanément ;
- confondre promotion et bonne affaire ;
- considérer Dealabs comme vérité ;
- favoriser artificiellement Amazon ;
- ralentir une décision déjà suffisamment sûre.

---

# 6. Dealabs

## 6.1 Rôle

Dealabs est le :

**RADAR PRINCIPAL DE PROMOTIONS**

Il sert à détecter rapidement :

- promotions ;
- erreurs de prix ;
- coupons ;
- ventes flash ;
- baisses de prix ;
- offres inhabituelles.

---

## 6.2 Ce que Dealabs ne fait PAS

Dealabs ne valide pas :

- la compatibilité ;
- la qualité réelle du produit ;
- la pertinence pour notre configuration ;
- le vendeur ;
- le rapport coût/opportunité ;
- la fiabilité de l'offre.

Un deal très chaud peut être inutile pour nous.

---

## 6.3 Procédure

Lorsqu'une offre intéressante apparaît :

collecter :

```text
Produit :
Référence exacte :
Prix :
Prix barré :
Vendeur :
Stock :
Livraison :
Code promo :
Commentaires intéressants :
Lien :
```

Puis transmettre à ChatGPT.

---

## 6.4 Commentaires Dealabs

Les commentaires servent surtout à détecter :

- erreur dans la fiche ;
- coupon caché ;
- problème vendeur ;
- version différente ;
- problème de garantie ;
- meilleure offre concurrente ;
- disponibilité réelle.

Ils constituent un signal, pas une preuve.

---

# 7. Amazon Prime

## 7.1 Rôle

Amazon Prime est une :

**SOURCE COMMERCIALE SUPPLÉMENTAIRE**

Il peut fournir :

- prix spécifiques ;
- promotions Prime ;
- livraison rapide ;
- ventes flash ;
- disponibilité intéressante.

---

## 7.2 Règle importante

ChatGPT ne voit pas nécessairement le même prix que le compte Amazon de l'utilisateur.

Le prix réellement visible dans le compte utilisateur est prioritaire.

Format :

```text
PRIX PRIME RÉEL :
[prix]
```

---

## 7.3 Procédure

Lorsqu'une offre Prime est intéressante :

```text
Produit :
Référence :
Prix Prime :
Vendeur :
Expédié par :
Livraison :
Stock :
Coupon éventuel :
```

Puis comparaison avec :

- Dealabs ;
- autres marchands ;
- historique ;
- Mino ;
- Shoptimate.

---

## 7.4 Anti-FOMO

Badges comme :

```text
OFFRE ÉCLAIR
PLUS QUE X
FINIT DANS XX:XX
```

ne déclenchent jamais seuls un achat.

---

# 8. Mino

## 8.1 Rôle

Mino est un :

**COMPARATEUR / DÉTECTEUR DE COUPONS DE DERNIÈRE ÉTAPE**

Il est utilisé principalement dans le profil navigateur principal.

---

## 8.2 Moment d'utilisation

Mino intervient APRÈS :

```text
configuration validée
+
deal validé
```

Il sert ensuite à vérifier :

- prix concurrent ;
- coupon ;
- cashback éventuel ;
- variation de prix.

---

## 8.3 Règle

Une offre Mino n'est jamais automatiquement meilleure.

Si Mino trouve un autre marchand :

```text
nouveau vendeur
      ↓
validation ChatGPT
      ↓
achat éventuel
```

---

# 9. Shoptimate

## 9.1 Rôle

Shoptimate constitue une :

**DEUXIÈME COUCHE DE COMPARAISON**

Utilisation dans un profil navigateur séparé.

---

## 9.2 Fonction

Il sert à vérifier :

- même référence ailleurs ;
- coût livraison ;
- prix final ;
- éventuels coupons.

---

## 9.3 Règle de sécurité

Ne pas utiliser Shoptimate comme source d'identité ou de paiement.

Son résultat doit être vérifié directement sur le site marchand.

---

# 10. Sites marchands

## 10.1 Rôle

Le marchand constitue la :

**SOURCE DE VÉRITÉ TRANSACTIONNELLE**

Le prix réellement payable est celui du panier.

---

## 10.2 Vérifications finales

Avant achat :

```text
Référence exacte
Prix TTC
Livraison
Disponibilité
Vendeur réel
Garantie
Conditions de retour
Adresse
Mode de paiement
Total panier
```

---

## 10.3 Nouveau marchand

Tout nouveau vendeur doit être évalué.

ChatGPT vérifie :

- identité ;
- ancienneté ;
- réputation ;
- mentions légales ;
- SAV ;
- garantie ;
- retours ;
- paiement ;
- signalements récents.

Verdict :

```text
LISTE BLANCHE
ou
REFUSÉ
```

---

# 11. Liste blanche marchands

Construite progressivement pendant les simulations.

Un vendeur de la liste blanche peut être utilisé plus rapidement le jour J.

Un vendeur inconnu nécessite validation.

En mode panne totale des IA :

```text
vendeur inconnu = PAS D'ACHAT
```

---

# 12. NordVPN

## 12.1 Rôle

NordVPN est une :

**COUCHE D'HYGIÈNE ET DE PROTECTION RÉSEAU**

Il n'est PAS utilisé normalement pour chercher des prix selon les pays.

---

## 12.2 Utilisation

Pertinent surtout pour :

- navigation exploratoire ;
- sites moins connus ;
- outils dont la politique de confidentialité est peu rassurante.

---

## 12.3 Limites

VPN ≠ anonymat complet.

Il ne masque pas nécessairement :

- compte connecté ;
- cookies ;
- fingerprint navigateur ;
- données données volontairement au marchand.

---

# 13. Aerix / simulateur airflow

## 13.1 Rôle

Aerix ou outil similaire est un :

**OUTIL DE COMPARAISON THERMIQUE SECONDAIRE**

Il sert surtout à comparer :

- nombre de ventilateurs ;
- intake/exhaust ;
- position AIO ;
- position radiateur ;
- disposition GPU ;
- profils de ventilation.

---

## 13.2 Utilisation correcte

Exemple :

```text
Configuration A
3 intake + 2 exhaust

vs

Configuration B
2 intake + 3 exhaust
```

L'outil aide à comparer les tendances.

---

## 13.3 Interdiction

Ne jamais traiter une température simulée comme une température réelle garantie.

Exemple interdit :

```text
Aerix indique 67 °C
→ le PC fera réellement 67 °C
```

Utilisation correcte :

```text
Aerix indique que A semble thermiquement plus favorable que B.
→ chercher ensuite des tests réels.
```

---

# 14. Chronomètre

## 14.1 Rôle

Le chronomètre mesure l'efficacité réelle du système.

Mesure principale :

```text
T0 = deal détecté

↓

T1 = décision exécutable
```

---

## 14.2 Première phase

Pendant les premières simulations :

mesurer uniquement le temps total.

---

## 14.3 Deuxième phase

Si le processus est trop lent, mesurer :

```text
Recherche Dealabs
Validation ChatGPT
Claude
Lecture humaine
Recherche parallèle
Mino
Shoptimate
Validation finale
```

---

## 14.4 KPI principal

```text
Temps détection → décision exécutable
```

Pas :

```text
temps de génération de l'IA
```

Un résultat généré en 40 secondes mais nécessitant 6 minutes de lecture est mauvais.

---

# 15. Profils navigateur

## Profil principal

Utiliser pour :

- comptes marchands ;
- Amazon Prime ;
- Mino ;
- commandes réelles.

## Profil comparaison

Utiliser pour :

- Shoptimate ;
- exploration ;
- marchands inconnus ;
- comparaisons.

Éviter d'y conserver les données de paiement.

---

# 16. Achat one-shot

Principe nominal :

```text
OBSERVATION
↓
CONFIGURATION
↓
VALIDATION
↓
PRIX FINAUX
↓
ONE-SHOT
```

Objectif :

acheter autant que possible tout le système dans une même fenêtre.

---

# 17. Exceptions au one-shot

Une exception est possible si :

### Offre extraordinaire

Exemple :

GPU très fortement remisé avant Black Friday.

### Promotion future confirmée

Exemple :

```text
vente flash officiellement annoncée
demain 08:00
prix connu
```

### Risque de rupture exceptionnel

Seulement si corroboré.

Toute exception importante doit être évaluée par ChatGPT et éventuellement Claude.

---

# 18. Promotion future

Format de transmission :

```text
PROMO FUTURE CONFIRMÉE : OUI

PRODUIT :
RÉFÉRENCE :
SOURCE :
DATE :
HEURE :
PRIX FUTUR CONNU : OUI/NON
PRIX :
```

ChatGPT décide ensuite :

```text
ACHETER MAINTENANT
ATTENDRE
DÉPLACER LE ONE-SHOT
CLAUDE URGENCE
```

---

# 19. Configurations de secours

Les trois jours précédant le Black Friday :

```text
24 novembre 20:00
25 novembre 20:00
26 novembre 20:00
```

Claude produit et actualise les configurations de secours.

ChatGPT les contrôle.

---

# 20. Pack final T−1

Le 26 novembre au soir :

```text
PLAN A
configuration principale

PLAN B
GPU cible indisponible

PLAN C
GPU supérieur devenu rentable

PLAN D
configuration Value

PLAN E
panne totale des IA
```

Chaque référence du PLAN E doit avoir :

```text
Référence exacte
Prix maximal
Vendeurs autorisés
Substitut
Conditions
```

---

# 21. Mode dégradé

## Claude indisponible

ChatGPT :

- vérifie les deals ;
- traite les substitutions déjà connues ;
- évite les architectures nouvelles.

## ChatGPT indisponible

Claude :

- utilise les configurations déjà validées ;
- devient plus conservateur.

## Les deux indisponibles

Utilisateur :

```text
PLAN E UNIQUEMENT
```

Aucune improvisation.

---

# 22. Principe de créativité

```text
Mode normal
→ créativité autorisée

Un agent indisponible
→ créativité réduite

Deux agents indisponibles
→ aucune créativité
```

---

# 23. Format standard utilisateur → ChatGPT

```text
MODE :

CONFIG :

PRODUIT :

RÉFÉRENCE :

PRIX :

VENDEUR :

LIEN :

STOCK :

SOURCE :

PRIX PRIME :

SHOPTIMATE :

MINO :

QUESTION :
```

---

# 24. Format standard ChatGPT → utilisateur

```text
VERDICT :

PRIX :

VENDEUR :

COMPATIBILITÉ :

IMPACT :

CLAUDE À RELANCER : OUI/NON

ACTION :
```

---

# 25. Format standard ChatGPT → Claude

```text
MODE : URGENCE

CONFIGURATION ACTUELLE :

VARIABLE VÉRIFIÉE :

RÉFÉRENCE :

PRIX :

VENDEUR :

STOCK :

CAUSE DU RECALCUL :

QUESTION :
Cette variable justifie-t-elle une recomposition ?
```

---

# 26. Format standard Claude → ChatGPT

```text
MODE : URGENCE

VERDICT :

RECOMPOSITION :

CHANGEMENTS :

BUDGET AVANT :

BUDGET APRÈS :

CONSÉQUENCES :

RISQUES :

POINTS À CONTRÔLER PAR CHATGPT :
```

---

# 27. Anti-FOMO

Un achat ne doit jamais être déclenché uniquement par :

```text
-20 %
vente flash
plus que 2
offre populaire
500°
fin dans 10 minutes
```

Il faut une combinaison de :

- prix pertinent ;
- besoin réel ;
- compatibilité ;
- vendeur fiable ;
- risque de disponibilité ;
- coût de substitution.

---

# 28. Anti-perfectionnisme

Inversement :

si une offre est déjà excellente,

ne pas risquer de la perdre uniquement pour espérer :

```text
10 €
20 €
1 %
2 %
```

d'économie supplémentaire.

L'objectif est :

```text
minimiser le regret attendu
```

pas obtenir le minimum historique absolu.

---

# 29. Règle finale

Avant toute décision importante, répondre à :

```text
1. L'information est-elle fiable ?

2. Est-elle réellement importante ?

3. Change-t-elle la configuration ?

4. Claude doit-il être relancé ?

5. Existe-t-il une meilleure offre ?

6. Le vendeur est-il fiable ?

7. La configuration reste-t-elle dans le budget ?

8. Le système complet reste-t-il cohérent ?

9. Le gain d'attendre dépasse-t-il le risque d'attendre ?

10. Avons-nous assez d'informations pour agir maintenant ?
```

Lorsque la réponse à la dernière question devient :

```text
OUI
```

il faut décider.

Le système ne doit pas continuer à analyser simplement parce qu'il est capable de continuer à analyser.
