# Notation et classement

## 1. Objet

Ce document définit la méthode permettant d'évaluer, comparer et classer plusieurs configurations.

L'objectif n'est pas uniquement d'attribuer une note.

L'objectif est de produire une décision argumentée, reproductible et adaptée à la mission.

Toutes les règles générales du guide restent applicables.

---

# 2. Philosophie

Le moteur ne cherche pas :

* le composant le plus performant ;
* la configuration la plus chère ;
* la configuration ayant le plus grand nombre de points.

Le moteur cherche la configuration présentant le meilleur compromis pour la mission étudiée.

La notation est donc toujours relative au contexte.

---

# 3. Étapes de l'évaluation

Chaque configuration suit les étapes suivantes :

Validation

↓

Analyse des contraintes

↓

Calcul des métriques

↓

Calcul des scores

↓

Pondération

↓

Classement

↓

Justification

↓

Rapport final

Une configuration qui échoue à une étape éliminatoire n'est pas notée.

---

# 4. Validation préalable

Avant toute notation, le moteur vérifie :

* compatibilité ;
* respect des contraintes ;
* sécurité ;
* faisabilité ;
* mission réalisable.

Toute configuration invalide est rejetée.

---

# 5. Familles de scores

Le moteur calcule plusieurs scores indépendants.

## Score technique

Évalue notamment :

* performances utiles ;
* cohérence ;
* compatibilité.

---

## Score économique

Évalue :

* coût initial ;
* coût total de possession ;
* rendement marginal ;
* coût d'évolution.

---

## Score énergétique

Évalue :

* consommation ;
* rendement ;
* efficacité énergétique.

---

## Score thermique

Évalue :

* stabilité thermique ;
* marges de refroidissement ;
* bruit.

---

## Score d'évolutivité

Évalue :

* possibilités d'évolution ;
* modularité ;
* durée de vie.

---

## Score de robustesse

Évalue :

* tolérance aux évolutions ;
* marges ;
* risques.

---

## Score de maintenabilité

Évalue :

* facilité de remplacement ;
* disponibilité des pièces ;
* simplicité de maintenance.

---

## Score ergonomique

Évalue :

* confort ;
* bruit ;
* expérience utilisateur.

---

# 6. Pondération

Chaque score est pondéré selon :

* la mission ;
* les priorités utilisateur ;
* les contraintes.

Une pondération n'est jamais fixe.

Elle dépend toujours du contexte.

---

# 7. Normalisation

Les métriques sont converties dans une échelle commune avant comparaison.

Le moteur précise :

* méthode de normalisation ;
* valeurs de référence ;
* limites d'application.

Toutes les transformations doivent être traçables.

---

# 8. Classement

Le classement est obtenu à partir :

* des scores ;
* des pondérations ;
* des critères éliminatoires.

Deux configurations peuvent obtenir un score global proche tout en présentant des profils très différents.

Le rapport doit conserver cette information.

---

# 9. Analyse de sensibilité

Le moteur évalue notamment :

* impact d'une variation du budget ;
* impact d'un changement de mission ;
* impact d'une évolution matérielle ;
* impact des hypothèses.

Cette analyse mesure la stabilité de la décision.

---

# 10. Niveau de confiance

Le moteur attribue un niveau de confiance selon :

* la qualité des données ;
* le nombre de mesures disponibles ;
* les hypothèses ;
* la fraîcheur des informations.

Exemple :

Niveau A : données complètes et mesurées.

Niveau B : données principalement mesurées.

Niveau C : données partielles.

Niveau D : nombreuses estimations.

---

# 11. Justification automatique

Chaque décision doit pouvoir être expliquée.

Le rapport indique notamment :

* pourquoi la configuration est retenue ;
* quels critères ont été déterminants ;
* quels compromis ont été réalisés ;
* quels risques subsistent.

---

# 12. Comparaison de configurations

Pour chaque paire de configurations, le moteur identifie :

* les avantages ;
* les inconvénients ;
* les différences significatives ;
* les domaines où chaque configuration est supérieure.

Une configuration n'est jamais déclarée "meilleure" sans préciser le contexte.

---

# 13. Gestion des ex æquo

En cas de scores proches, le moteur privilégie successivement :

1. la meilleure adéquation à la mission ;
2. la plus faible incertitude ;
3. le coût total de possession le plus faible ;
4. la meilleure évolutivité ;
5. la meilleure robustesse.

---

# 14. Rapport de classement

Le rapport final doit présenter :

* les scores détaillés ;
* les pondérations utilisées ;
* les métriques principales ;
* les hypothèses ;
* le niveau de confiance ;
* la justification de chaque classement.

Toutes les décisions doivent être entièrement traçables et reproductibles.

---

# 15. Principe final

Le classement constitue une aide à la décision.

Il ne remplace jamais le jugement de l'utilisateur.

Le moteur fournit une recommandation argumentée fondée sur des mesures, des métriques, des contraintes et des priorités explicites.

Toute recommandation doit pouvoir être auditée, reproduite et remise en question si les données d'entrée évoluent.
