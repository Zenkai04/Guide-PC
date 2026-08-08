---

title: "Objet et périmètre"
description: "Définition de l'objectif, du domaine d'application et des principes du guide de sélection des composants d'un PC."
version: "1.0"
--------------

# Objet et périmètre

## 1. Objet du guide

Ce guide définit une méthode structurée permettant de sélectionner les composants d’un ordinateur personnel à partir :

* des besoins de l’utilisateur ;
* des usages prévus ;
* des performances attendues ;
* du budget disponible ;
* des contraintes techniques et pratiques ;
* de la durée de conservation visée ;
* de la stratégie d’évolution du système.

L’objectif n’est pas d’identifier le composant le plus performant dans l’absolu.

L’objectif est de sélectionner une configuration qui :

1. remplit la mission définie ;
2. respecte les contraintes obligatoires ;
3. présente un coût justifié par ses gains réels ;
4. reste cohérente au niveau du système complet ;
5. offre des possibilités d’évolution adaptées à sa durée de vie ;
6. limite les remplacements prématurés ;
7. peut être objectivement comparée à d’autres configurations.

---

## 2. Résultat attendu

À partir des données fournies par l’utilisateur, la méthode doit produire :

* une liste d’exigences mesurables ;
* un budget global et une allocation initiale par fonction ;
* l’identification du ou des composants directeurs ;
* une liste de composants compatibles ;
* une liste de composants rejetés avec le motif du rejet ;
* un classement des solutions valides ;
* une vérification des interactions entre composants ;
* une estimation des performances utiles ;
* une évaluation économique ;
* une évaluation de l’évolutivité ;
* une analyse des risques et des incertitudes ;
* une configuration finale ;
* une justification complète de chaque choix.

La sortie ne doit pas se limiter à une liste de références.

Elle doit expliquer pourquoi chaque composant a été retenu et pourquoi les principales alternatives ont été écartées.

---

## 3. Horizon de durée de vie

Le guide doit pouvoir traiter différentes durées de conservation.

Dans le cas de référence, l’objectif est de conserver le système pendant environ dix ans.

Cette durée ne signifie pas nécessairement que tous les composants doivent rester inchangés pendant dix ans.

Elle signifie que l’architecture initiale doit permettre de maintenir un niveau de service satisfaisant pendant cette période grâce à une combinaison de :

* marge de performance initiale ;
* maintenance ;
* remplacement ciblé de certains composants ;
* ajout de capacité ;
* mise à niveau progressive ;
* conservation des composants durables.

Le guide distingue donc :

### 3.1 Durée de vie du système

Période pendant laquelle le PC complet reste utilisable pour sa mission principale.

### 3.2 Durée de vie d’un composant

Période pendant laquelle un composant particulier reste fonctionnel et suffisamment performant.

### 3.3 Durée de support

Période pendant laquelle le composant reçoit encore :

* des mises à jour ;
* des pilotes ;
* des correctifs ;
* une compatibilité logicielle suffisante ;
* un support constructeur ou communautaire raisonnable.

### 3.4 Durée de pertinence

Période pendant laquelle le composant reste adapté à la mission, même s’il fonctionne encore techniquement.

---

## 4. Principe fondamental

Toute décision doit être évaluée par rapport à la mission du système.

Un composant n’est ni bon ni mauvais dans l’absolu.

Il peut être :

* suffisant ;
* insuffisant ;
* surdimensionné ;
* mal adapté ;
* économiquement injustifié ;
* techniquement intéressant mais incompatible ;
* pertinent à court terme mais défavorable à long terme.

La valeur d’un composant dépend du contexte dans lequel il est utilisé.

---

## 5. Ordre de priorité

Les décisions doivent respecter l’ordre suivant :

```text
1. Satisfaction du besoin
2. Respect des critères éliminatoires
3. Compatibilité avec le système
4. Respect du budget maximal
5. Justification du prix
6. Équilibre global de la configuration
7. Évolutivité
8. Optimisations secondaires
```

Une option qui échoue à un niveau supérieur ne peut pas être sauvée par un bon résultat à un niveau inférieur.

Exemple :

Un processeur incompatible avec la carte mère doit être rejeté, même s’il possède un excellent rapport performance-prix.

---

## 6. Séparation des critères

Le guide distingue plusieurs catégories de critères.

### 6.1 Critères éliminatoires

Ils déterminent si une solution est acceptable.

Le résultat est binaire :

```text
Validé
ou
Rejeté
```

Exemples :

* socket incompatible ;
* capacité de mémoire insuffisante ;
* puissance d’alimentation insuffisante ;
* carte graphique trop longue pour le boîtier ;
* connecteur requis absent ;
* performance minimale non atteinte ;
* budget maximal dépassé sans correction possible.

Les critères éliminatoires ne doivent pas être compensés par une note élevée sur d’autres critères.

---

### 6.2 Critères de validation

Ils vérifient que le composant remplit correctement la mission.

Exemples :

* niveau de performance minimal ;
* capacité minimale ;
* nombre minimal de ports ;
* niveau de bruit maximal ;
* température maximale ;
* autonomie ou consommation cible ;
* compatibilité logicielle.

Ils peuvent comporter une marge au-dessus du minimum.

---

### 6.3 Critères d’optimisation

Ils servent à départager plusieurs solutions déjà valides.

Exemples :

* meilleur rapport performance-prix ;
* consommation plus faible ;
* bruit inférieur ;
* garantie plus longue ;
* connectique plus complète ;
* meilleure efficacité thermique ;
* meilleure facilité de maintenance.

Un critère d’optimisation ne doit jamais masquer un échec de validation.

---

### 6.4 Critères d’évolution

Ils évaluent la capacité du système à accepter des changements futurs.

Exemples :

* emplacements mémoire libres ;
* ports M.2 disponibles ;
* lignes PCI Express disponibles ;
* marge de puissance de l’alimentation ;
* dimensions du boîtier ;
* capacité de refroidissement ;
* durée probable de la plateforme ;
* possibilité de remplacer le processeur ;
* compatibilité avec des cartes graphiques plus puissantes.

---

### 6.5 Critères économiques

Ils évaluent si le prix est justifié.

Exemples :

* coût total ;
* coût par unité de performance ;
* coût par gigaoctet ;
* coût par image par seconde ;
* coût par heure gagnée ;
* coût sur la durée de vie ;
* coût du remplacement futur évité ;
* coût énergétique estimé.

---

## 7. Types de données

Le guide distingue obligatoirement les catégories suivantes.

### 7.1 Caractéristiques constructeur

Données déclarées par le fabricant.

Exemples :

* fréquence ;
* capacité ;
* nombre de cœurs ;
* puissance nominale ;
* version d’interface ;
* dimensions ;
* garantie.

Ces données décrivent le produit, mais ne suffisent pas toujours à prévoir son comportement réel.

---

### 7.2 Mesures

Valeurs observées au cours d’un essai.

Exemples :

* temps de rendu ;
* débit réel ;
* latence ;
* consommation électrique ;
* température ;
* bruit ;
* nombre d’images par seconde.

Une mesure doit idéalement préciser :

* le protocole ;
* le matériel utilisé ;
* le logiciel ;
* la version ;
* les paramètres ;
* la température ambiante ;
* la durée de l’essai ;
* l’incertitude éventuelle.

---

### 7.3 Métriques calculées

Valeurs dérivées d’une ou de plusieurs données.

Exemples :

```text
Performance par euro
Performance par watt
Coût par gigaoctet
Latence réelle en nanosecondes
Coût annuel énergétique
Marge de puissance
Marge de capacité
Gain relatif
Surcoût relatif
```

Une métrique doit toujours conserver le lien avec les données ayant servi à son calcul.

---

### 7.4 Vérifications

Contrôles logiques ou techniques.

Exemples :

```text
Socket CPU = socket carte mère
Type de RAM supporté
Longueur GPU ≤ longueur maximale du boîtier
Hauteur du ventirad ≤ hauteur disponible
Puissance PSU ≥ puissance requise avec marge
Connecteurs PSU compatibles avec le GPU
```

Le résultat est généralement :

```text
Validé
Non validé
Inconnu
```

---

### 7.5 Estimations

Valeurs obtenues par approximation.

Exemples :

* consommation annuelle ;
* durée probable avant mise à niveau ;
* niveau de performance futur ;
* coût futur d’une extension.

Une estimation doit être clairement identifiée comme telle.

---

### 7.6 Hypothèses

Informations utilisées dans le raisonnement sans être garanties.

Exemples :

* maintien d’un socket pendant plusieurs générations ;
* évolution future des besoins logiciels ;
* baisse du prix d’un composant ;
* disponibilité future d’une pièce compatible ;
* progression des performances nécessaires.

Une hypothèse ne doit jamais être présentée comme un fait.

---

## 8. Niveaux de confiance

Chaque information importante doit pouvoir recevoir un niveau de confiance.

### Niveau A — Vérifié

Information confirmée par une source directe, une documentation officielle ou une mesure reproductible.

### Niveau B — Fortement probable

Information soutenue par plusieurs sources cohérentes ou par un comportement technique bien établi.

### Niveau C — Estimé

Information obtenue par calcul, extrapolation ou comparaison indirecte.

### Niveau D — Hypothétique

Information dépendant d’un événement futur ou d’une décision non confirmée.

Les critères éliminatoires doivent, autant que possible, reposer sur des informations de niveau A ou B.

---

## 9. Seuils de gain

Pour évaluer le caractère significatif d’une amélioration, le guide utilise les seuils indicatifs suivants :

|                 Gain mesuré | Interprétation initiale                                                              |
| --------------------------: | ------------------------------------------------------------------------------------ |
|            Inférieur à 10 % | Gain généralement insuffisant pour justifier un remplacement ou un fort surcoût      |
|            Entre 10 et 20 % | Gain à analyser selon le prix, la mission et la durée de vie                         |
|            Entre 20 et 40 % | Gain significatif pouvant justifier un surcoût                                       |
| Supérieur ou proche de 40 % | Évolution majeure, généralement pertinente si les autres contraintes sont respectées |

Ces seuils ne doivent pas être appliqués mécaniquement.

Un gain de 8 % peut être important lorsqu’il permet de respecter une contrainte critique.

Un gain de 30 % peut être inutile s’il concerne une charge absente de la mission.

---

## 10. Performance utile

La performance utile est la performance réellement exploitable dans les usages définis.

Elle s’oppose à la performance théorique ou à la performance mesurée dans une charge non représentative.

Une mesure n’est considérée comme pertinente que si elle correspond :

* au logiciel utilisé ;
* à une charge similaire ;
* à la résolution prévue ;
* à un niveau de qualité comparable ;
* à une durée de charge représentative ;
* à une configuration suffisamment proche.

Le guide doit privilégier les mesures directement liées à la mission.

---

## 11. Justification du prix

Le composant le moins cher n’est pas automatiquement le meilleur choix.

Le composant le plus performant ne l’est pas davantage.

Le prix est considéré comme justifié lorsque le surcoût procure au moins l’un des bénéfices suivants :

* performance utile significativement supérieure ;
* capacité nécessaire ;
* suppression d’un goulot d’étranglement ;
* réduction importante du bruit ;
* baisse mesurable de la consommation ;
* amélioration de la fiabilité ;
* durée d’utilisation plus longue ;
* possibilité d’éviter un remplacement futur ;
* meilleure évolutivité ;
* fonctionnalité indispensable.

Le prix n’est pas considéré comme justifié lorsque le surcoût repose principalement sur :

* une caractéristique inutilisée ;
* une amélioration inférieure au seuil utile ;
* une spécification marketing sans effet mesuré ;
* une marge disproportionnée ;
* une hypothèse future trop incertaine ;
* un prestige de gamme ou de marque sans avantage technique démontré.

---

## 12. Évolutivité et anticipation

L’évolutivité doit être évaluée comme une possibilité réelle, et non comme une promesse abstraite.

Une possibilité d’évolution est pertinente seulement si elle est :

* techniquement compatible ;
* économiquement raisonnable ;
* susceptible d’être utilisée ;
* disponible pendant la période concernée ;
* cohérente avec la mission future probable.

Le guide doit éviter de payer une prime excessive pour une évolutivité hypothétique.

L’évolutivité doit être distinguée du surdimensionnement.

### Évolutivité

Capacité à ajouter ou remplacer ultérieurement une ressource.

### Surdimensionnement

Achat immédiat d’une ressource largement supérieure au besoin actuel.

Le surdimensionnement n’est justifié que s’il est plus rentable ou plus fiable qu’une mise à niveau future.

---

## 13. Composant directeur

Le composant directeur est celui qui influence le plus fortement la capacité du système à remplir sa mission.

Il varie selon les usages.

Exemples :

| Mission principale                | Composant ou ressource directrice     |
| --------------------------------- | ------------------------------------- |
| Jeu en haute résolution           | GPU                                   |
| Jeu compétitif à fréquence élevée | CPU et GPU                            |
| Compilation importante            | CPU                                   |
| Rendu 3D GPU                      | GPU et VRAM                           |
| Rendu 3D CPU                      | CPU                                   |
| Intelligence artificielle locale  | GPU, VRAM et compatibilité logicielle |
| Virtualisation                    | CPU, RAM et stockage                  |
| Montage vidéo                     | CPU, GPU, RAM et stockage             |
| Serveur de fichiers               | Stockage, réseau et fiabilité         |
| Usage bureautique                 | Coût global, ergonomie et sobriété    |

Le processus de sélection doit commencer par le composant directeur ou par le sous-système qui impose les contraintes les plus fortes.

---

## 14. Cohérence globale

Une configuration ne doit pas être évaluée comme une simple somme de composants.

La méthode doit vérifier les interactions suivantes :

* CPU et GPU ;
* CPU et mémoire ;
* CPU et carte mère ;
* GPU et alimentation ;
* GPU et boîtier ;
* carte mère et stockage ;
* refroidissement et boîtier ;
* consommation et ventilation ;
* résolution d’affichage et capacité graphique ;
* nombre de périphériques et connectique ;
* plateforme et stratégie d’évolution.

Une configuration peut être rejetée même si tous ses composants sont individuellement valides.

---

## 15. Budget

Le budget doit être traité comme une ressource globale.

Il doit inclure, selon le périmètre défini :

* composants internes ;
* refroidissement ;
* boîtier ;
* système d’exploitation ;
* écrans ;
* périphériques ;
* câbles ou adaptateurs ;
* montage ;
* transport ;
* extensions prévues ;
* marge de sécurité.

Le budget ne doit pas être réparti uniformément.

Il doit être dirigé vers les composants qui apportent le plus de valeur à la mission.

---

## 16. Budget minimal, cible et maximal

Trois valeurs doivent être distinguées.

### Budget minimal viable

Montant minimal permettant de remplir la mission sans violation des contraintes.

### Budget cible

Montant offrant le meilleur compromis entre performance, coût et durée de vie.

### Budget maximal

Limite absolue qui ne peut être dépassée sans modification explicite du besoin.

Cette distinction permet d’éviter de consommer automatiquement tout le budget disponible.

---

## 17. Décision multicritère

La décision ne doit pas reposer uniquement sur un score global.

Chaque solution doit recevoir plusieurs évaluations indépendantes :

* adéquation à la mission ;
* performance utile ;
* coût ;
* efficacité énergétique ;
* bruit ;
* fiabilité ;
* compatibilité ;
* évolutivité ;
* maintenabilité ;
* niveau de confiance.

Un score global peut être calculé pour faciliter le classement, mais il ne doit jamais masquer les résultats détaillés.

---

## 18. Règle de rejet avant notation

Le processus doit toujours respecter l’ordre suivant :

```text
1. Vérifications éliminatoires
2. Validation de la mission
3. Vérification de compatibilité
4. Vérification du budget
5. Calcul des métriques
6. Notation multicritère
7. Classement
8. Justification
```

Une solution rejetée ne doit pas recevoir de note de classement.

---

## 19. Traçabilité de la décision

Toute décision doit pouvoir être retracée.

Pour chaque composant retenu, le rapport doit indiquer :

* les besoins auxquels il répond ;
* les critères obligatoires validés ;
* les mesures utilisées ;
* les métriques calculées ;
* les alternatives comparées ;
* les motifs de rejet des alternatives ;
* les hypothèses retenues ;
* les incertitudes restantes ;
* le surcoût éventuel ;
* les bénéfices justifiant ce surcoût.

---

## 20. Domaine d’application

Le guide s’applique principalement à la conception ou à l’évolution de :

* PC de bureau ;
* stations de travail ;
* PC de jeu ;
* machines de développement ;
* stations de création ;
* systèmes de calcul personnel ;
* configurations polyvalentes.

Il peut également être adapté à certains serveurs personnels ou systèmes spécialisés.

---

## 21. Limites

Le guide ne garantit pas :

* l’absence totale de panne ;
* la disponibilité future des composants ;
* la stabilité des prix ;
* la durée exacte de support d’une plateforme ;
* les besoins logiciels à dix ans ;
* la compatibilité avec des technologies non encore définies.

Son rôle est de réduire l’incertitude et de rendre les décisions explicables, non de prédire parfaitement l’avenir.

---

## 22. Principe final

La configuration retenue doit être la solution la moins coûteuse qui satisfait correctement la mission et les contraintes, sauf lorsqu’un surcoût mesurable est justifié par :

* un gain utile ;
* une meilleure durée de vie ;
* une réduction des risques ;
* une amélioration de l’évolutivité ;
* une diminution du coût total de possession.

La décision finale doit toujours pouvoir être formulée ainsi :

> Ce composant a été retenu parce qu’il satisfait les exigences obligatoires, apporte un bénéfice mesurable dans les usages définis, présente un coût proportionné à ce bénéfice et s’intègre dans une architecture cohérente avec la durée de vie et la stratégie d’évolution du système.

---

## 23. Extension : le moteur d’acquisition

Les sections précédentes définissent un moteur qui répond à une première question :

> Quelle configuration constitue le meilleur choix ?

Ce moteur reste inchangé. Il détermine toujours **quoi** acheter, selon la chaîne :

```text
Besoin → mission → contraintes → critères éliminatoires → candidats
→ compatibilités → dimensionnement → mesures → interactions
→ budget → notation → Pareto → configurations candidates
→ rapport de décision
```

Le guide répond désormais également à une seconde question :

> Sachant ce que nous voulons acheter, quand faut-il effectivement déclencher l’achat ?

Cette seconde question est traitée par un moteur d’acquisition, qui s’exécute après le moteur de composition, en boucle, jusqu’à ce que tous les achats soient sécurisés :

```text
Moteur de conception → configurations candidates → moteur d’exécution du marché → achats
```

Le guide comporte donc trois moteurs successifs :

1. **Moteur d’ingénierie** — de quoi ai-je réellement besoin ? (documents `01` à `03`)
2. **Moteur de composition** — quelle combinaison de composants répond le mieux à ce besoin ? (documents `04` à `20`)
3. **Moteur d’acquisition** — quand et chez qui dois-je acheter chaque composant pour obtenir cette configuration avec un coût et un risque acceptables ? (documents `21` à `29`)

Ce troisième moteur est décrit à partir de `21-Moteur-dacquisition.md`. Il ne modifie et ne remplace aucune règle définie dans les documents `01` à `20` ; il en exploite le résultat pour arbitrer entre le risque de payer trop cher en achetant trop tôt et le risque de perdre l’accès à une solution acceptable en attendant trop longtemps.
