# Algorithme global

## 1. Objet

Ce document décrit le fonctionnement global du moteur de décision.

Il définit l'enchaînement des traitements permettant de transformer un ensemble de besoins, de contraintes et de données techniques en une ou plusieurs recommandations argumentées.

Toutes les règles générales du guide restent applicables.

---

# 2. Philosophie

Le moteur n'effectue pas une recherche exhaustive parmi toutes les configurations possibles.

Il procède par réduction progressive de l'espace des solutions.

À chaque étape, certaines configurations sont éliminées jusqu'à ne conserver que les solutions pertinentes.

L'objectif est d'obtenir une décision cohérente, reproductible et justifiable.

---

# 3. Données d'entrée

Le moteur reçoit notamment :

## Mission

* usages principaux ;
* usages secondaires ;
* priorités.

---

## Contraintes

* budget ;
* consommation ;
* encombrement ;
* bruit ;
* compatibilité ;
* environnement.

---

## Préférences

* évolutivité ;
* marques ;
* réutilisation de composants ;
* préférences ergonomiques.

---

## Données techniques

* composants disponibles ;
* mesures ;
* métriques ;
* caractéristiques.

---

# 4. Pipeline général

Le moteur applique successivement les étapes suivantes :

Collecte des données

↓

Validation des entrées

↓

Analyse de la mission

↓

Extraction des exigences

↓

Classification des contraintes

↓

Identification du composant directeur

↓

Détermination du budget exploitable

↓

Sélection des composants

↓

Analyse des interactions

↓

Calcul des métriques

↓

Notation

↓

Classement

↓

Analyse de sensibilité

↓

Production du rapport final

Chaque étape produit des informations utilisées par les suivantes.

---

# 5. Validation des entrées

Le moteur vérifie notamment :

* cohérence des besoins ;
* contraintes contradictoires ;
* données manquantes ;
* hypothèses nécessaires.

Les incohérences sont signalées avant toute sélection.

---

# 6. Détermination de la stratégie

Le moteur détermine notamment :

* stratégie de durée de vie ;
* stratégie budgétaire ;
* stratégie d'évolution ;
* stratégie énergétique.

Ces stratégies orientent les choix futurs.

---

# 7. Sélection des composants

Chaque famille de composants suit son propre algorithme.

Pour chaque composant :

Validation

↓

Critères éliminatoires

↓

Vérifications

↓

Mesures

↓

Calcul des métriques

↓

Notation

↓

Classement local

Les meilleurs candidats sont conservés.

---

# 8. Construction de la configuration

Les composants retenus sont assemblés progressivement.

Après chaque ajout, le moteur vérifie :

* compatibilité ;
* interactions ;
* contraintes ;
* équilibre global.

Une incompatibilité entraîne le rejet de la combinaison.

---

# 9. Analyse systémique

Une fois la configuration construite, le moteur réalise une analyse globale.

Il identifie notamment :

* goulots d'étranglement ;
* ressources inutilisées ;
* marges disponibles ;
* dépendances critiques ;
* risques.

---

# 10. Calcul des scores

Les scores sont calculés conformément au document "Notation et classement".

Le moteur calcule notamment :

* score technique ;
* score économique ;
* score énergétique ;
* score thermique ;
* score de robustesse ;
* score d'évolutivité ;
* score de maintenabilité ;
* score ergonomique.

---

# 11. Analyse de sensibilité

Le moteur simule différentes évolutions.

Exemples :

* augmentation du budget ;
* réduction du budget ;
* changement de mission ;
* évolution des composants ;
* ajout de nouveaux besoins.

Cette étape évalue la robustesse de la décision.

---

# 12. Sélection finale

Le moteur retient les configurations présentant :

* une validation complète ;
* les meilleurs profils de scores ;
* une cohérence globale ;
* un niveau de confiance suffisant.

Le moteur peut retenir plusieurs solutions lorsqu'elles répondent à des compromis différents.

---

# 13. Niveau de confiance

Le moteur attribue un niveau de confiance en fonction :

* de la qualité des mesures ;
* de la qualité des sources ;
* des hypothèses utilisées ;
* de la stabilité de la décision.

Le niveau de confiance est indépendant du score obtenu.

---

# 14. Traçabilité

Le moteur enregistre notamment :

* les décisions prises ;
* les critères éliminatoires rencontrés ;
* les pondérations utilisées ;
* les métriques calculées ;
* les hypothèses.

Chaque décision doit pouvoir être reproduite.

---

# 15. Performances du moteur

Le moteur privilégie :

* la cohérence ;
* la reproductibilité ;
* la robustesse.

L'optimisation du temps de calcul ne doit jamais dégrader la qualité de la décision.

---

# 16. Évolutivité du moteur

Le moteur doit permettre l'ajout futur :

* de nouveaux composants ;
* de nouvelles métriques ;
* de nouveaux critères ;
* de nouvelles missions.

L'architecture doit rester modulaire.

---

# 17. Principe final

Le moteur ne cherche pas à déterminer la configuration la plus performante.

Il cherche à identifier les configurations les plus adaptées à une mission donnée, en tenant compte des contraintes, des interactions, des risques, du coût total, de la durée de vie et du niveau de confiance des informations utilisées.

Chaque recommandation est le résultat d'un processus d'ingénierie transparent, justifiable et reproductible.
