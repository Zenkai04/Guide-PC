# Manuel d'utilisation des outils — Projet PC Black Friday 2026

Version : 2.1
Statut : baseline Web validée + stratégie de décision pragmatique (§31) issue du benchmark CLI #1
Mise à jour : 31 octobre 2026

---

# 1. Objet

Ce document définit comment utiliser les différents outils et agents du projet d'achat PC Black Friday 2026.

Le workflow Web validé est :

```text
Guide-PC
   ↓
Claude Web — MODE NORMAL
   ↓
Architectures candidates
   ↓
ChatGPT Web — contrôle contradictoire
   ↓
Consensus architectural
   ↓
Claude Web — MODE BOM
   ↓
BOM candidate exacte
   ↓
ChatGPT Web — audit BOM
   ↓
BOM GELÉE
   ↓
Recherche marché
   ↓
Dealabs / Amazon / marchands
   ↓
Validation des deals
   ↓
Mino / Shoptimate
   ↓
Prix réels au panier
   ↓
Validation finale
   ↓
GO / NO-GO
   ↓
Achat
```

Principe central de la version 2 :

> Une architecture techniquement correcte n'est pas encore une liste d'achat.
> La recherche commerciale ne commence qu'après production, audit et gel d'une BOM exploitable.

Exception encadrée : relevés de prix indicatifs pour vérifier la faisabilité économique avant le gel (voir §31.3).

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

Toujours distinguer :

```text
FAIT VÉRIFIÉ
ESTIMATION
HYPOTHÈSE
RECOMMANDATION
```

---

# 3. Guide-PC / bibliothèque du projet

Le dépôt `Guide-PC` constitue la base normative du projet.

Organisation :

```text
00–03 : besoin, entrées, processus, règles
04–20 : moteur de composition
21–29 : moteur d'acquisition
30 : manuel opérationnel
Compositions/ : configurations et retours critiques
```

Une version récente d'une configuration n'est pas automatiquement correcte.

Toujours distinguer :

```text
PROPOSITION
RETOUR CRITIQUE
DÉCISION APPROUVÉE
```

Le guide définit une méthode, pas une simple liste de composants.

---

# 4. Claude Web

## 4.1 Rôle

Claude Web est le moteur principal de :

- composition ;
- recomposition ;
- compatibilité et dimensionnement ;
- analyse des compromis ;
- configurations de secours ;
- matérialisation d'une architecture approuvée ;
- production et correction de BOM.

Claude n'est pas :

- le contrôleur contradictoire final ;
- le validateur principal des vendeurs ;
- le décideur final d'achat ;
- l'autorité qui gèle sa propre BOM.

## 4.2 Modes

Claude reconnaît quatre modes :

```text
MODE : NORMAL
MODE : BOM
MODE : CORRECTION BOM
MODE : URGENCE
```

### MODE NORMAL

Utilisé pour générer et comparer des architectures.

Un niveau de composant peut encore être générique s'il est suffisamment précis pour comparer les stratégies.

Exemples acceptables :

```text
RTX 5080
64 Go DDR5-6000 CL30
SSD NVMe Gen4 2 To haut de gamme
```

### MODE BOM

Déclenché uniquement après consensus architectural transmis par ChatGPT.

À ce stade, les formulations suivantes ne suffisent plus :

```text
RTX 5080
64 Go DDR5
SSD 2 To
1000 W Gold
écran OLED 34 pouces
```

L'objectif est de produire des références réellement recherchables.

### MODE CORRECTION BOM

Utilisé après audit ChatGPT lorsqu'une correction locale est demandée.

Ne pas recommencer toute l'étude si seules quelques lignes sont concernées.

### MODE URGENCE

Utilisé lorsqu'une variable structurelle peut modifier l'espace de solutions :

- GPU très fortement remisé ;
- GPU cible indisponible ;
- changement CPU ;
- changement de résolution ;
- écran central différent ;
- variation majeure du budget ;
- incompatibilité majeure ;
- composant directeur devenu anormalement intéressant.

## 4.3 Répartition Claude / ChatGPT

Claude :

```text
composition
→ recomposition
→ matérialisation
→ BOM candidate
→ correction technique
```

ChatGPT :

```text
orchestration
→ contrôle contradictoire
→ audit BOM
→ validation marché
→ validation vendeurs/deals
→ décision de relance
→ GO / NO-GO
```

Une `VARIABLE VÉRIFIÉE` transmise par ChatGPT devient une nouvelle donnée d'entrée et ne doit pas être remplacée silencieusement par une ancienne hypothèse.

## 4.4 Philosophie du moteur

- la mission prime ;
- les critères éliminatoires précèdent les scores ;
- une incompatibilité ne peut jamais être compensée ;
- le budget maximal est une limite, pas un objectif de dépense ;
- les composants doivent être évalués au niveau du système ;
- le rendement marginal et le coût d'opportunité comptent ;
- C1–C5 constituent un espace de solutions, pas des dogmes ;
- une configuration peut être recomposée si les données changent.

Question à poser lorsque les données changent :

> Quelle configuration est maintenant la meilleure compte tenu du nouvel état du système ?

## 4.5 Règles du MODE BOM

### Ne pas extrapoler l'architecture

Une architecture approuvée doit être matérialisée telle qu'elle a été transmise.

Si une partie reste ambiguë :

- ne pas choisir silencieusement une variante ;
- matérialiser les parties certaines ;
- marquer le sous-système concerné `À DÉTERMINER` ;
- l'ajouter aux `POINTS NON RÉSOLUS`.

### Séparation stricte BOM / marché

En MODE BOM, la recherche externe est limitée à la vérification technique :

- constructeur ;
- documentation officielle ;
- référence/SKU ;
- spécifications ;
- dimensions ;
- connectique ;
- compatibilité ;
- VESA ;
- poids ;
- caractéristiques électriques.

Ne pas consulter volontairement :

- Dealabs ;
- Amazon pour les prix ;
- boutiques pour les promotions ;
- Google Shopping ;
- comparateurs de prix ;
- Mino ;
- Shoptimate ;
- historiques commerciaux.

Un prix découvert accidentellement ne doit pas influencer la BOM.

Exception : ChatGPT fournit explicitement une `VARIABLE VÉRIFIÉE`.

### Références incertaines

Ne jamais inventer un SKU.

Utiliser :

```text
RÉFÉRENCE À VÉRIFIER
```

ou :

```text
RÉFÉRENCE À DÉTERMINER
```

### Statut du choix

Chaque ligne doit comporter :

```text
STATUT DU CHOIX
```

Valeurs autorisées :

```text
APPROUVÉ
DÉRIVÉ DE L'ARCHITECTURE
PROPOSITION CLAUDE
À DÉTERMINER
```

### Préférences utilisateur inconnues

Pour une catégorie dépendant fortement d'une préférence jamais arrêtée, Claude peut proposer un candidat mais doit le marquer `PROPOSITION CLAUDE`.

### Prix

Si aucun prix cible ou maximal n'a été défini :

```text
NON DÉFINI
```

Ne jamais fabriquer un seuil.

## 4.6 Contenu obligatoire de la BOM

Vérifier explicitement :

- CPU ;
- GPU ;
- carte mère ;
- RAM ;
- stockage ;
- alimentation ;
- refroidissement CPU ;
- boîtier ;
- ventilateurs supplémentaires ;
- écran central ;
- écran gauche ;
- écran droit ;
- support(s) écran ;
- clavier ;
- souris ;
- casque ;
- webcam ;
- câbles indispensables ;
- adaptateurs indispensables ;
- autres accessoires réellement nécessaires.

Chaque ligne comporte au minimum :

- numéro ;
- catégorie ;
- fabricant ;
- modèle exact ;
- référence/SKU ;
- quantité ;
- caractéristiques critiques ;
- alternative(s) ;
- dépendances ;
- prix cible ;
- prix maximal ;
- `STATUT DU CHOIX`.

## 4.7 Contrôles internes Claude avant transmission

Contrôler au minimum :

```text
CPU ↔ carte mère
CPU ↔ refroidissement
RAM ↔ carte mère
RAM ↔ refroidissement
GPU ↔ boîtier
GPU ↔ alimentation
GPU ↔ connecteurs alimentation
PSU ↔ boîtier
AIO/ventirad ↔ boîtier
ventilateurs ↔ emplacements
SSD ↔ M.2 / PCIe
GPU ↔ écrans
écrans ↔ connectique
supports ↔ VESA
supports ↔ poids
dimensions globales
budget connu
```

Ce contrôle ne remplace pas l'audit contradictoire de ChatGPT.

## 4.8 Sortie obligatoire du MODE BOM

Commencer par :

```text
MODE : BOM

ARCHITECTURE SOURCE :
VERSION BOM CANDIDATE :
ÉTAT :
```

Terminer par :

```text
COMPATIBILITÉS CONTRÔLÉES :
...

POINTS NON RÉSOLUS :
...

HYPOTHÈSES :
...

POINTS À AUDITER PAR CHATGPT :
...
```

Puis obligatoirement :

```text
BOM CANDIDATE COMPLÈTE — À AUDITER PAR CHATGPT
```

ou :

```text
BOM INCOMPLÈTE — NE PAS GELER
```

Claude ne prononce jamais lui-même `BOM GELÉE`.

## 4.9 MODE CORRECTION BOM

Claude doit :

- corriger uniquement les lignes concernées ;
- recalculer leurs dépendances ;
- incrémenter la version ;
- signaler tout impact architectural.

Si une correction remet en cause l'architecture :

```text
IMPACT STRUCTUREL DÉTECTÉ
RETOUR À L'ARCHITECTURE NÉCESSAIRE
```

## 4.10 Prompt Claude — génération normale

```text
MODE : NORMAL

Applique le corpus Guide-PC disponible dans le projet.

OBJECTIF :
Produire les architectures candidates actuellement les plus cohérentes pour la mission.

Utilise les dernières décisions approuvées et distingue :
- données vérifiées ;
- hypothèses ;
- estimations.

Ne cherche pas à dépenser tout le budget.

Les critères éliminatoires précèdent les scores.

Les configurations doivent représenter de vraies stratégies différentes.

Pour chaque configuration indique :
- objectif ;
- composants ou niveaux de référence ;
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

## 4.11 Prompt Claude — BOM

```text
MODE : BOM

ARCHITECTURE APPROUVÉE :
[architecture transmise par ChatGPT]

OBJECTIF :
Transformer exactement cette architecture en nomenclature réellement achetable.

Ne relance pas une comparaison générale des architectures.

Pour chaque ligne :
- fabricant ;
- modèle exact ;
- référence/SKU si vérifiée ;
- quantité ;
- caractéristiques critiques ;
- alternatives réellement interchangeables ;
- dépendances ;
- prix cible si déjà défini ;
- prix maximal si déjà défini ;
- STATUT DU CHOIX.

N'invente ni référence, ni prix, ni préférence utilisateur.

Ne consulte pas le marché commercial.

Si une partie de l'architecture est ambiguë :
marque-la À DÉTERMINER et garde la BOM incomplète.

Effectue les contrôles de compatibilité internes.

Termine par :
BOM CANDIDATE COMPLÈTE — À AUDITER PAR CHATGPT
ou
BOM INCOMPLÈTE — NE PAS GELER
```

## 4.12 Prompt Claude — urgence

```text
MODE : URGENCE

CONFIGURATION ACTUELLE :
[configuration]

BOM ACTUELLE :
[BOM si elle existe]

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

Commence obligatoirement par :

VERDICT :
IMPACT : FAIBLE / MOYEN / STRUCTUREL
RECOMPOSITION : OUI / NON

Recalcule uniquement ce qui est affecté.

Indique aussi :

IMPACT SUR LA BOM :
INCHANGÉE / MODIFICATION LOCALE / OBSOLÈTE

Termine par :

POINTS À CONTRÔLER PAR CHATGPT :
```

## 4.13 Erreurs à éviter

Claude ne doit pas :

- défendre automatiquement la configuration précédente ;
- inventer des prix ;
- inventer du stock ;
- inventer des SKU ;
- extrapoler silencieusement une architecture ;
- transformer une estimation en fait ;
- dépasser le budget silencieusement ;
- reconstruire toute l'étude pour une petite variation ;
- devenir lui-même l'orchestrateur marché ;
- utiliser un comparateur commercial en MODE BOM ;
- déclarer sa propre BOM gelée.

---

# 5. ChatGPT Web

## 5.1 Rôle

ChatGPT Web est le :

**CENTRE DE PILOTAGE, CONTRÔLEUR CONTRADICTOIRE ET COORDINATEUR MARCHÉ**

Claude reste le moteur principal de composition.

ChatGPT doit :

1. orchestrer ;
2. contrôler Claude contradictoirement ;
3. détecter erreurs, incompatibilités et hypothèses faibles ;
4. décider quand Claude doit être relancé ;
5. empêcher le passage prématuré au marché ;
6. auditer la BOM ;
7. rechercher le marché en parallèle après gel ;
8. vérifier vendeurs et deals ;
9. centraliser l'état courant ;
10. rendre la décision finale exécutable.

## 5.2 Workflow obligatoire

```text
MISSION / CONTRAINTES
        ↓
ARCHITECTURES CLAUDE
        ↓
CONTRÔLE CHATGPT
        ↓
CONSENSUS ARCHITECTURAL
        ↓
CLAUDE BOM
        ↓
AUDIT BOM CHATGPT
        ↓
CORRECTIONS ÉVENTUELLES
        ↓
BOM GELÉE
        ↓
RECHERCHE MARCHÉ
        ↓
VALIDATION DES DEALS
        ↓
ÉVENTUELLES RECOMPOSITIONS
        ↓
PRIX FINAUX AU PANIER
        ↓
GO / NO-GO
```

Aucune phase ne doit être sautée.

## 5.3 États opérationnels

```text
ARCHITECTURE EN ÉTUDE
CLAUDE CORRECTION
ARCHITECTURE APPROUVÉE
CLAUDE BOM
BOM EN AUDIT
BOM À CORRIGER
BOM GELÉE
RECHERCHE MARCHÉ
CLAUDE URGENCE
VALIDATION FINALE
GO
NO-GO
```

## 5.4 Contrôle de l'architecture

Lorsque Claude fournit des candidates, contrôler notamment :

- compatibilité ;
- dimensionnement ;
- budget ;
- rendement marginal ;
- coût d'opportunité ;
- bruit ;
- refroidissement ;
- durée de vie ;
- cohérence du trio d'écrans ;
- hypothèses non vérifiées ;
- données potentiellement périmées.

Verdicts possibles :

```text
ARCHITECTURE VALIDÉE
CLAUDE CORRECTION
CLAUDE NORMAL À RELANCER
```

## 5.5 Consensus architectural

Une architecture est approuvée lorsque :

- aucun critère éliminatoire n'échoue ;
- les incompatibilités majeures sont résolues ;
- le budget est cohérent ;
- les compromis sont compris ;
- Claude et ChatGPT convergent suffisamment.

À ce stade :

```text
ARCHITECTURE APPROUVÉE

PROCHAINE ACTION :
CLAUDE BOM
```

Ne pas commencer Dealabs.

## 5.6 Audit de BOM

Pour chaque ligne, vérifier :

- référence suffisamment précise ;
- `STATUT DU CHOIX` ;
- compatibilité ;
- dimensionnement ;
- dépendances ;
- caractéristiques critiques ;
- alternatives réellement interchangeables ;
- surdimensionnement ;
- sous-dimensionnement ;
- information vérifiée ou hypothétique.

Contrôles croisés :

```text
CPU ↔ carte mère
CPU ↔ refroidissement
RAM ↔ carte mère
RAM ↔ refroidissement
GPU ↔ boîtier
GPU ↔ PSU
PSU ↔ GPU / connecteurs
AIO ↔ boîtier
ventilateurs ↔ boîtier
SSD ↔ M.2 / PCIe
GPU ↔ écrans
écrans ↔ connectique
supports ↔ VESA / poids
budget total connu
```

Réponse :

```text
VERDICT BOM :

CORRECTIONS OBLIGATOIRES :
...

AMBIGUÏTÉS :
...

RISQUES :
...

ÉTAT :
BOM GELÉE / BOM À CORRIGER
```

## 5.7 Gate obligatoire avant marché

La recherche commerciale n'est autorisée que lorsque ChatGPT écrit explicitement :

```text
BOM GELÉE Vx
OK POUR RECHERCHE MARCHÉ
```

Avant cet état :

```text
Dealabs = NON
Mino = NON
Shoptimate = NON
recherche systématique des prix = NON
```

Les vérifications techniques constructeur restent autorisées.

Les relevés de prix indicatifs définis au §31.3 restent autorisés ; ils ne constituent ni une recherche de deals ni une décision d'achat.

## 5.8 Recherche marché

Après gel de la BOM :

l'utilisateur recherche principalement sur :

- Dealabs ;
- Amazon Prime ;
- marchands.

ChatGPT recherche en parallèle :

- mêmes références ;
- alternatives prévalidées ;
- autres vendeurs ;
- promotions absentes de Dealabs ;
- problèmes récents de modèles ;
- disponibilité.

## 5.9 Validation d'un deal

Pour chaque deal vérifier :

- référence exacte ;
- prix TTC réel ;
- vendeur réel ;
- livraison ;
- stock ;
- garantie ;
- réputation récente ;
- compatibilité avec la BOM ;
- prix concurrents ;
- alternatives ;
- impact sur le système.

Réponse courte :

```text
VERDICT :
PRIX :
VENDEUR :
COMPATIBILITÉ :
IMPACT :
CLAUDE À RELANCER :
ACTION :
```

## 5.10 Classification d'une nouvelle variable

### Impact faible

Petit écart de prix, vendeur déjà validé, coupon ou alternative strictement équivalente.

Traitement local.

### Impact moyen

Peut modifier une ou plusieurs lignes de BOM sans changer l'architecture globale.

### Impact structurel

Exemples :

- gamme GPU différente ;
- GPU supérieur exceptionnellement accessible ;
- disparition d'un composant directeur ;
- changement CPU ;
- changement important d'écran/résolution ;
- changement significatif de budget ;
- incompatibilité majeure.

Verdict :

```text
CLAUDE URGENCE
```

## 5.11 Retour Claude après urgence

Contrôler principalement ce qui a changé et ses conséquences.

Toute modification structurelle rend l'ancienne BOM obsolète jusqu'à nouvel audit.

## 5.12 Achat one-shot

Stratégie nominale :

```text
préparer
→ valider
→ figer
→ observer
→ acheter autant que possible dans une même fenêtre
```

Exceptions :

- opportunité extraordinaire ;
- promotion future officiellement confirmée ;
- impossibilité rationnelle de sécuriser tout simultanément.

## 5.13 Anti-FOMO et anti-perfectionnisme

Un stock faible ou une minuterie marketing ne suffisent jamais seuls.

Inversement, une excellente offre ne doit pas être perdue uniquement pour tenter de gagner les derniers euros.

Objectif :

```text
minimiser le regret attendu
```

## 5.14 Mode dégradé

### Claude indisponible

ChatGPT peut traiter :

- changements non structurels ;
- alternatives déjà validées ;
- vendeurs déjà validés.

Pas d'architecture radicalement nouvelle.

### ChatGPT indisponible

Claude applique le protocole de secours et devient plus conservateur.

### Deux agents indisponibles

Uniquement :

- BOM prévalidée ;
- alternatives prévalidées ;
- vendeurs prévalidés ;
- seuils prévalidés.

Aucune créativité.

## 5.15 Longueur des réponses opérationnelles

Deal simple : 5–10 lignes.

Deal important : 10–20 lignes.

Urgence :

```text
VERDICT
IMPACT
CLAUDE À RELANCER : OUI/NON
ACTION IMMÉDIATE
```

## 5.16 Prompt ChatGPT — deal normal

```text
MODE : DEAL NORMAL

BOM GELÉE :
[version]

PRODUIT :
[produit]

RÉFÉRENCE :
[référence]

PRIX :
[prix]

VENDEUR :
[vendeur]

STOCK :
[stock]

LIVRAISON :
[livraison]

SOURCE :
[source]

Vérifie :
- référence ;
- vendeur ;
- prix final ;
- stock ;
- garantie ;
- compatibilité avec la BOM ;
- alternatives ;
- impact.

Réponds avec :

VERDICT :
PRIX :
VENDEUR :
COMPATIBILITÉ :
IMPACT :
CLAUDE À RELANCER :
ACTION :
```

## 5.17 Prompt ChatGPT — variable structurelle

```text
MODE : VARIABLE STRUCTURELLE

BOM ACTUELLE :
[version]

VARIABLE :
[...]

RÉFÉRENCE :
[...]

PRIX :
[...]

VENDEUR :
[...]

STOCK :
[...]

Évalue immédiatement :

VERDICT :
IMPACT : FAIBLE / MOYEN / STRUCTUREL
CLAUDE URGENCE : OUI / NON
ACTION IMMÉDIATE :

Si Claude doit être relancé, fournis le paquet minimal prêt à copier-coller.
```

## 5.18 Prompt ChatGPT — retour Claude

```text
MODE : RETOUR CLAUDE

Voici la sortie Claude :
[coller]

Contrôle contradictoirement uniquement ce qui doit l'être.

Indique :

VERDICT :
ERREURS / INCOHÉRENCES :
RISQUES :
CORRECTIONS :
ÉTAT ACTUEL :
PROCHAINE ACTION :
```

## 5.19 Prompt ChatGPT — audit BOM

```text
MODE : AUDIT BOM

Voici la BOM candidate Claude :
[coller]

Audite chaque ligne et les dépendances croisées.

Vérifie notamment :
- précision des références ;
- STATUT DU CHOIX ;
- compatibilités ;
- dimensionnement ;
- alternatives ;
- hypothèses ;
- éléments manquants.

Réponds :

VERDICT BOM :

CORRECTIONS OBLIGATOIRES :
...

AMBIGUÏTÉS :
...

RISQUES :
...

ÉTAT :
BOM À CORRIGER
ou
BOM GELÉE Vx — OK POUR RECHERCHE MARCHÉ
```

## 5.20 Prompt ChatGPT — validation finale

```text
MODE : VALIDATION FINALE

BOM GELÉE :
[version]

PANIER FINAL :
[liste des références, vendeurs et prix réels]

Vérifie :
- conformité à la BOM ;
- prix final TTC ;
- livraison ;
- vendeurs ;
- disponibilité ;
- garantie ;
- budget total ;
- incohérences de dernière minute ;
- risque d'attendre.

Termine par :

GO
ou
NO-GO
```

## 5.21 Centralisation

Ce chat est le centre de pilotage Web.

Il doit toujours pouvoir répondre à :

```text
Quelle architecture est approuvée ?
Quelle BOM est valide ?
Quelle version ?
Quels éléments restent ouverts ?
Quels deals sont validés ?
Quels vendeurs sont autorisés ?
Claude doit-il être relancé ?
Quelle est la prochaine action ?
```

---

# 6. Dealabs

Dealabs est le radar principal de promotions.

Il sert à détecter :

- promotions ;
- erreurs de prix ;
- coupons ;
- ventes flash ;
- baisses de prix ;
- offres inhabituelles.

Dealabs ne valide pas :

- compatibilité ;
- pertinence pour notre configuration ;
- vendeur ;
- coût d'opportunité ;
- fiabilité de l'offre.

Pour une offre intéressante, relever :

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

---

# 7. Amazon Prime

Amazon Prime est une source commerciale supplémentaire.

Le prix réellement visible dans le compte utilisateur est prioritaire.

Format :

```text
PRIX PRIME RÉEL :
[prix]
```

Une offre Prime doit ensuite être comparée avec les autres marchands et les outils de comparaison.

---

# 8. Mino

Mino intervient après :

```text
BOM GELÉE
+
deal initialement validé
```

Il ne sert pas à choisir l'architecture ni à matérialiser la BOM.

Il vérifie notamment :

- prix concurrent ;
- coupon ;
- cashback éventuel ;
- variation de prix.

Un nouveau vendeur trouvé via Mino doit être validé par ChatGPT.

---

# 9. Shoptimate

Shoptimate constitue une deuxième couche de comparaison.

Il sert à vérifier :

- même référence ailleurs ;
- coût livraison ;
- prix final ;
- coupons éventuels.

Le résultat doit toujours être vérifié directement sur le site marchand.

---

# 10. Sites marchands

Le marchand constitue la source de vérité transactionnelle.

Avant achat vérifier :

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

Tout nouveau vendeur doit être évalué.

Verdict :

```text
LISTE BLANCHE
ou
REFUSÉ
```

---

# 11. Liste blanche marchands

Construite progressivement pendant les simulations.

En mode panne totale des IA :

```text
vendeur inconnu = PAS D'ACHAT
```

---

# 12. NordVPN

NordVPN est une couche d'hygiène et de protection réseau.

Il n'est pas utilisé normalement pour chercher des prix selon les pays.

Il ne supprime pas :

- cookies ;
- compte marchand ;
- empreinte navigateur ;
- suivi par extension ;
- adresse réelle de livraison ;
- TVA et contraintes commerciales.

---

# 13. Aerix / simulateur airflow

Aerix ou un outil équivalent est un outil secondaire de comparaison thermique / airflow.

Il peut comparer :

- 2 vs 3 ventilateurs frontaux ;
- 120 vs 140 mm ;
- AIO frontal vs supérieur ;
- intake/exhaust ;
- pression positive/négative ;
- boîtiers alternatifs.

Ne pas traiter ses températures ou valeurs acoustiques comme des mesures physiques exactes.

---

# 14. Chronomètre

Le chronomètre mesure l'efficacité réelle du système, pas seulement la vitesse d'un modèle.

## Conception

```text
T0 = début génération architecture
↓
consensus
↓
BOM candidate
↓
audit
↓
BOM gelée
```

## Acquisition

```text
T0 = deal détecté
↓
validation
↓
éventuelle urgence Claude
↓
décision exécutable
```

Pendant les premières simulations, mesurer surtout le temps total.

Si le processus est trop lent, décomposer ensuite :

```text
Claude NORMAL
Contrôle ChatGPT
Lecture humaine
Claude BOM
Audit ChatGPT
Correction BOM
Recherche Dealabs
Recherche parallèle
Claude URGENCE
Mino
Shoptimate
Validation finale
```

KPI :

```text
Temps début architecture → BOM gelée exploitable
Temps humain d'orchestration (lecture, copier-coller, réponses aux agents)
```

et, pour le marché :

```text
Temps détection → décision exécutable
```

---

# 15. Profils navigateur

## Profil principal

- comptes marchands ;
- Amazon Prime ;
- Mino ;
- commandes réelles.

## Profil comparaison

- Shoptimate ;
- exploration ;
- marchands inconnus ;
- comparaisons.

Éviter d'y conserver les données de paiement.

---

# 16. Achat one-shot

Principe nominal :

```text
ARCHITECTURE
↓
CONSENSUS
↓
BOM CANDIDATE
↓
AUDIT
↓
BOM GELÉE
↓
OBSERVATION DU MARCHÉ
↓
PRIX FINAUX
↓
ONE-SHOT
```

---

# 17. Exceptions au one-shot

Exception possible si :

- offre extraordinaire ;
- promotion future confirmée ;
- risque de rupture exceptionnel corroboré.

Toute exception importante doit être évaluée par ChatGPT et éventuellement Claude.

---

# 18. Promotion future

Format :

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

ChatGPT décide :

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

## Deal

```text
MODE : DEAL NORMAL

BOM GELÉE :

PRODUIT :

RÉFÉRENCE :

PRIX :

VENDEUR :

LIEN :

STOCK :

LIVRAISON :

SOURCE :

PRIX PRIME :

SHOPTIMATE :

MINO :

QUESTION :
```

## Retour Claude / BOM

```text
MODE : RETOUR CLAUDE
ou
MODE : AUDIT BOM

ARCHITECTURE :

VERSION BOM :

SORTIE CLAUDE :
[coller]
```

---

# 24. Format standard ChatGPT → utilisateur

```text
VERDICT :

ÉTAT ACTUEL :

IMPACT :

CLAUDE À RELANCER : OUI/NON

ACTION :
```

Pour un deal :

```text
VERDICT :
PRIX :
VENDEUR :
COMPATIBILITÉ :
IMPACT :
CLAUDE À RELANCER :
ACTION :
```

---

# 25. Format standard ChatGPT → Claude

## Passage à la BOM

```text
ARCHITECTURE APPROUVÉE :
[architecture]

PROCHAINE ACTION :
CLAUDE BOM

Produis la BOM candidate exacte conformément au manuel.
```

## Urgence

```text
MODE : URGENCE

CONFIGURATION ACTUELLE :

BOM ACTUELLE :

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

## Architecture

```text
MODE : NORMAL

CLASSEMENT :
...

RECOMMANDATION :
...

NIVEAU DE CONFIANCE :
...

POINTS À CONTRÔLER PAR CHATGPT :
...
```

## BOM

```text
MODE : BOM

ARCHITECTURE SOURCE :

VERSION BOM CANDIDATE :

ÉTAT :

[BOM]

COMPATIBILITÉS CONTRÔLÉES :
...

POINTS NON RÉSOLUS :
...

HYPOTHÈSES :
...

POINTS À AUDITER PAR CHATGPT :
...

BOM CANDIDATE COMPLÈTE — À AUDITER PAR CHATGPT
ou
BOM INCOMPLÈTE — NE PAS GELER
```

## Urgence

```text
MODE : URGENCE

VERDICT :

RECOMPOSITION :

CHANGEMENTS :

BUDGET AVANT :

BUDGET APRÈS :

CONSÉQUENCES :

RISQUES :

IMPACT SUR LA BOM :

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

Une excellente offre ne doit pas être perdue uniquement pour tenter de gagner :

```text
10 €
20 €
1 %
2 %
```

Objectif :

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
3. L'architecture est-elle approuvée ?
4. Une BOM exacte existe-t-elle ?
5. La BOM a-t-elle été auditée et gelée ?
6. Sommes-nous autorisés à passer au marché ?
7. La nouvelle information change-t-elle la configuration ou la BOM ?
8. Claude doit-il être relancé ?
9. Existe-t-il une meilleure offre ?
10. Le vendeur est-il fiable ?
11. Le système reste-t-il dans le budget ?
12. Le système complet reste-t-il cohérent ?
13. Le gain d'attendre dépasse-t-il le risque d'attendre ?
14. Avons-nous assez d'informations pour agir maintenant ?
```

Lorsque la réponse à la dernière question devient :

```text
OUI
```

il faut décider.

Le système ne doit pas continuer à analyser simplement parce qu'il est capable de continuer à analyser.

---

# 30. Statut de cette version

Cette version 2.0 formalise la baseline Web validée après simulations :

```text
Claude Web :
composition + recomposition + BOM
version comportementale validée : V2.1

ChatGPT Web :
orchestration + audit contradictoire + audit BOM + marché
version comportementale validée : V2
```

Le workflow obligatoire devient :

```text
architecture
→ consensus
→ BOM
→ audit
→ BOM gelée
→ marché
→ validation finale
```

Claude Code et Codex ne sont pas encore décrits en détail comme agents opérationnels dans ce manuel.

Leur bootstrap et le contrôle contradictoire CLI ont été validés par le benchmark CLI #1 (voir `31-Etat-operationnel.md`) ; leurs rôles et règles de démarrage sont définis par `31-Etat-operationnel.md`, `CLAUDE.md` et `AGENTS.md`.

---

# 31. Stratégie de décision pragmatique

Adoptée après le benchmark CLI #1 (31 octobre 2026), qui a confirmé la qualité du contrôle contradictoire mais révélé un coût excessif en itérations et en interventions humaines.

Ces règles complètent le workflow ; elles ne suppriment ni les critères éliminatoires, ni les contrôles de compatibilité, ni la traçabilité, ni la vérification des données, ni le gel obligatoire de la BOM avant le marché.

## 31.1 Périmètre de l'étude initiale

Limiter l'étude initiale à **deux configurations concrètes**, complètes et comparables.

Une **solution de secours** n'est ajoutée que si elle est nécessaire (par exemple : risque budgétaire, de disponibilité ou d'échec d'un critère éliminatoire).

## 31.2 Audit principal et itérations

Effectuer **un audit Codex principal**.

Une nouvelle itération n'est obligatoire que pour :

- une incompatibilité ;
- une violation d'exigence essentielle ;
- une erreur budgétaire significative ;
- un défaut susceptible de changer le choix.

Les autres remarques sont consignées comme réserves, sans relancer de boucle.

## 31.3 Prix indicatifs avant le gel

Avant le gel de la BOM, des **prix indicatifs** et **relevés commerciaux exploratoires** sont autorisés afin de vérifier la faisabilité économique des configurations.

Restent interdits avant le gel :

- la recherche systématique de promotions et de deals ;
- toute décision d'achat.

Les relevés sont effectués ou transmis par le pilotage (ChatGPT ou utilisateur). Ils sont marqués `PRIX INDICATIF`, datés et sourcés. Ils ne valent ni prix au panier, ni stock, ni `VARIABLE VÉRIFIÉE`, ni engagement.

Les règles propres aux agents restent inchangées : en MODE BOM, Claude ne consulte pas volontairement le marché ; Codex ne lance pas de recherche de deals.

## 31.4 Incertitude résiduelle

Accepter une **incertitude résiduelle explicite** lorsque des données parfaites sont indisponibles.

Une donnée absente reste signalée comme absente. Ne jamais inventer de mesure, et ne pas transformer l'absence de mesure en échec ou en validation.

## 31.5 Corrections sans effet sur la décision

Éviter les corrections purement rédactionnelles ou méthodologiques qui ne changent pas la décision.

Question de contrôle avant toute relance :

> Cette correction peut-elle changer la configuration retenue, sa conformité ou son budget ?

Si non : la noter, ne pas itérer.

## 31.6 Temps humain

Mesurer aussi le **temps humain consacré à l'orchestration** (lecture, copier-coller, réponses aux agents), en plus du temps des agents (voir §14).
