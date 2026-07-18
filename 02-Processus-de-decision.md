# Processus de décision

## 1. Objet

Ce document décrit le processus complet permettant de transformer un besoin utilisateur en une configuration informatique objectivement justifiée.

Il définit uniquement l'ordre des opérations.

Les règles spécifiques aux composants sont définies dans leurs documents respectifs.

Le processus est identique quelle que soit la mission.

Seules les données d'entrée et les critères de décision changent.

---

# 2. Principe général

Le moteur de décision applique toujours les étapes suivantes.

```text
Collecte des données

↓

Validation des données

↓

Analyse de la mission

↓

Extraction des exigences

↓

Classification des contraintes

↓

Détermination du composant directeur

↓

Détermination du budget exploitable

↓

Sélection progressive des composants

↓

Vérification des interactions

↓

Calcul des métriques

↓

Notation multicritère

↓

Classement

↓

Rapport de décision
```

Chaque étape doit être validée avant de passer à la suivante.

---

# 3. Étape 1 — Collecte des données

Entrée :

Toutes les données définies dans `01-Donnees-entree.md`.

Objectif :

Construire une représentation complète des besoins.

Sortie :

Dossier utilisateur normalisé.

Aucune décision n'est prise à cette étape.

---

# 4. Étape 2 — Validation des données

Objectif :

Détecter les données manquantes ou incohérentes.

Exemples :

* budget négatif ;
* résolution absente pour une machine de jeu ;
* durée de vie non définie ;
* budget inférieur au minimum viable ;
* contraintes incompatibles entre elles.

Résultat :

* Validé
* À compléter
* Incohérent

Le processus est interrompu tant que cette étape n'est pas validée.

---

# 5. Étape 3 — Analyse de la mission

Objectif :

Transformer les besoins utilisateur en besoins techniques.

Exemple :

Entrée :

"Je veux jouer en 4K à 120 FPS."

Exigences produites :

* forte charge GPU ;
* besoin élevé en VRAM ;
* écran compatible ;
* débit vidéo élevé ;
* alimentation adaptée.

La mission est traduite en exigences mesurables.

---

# 6. Étape 4 — Extraction des exigences

Les exigences sont classées en quatre catégories.

## 6.1 Exigences fonctionnelles

Définissent ce que le système doit accomplir.

Exemple :

* compiler un projet ;
* exécuter un jeu ;
* entraîner un modèle IA.

---

## 6.2 Exigences de performance

Définissent un niveau minimal.

Exemple :

* 120 FPS ;
* moins de 10 minutes de rendu ;
* moins de 30 secondes de compilation.

---

## 6.3 Exigences de qualité

Exemple :

* bruit maximal ;
* consommation maximale ;
* stabilité ;
* température.

---

## 6.4 Exigences d'évolution

Exemple :

* ajout futur de RAM ;
* remplacement du GPU ;
* conservation du boîtier.

---

# 7. Étape 5 — Classification des contraintes

Toutes les contraintes sont classées.

## Contraintes absolues

Leur non-respect entraîne un rejet.

Exemples :

* budget maximal ;
* dimensions ;
* compatibilité.

---

## Contraintes fortes

Leur non-respect est exceptionnel.

Exemple :

* bruit maximal.

---

## Contraintes préférentielles

Servent au classement.

Exemple :

* préférence de marque ;
* couleur ;
* RGB.

---

# 8. Étape 6 — Détermination du composant directeur

Le moteur identifie le composant ayant l'impact principal sur la mission.

Exemples :

Jeu 4K

↓

GPU

---

Compilation

↓

CPU

---

Serveur NAS

↓

Stockage

---

IA locale

↓

GPU + VRAM

---

Virtualisation

↓

CPU + RAM

Le composant directeur est sélectionné en premier.

---

# 9. Étape 7 — Détermination du budget exploitable

Le budget est réparti selon la mission.

Exemple :

Gaming :

GPU > CPU > Carte mère > RAM > SSD

Serveur :

Stockage > Fiabilité > CPU

Le budget n'est jamais réparti uniformément.

---

# 10. Étape 8 — Sélection d'un composant

Chaque composant suit exactement le même algorithme.

```text
Caractéristiques

↓

Critères éliminatoires

↓

Vérifications

↓

Mesures

↓

Métriques

↓

Notation

↓

Classement
```

Chaque composant possède son propre document définissant ces éléments.

---

# 11. Étape 9 — Critères éliminatoires

Avant toute comparaison, les critères éliminatoires sont évalués.

Exemples :

* incompatibilité physique ;
* performances insuffisantes ;
* consommation excessive ;
* budget dépassé.

Une solution rejetée ne poursuit pas le processus.

---

# 12. Étape 10 — Vérifications

Les vérifications contrôlent la cohérence technique.

Exemples :

* socket compatible ;
* type de RAM ;
* lignes PCIe suffisantes ;
* connecteurs présents ;
* alimentation suffisante ;
* dimensions compatibles.

Résultat :

* Validé
* Rejeté
* Inconnu

---

# 13. Étape 11 — Mesures

Les performances sont évaluées à partir de mesures.

Le moteur privilégie les mesures représentatives de la mission.

Exemples :

Compilation.

FPS.

Temps Blender.

Débit SSD.

Température.

Consommation.

Bruit.

Les caractéristiques constructeur ne remplacent jamais les mesures lorsque celles-ci existent.

---

# 14. Étape 12 — Calcul des métriques

Les mesures sont transformées en indicateurs.

Exemples :

Performance/€

Performance/W

FPS/€

Coût annuel

Latence réelle

Indice d'évolutivité

Indice de maintenance

Les métriques permettent de comparer objectivement plusieurs solutions.

---

# 15. Étape 13 — Notation multicritère

Les solutions encore valides sont évaluées.

Chaque critère reçoit une note indépendante.

Exemple :

Mission

Compatibilité

Performance

Consommation

Bruit

Fiabilité

Prix

Évolutivité

Maintenance

Le moteur ne doit pas utiliser une note unique sans justification.

---

# 16. Étape 14 — Classement

Les solutions sont classées.

Le classement dépend :

* de la mission ;
* des priorités utilisateur ;
* des pondérations définies ;
* des contraintes.

Deux utilisateurs peuvent obtenir un classement différent avec le même matériel.

---

# 17. Étape 15 — Vérification globale

Une fois tous les composants sélectionnés, le moteur vérifie le système complet.

Exemples :

* alimentation suffisante ;
* refroidissement suffisant ;
* consommation totale ;
* dimensions ;
* bruit estimé ;
* connectique ;
* compatibilité logicielle ;
* marges d'évolution.

Une incompatibilité globale peut entraîner le remplacement d'un composant précédemment sélectionné.

---

# 18. Étape 16 — Optimisation

Le moteur recherche des améliorations sans modifier la mission.

Exemples :

* coût inférieur ;
* bruit réduit ;
* consommation plus faible ;
* meilleure évolutivité.

Une optimisation ne doit jamais dégrader une exigence obligatoire.

---

# 19. Étape 17 — Rapport de décision

Le moteur génère un rapport expliquant chaque choix.

Pour chaque composant retenu, le rapport indique :

* les besoins couverts ;
* les critères validés ;
* les mesures utilisées ;
* les métriques calculées ;
* les alternatives étudiées ;
* les motifs de rejet ;
* les hypothèses ;
* les incertitudes ;
* les avantages ;
* les limites.

Le rapport doit permettre à un tiers de reproduire le raisonnement.

---

# 20. Boucle d'itération

Le processus est itératif.

Une modification de :

* la mission ;
* du budget ;
* d'une contrainte ;
* d'une priorité ;

entraîne un nouveau calcul uniquement des étapes impactées.

Le moteur doit éviter de recalculer les parties inchangées.

---

# 21. Traçabilité

Chaque décision doit pouvoir être reliée à :

* une donnée d'entrée ;
* une règle ;
* une mesure ;
* une métrique ;
* une justification.

Aucune décision ne doit reposer uniquement sur une préférence implicite ou une opinion non argumentée.

---

# 22. Principe fondamental

Le moteur ne cherche pas le meilleur composant.

Il cherche la meilleure solution répondant à une mission donnée.

Une configuration est considérée optimale lorsqu'aucune autre configuration ne fournit un meilleur compromis entre :

* satisfaction des exigences ;
* coût ;
* performances utiles ;
* compatibilité ;
* évolutivité ;
* fiabilité ;
* consommation ;
* maintenabilité.

Toute décision doit être objectivement justifiable à partir des données disponibles.
