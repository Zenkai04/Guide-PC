---

title: "Dépendances et priorité d'achat"
description: "Criticité structurelle des composants et calcul d'une priorité d'achat dynamique, recalculée à chaque changement de marché."
version: "1.0"
--------------

# Dépendances et priorité d'achat

## 1. Objet

Ce document définit la manière dont le moteur d'acquisition ordonne les achats.

Contrairement à une règle fixe (« le GPU s'achète toujours en premier »), le moteur calcule une priorité d'achat qui évolue avec le marché, car les prix, les stocks et les risques de disponibilité changent en continu.

Toutes les règles générales du guide restent applicables.

---

# 2. Dépendances entre composants

Tous les composants d'une configuration ne sont pas indépendants les uns des autres. Certains imposent des contraintes fortes sur le reste du système.

Exemples :

```text
GPU → dimensions → boîtier
GPU → consommation → alimentation
CPU → socket → carte mère
RAM → QVL / contrôleur mémoire → carte mère + CPU
```

Sécuriser un composant structurant réduit l'incertitude sur plusieurs autres décisions à la fois. À l'inverse, retarder l'achat d'un composant structurant maintient de l'incertitude sur toute une partie de la configuration.

---

# 3. Criticité structurelle

Chaque composant reçoit une criticité structurelle, indépendante de son prix, qui mesure son influence sur le reste du système.

Un GPU, qui contraint le boîtier et l'alimentation, a une criticité structurelle beaucoup plus élevée qu'une webcam, qui ne contraint rien d'autre dans le système.

La criticité structurelle est déterminée à partir :

* du nombre de composants dont la sélection dépend de ce composant (dimensions, alimentation, socket, QVL) ;
* du caractère éliminatoire ou non des contraintes qu'il impose ;
* de sa place dans la hiérarchie du composant directeur (`00-Objet-et-perimetre.md`, section 13).

---

# 4. Priorité d'achat dynamique

## 4.1 Formule

```text
Priorité(c, t) = criticité structurelle(c)
               × rareté(c, t)
               × coût de substitution(c)
               × qualité de l'offre(c, t)
               × facteur de dépendance(c)
              ÷ atténuation par substituabilité(c)
```

Où :

* **criticité structurelle(c)** provient de la section 3 ;
* **rareté(c, t)** dérive de `R_dispo(c, t)` (`23-Disponibilite-et-substituabilite.md`) ;
* **coût de substitution(c)** est `C_sub(c)` (`23-Disponibilite-et-substituabilite.md`) ;
* **qualité de l'offre(c, t)** dérive de la zone de prix actuelle (`22-Temporalite-des-prix.md`) ;
* **facteur de dépendance(c)** augmente lorsque d'autres décisions en attente dépendent du résultat de cet achat ;
* **atténuation par substituabilité(c)** réduit la priorité lorsque `S(c)` est élevée : un composant facilement remplaçable n'a pas besoin d'être sécurisé en urgence.

## 4.2 Lecture

Un composant reçoit une priorité élevée lorsqu'il est structurellement important, difficile à substituer, en risque de rupture, et que son offre actuelle est bonne. Il reçoit une priorité faible lorsqu'il est aisément substituable, peu risqué, ou que son offre actuelle est médiocre.

---

# 5. Un classement recalculé, jamais figé

Le classement d'achat n'est pas fixé une fois pour toutes au début de la campagne. Il est recalculé à chaque scan et à chaque recalcul incrémental ou complet (`28-Configurations-secours-et-checkpoints.md`), parce que les prix et les stocks évoluent en continu.

## 5.1 Exemple

```text
À 00:05
1. écran
2. SSD
3. GPU

À 07:00
1. GPU
2. CPU
3. écran
```

Le classement a changé en quelques heures parce que les prix et les stocks ont changé entre-temps. C'est précisément le comportement recherché : un classement figé serait aveugle à l'état réel du marché.

---

# 6. Interaction avec le risque de configuration incomplète

La priorité d'achat ne doit pas être calculée uniquement composant par composant. Elle doit aussi tenir compte de l'état global de la configuration en cours de sécurisation.

Un composant déjà bien sécurisé (plusieurs alternatives abondantes, prix stable) voit sa priorité redescendre naturellement même s'il reste, en théorie, structurellement critique. À l'inverse, un composant dont toutes les alternatives se raréfient simultanément voit sa priorité augmenter fortement, indépendamment de son prix actuel.

Ce lien avec l'état global de la configuration est détaillé en `27-Budget-immobilise-et-risque-configuration.md`.

---

# 7. Traçabilité

Pour chaque instant de calcul, le rapport d'acquisition conserve :

* le classement de priorité obtenu ;
* la valeur de chacun des cinq facteurs pour chaque composant classé ;
* la comparaison avec le classement précédent, et les composants ayant changé de position ;
* le motif du changement (variation de prix, de stock, de risque, ou de dépendance).

---

# 8. Principe final

L'ordre d'achat n'est pas une règle fixe déterminée par la nature du composant. C'est le résultat d'un calcul qui combine l'importance structurelle du composant, la rareté de son offre, le coût d'un éventuel remplacement et la qualité du prix actuel. Ce calcul doit être refait aussi souvent que le marché change, sous peine de suivre un ordre d'achat qui ne correspond plus à la réalité.
