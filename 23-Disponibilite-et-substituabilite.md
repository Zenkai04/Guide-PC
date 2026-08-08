---

title: "Disponibilité et substituabilité"
description: "Évaluation du risque de disponibilité au niveau système, de la substituabilité des candidats et du coût de substitution."
version: "1.0"
--------------

# Disponibilité et substituabilité

## 1. Objet

Ce document définit la manière dont le moteur d'acquisition évalue le risque de perdre l'accès à une solution acceptable, et la facilité avec laquelle un composant indisponible peut être remplacé.

Ces deux notions sont distinctes et complémentaires :

* le **risque de disponibilité** mesure la probabilité qu'une solution acceptable devienne inaccessible ;
* la **substituabilité** mesure le coût réel d'une telle disparition.

Toutes les règles générales du guide restent applicables.

---

# 2. Risque de disponibilité

## 2.1 Définition

Pour toute référence candidate `c`, à l'instant `t`, le moteur évalue :

```text
R_dispo(c, t)
```

Le risque est exprimé selon quatre niveaux :

* faible ;
* moyen ;
* élevé ;
* critique.

## 2.2 Indices exploitables

Le risque de disponibilité est estimé à partir d'indices convergents, notamment :

* état du stock ;
* nombre de vendeurs disposant du produit ;
* disparition récente chez certains vendeurs ;
* délai de livraison annoncé ;
* fréquence des réapprovisionnements observés ;
* caractère très demandé de la référence ;
* proximité d'un évènement commercial à forte demande (Black Friday, soldes) ;
* éventuelle mention de stock limité.

## 2.3 Garde-fou contre les indices non fiables

Une simple mention commerciale du type « plus que 2 en stock ! » ne doit jamais, à elle seule, être considérée comme une preuve fiable de rupture imminente. Ce type de mention est fréquemment utilisé comme levier commercial indépendamment du stock réel.

Un indice de disponibilité n'est retenu que s'il est corroboré par au moins un second indice indépendant (par exemple : disparition effective chez un autre vendeur, augmentation du délai de livraison, absence de réapprovisionnement sur plusieurs scans successifs).

Cette règle est développée en tant que garde-fou général en `29-Algorithme-acquisition-marche.md`, section « règle anti-FOMO ».

---

# 3. Le risque se mesure au niveau du système, jamais sur une référence isolée

C'est un raffinement essentiel : le moteur ne doit jamais évaluer la disponibilité d'une référence indépendamment des autres candidats validés pour la même fonction.

Ce qui intéresse réellement le moteur est :

> la probabilité de perdre l'accès à une solution acceptable, et non la probabilité qu'une référence précise disparaisse.

## 3.1 Exemple — risque système faible

Trois cartes graphiques ont été validées pour la même fonction :

* ASUS TUF RTX 5080 ;
* MSI Gaming Trio RTX 5080 ;
* Gigabyte Gaming OC RTX 5080.

Si la TUF commence à disparaître mais que les deux autres restent abondantes à des prix similaires, le risque système reste faible : une solution acceptable demeure accessible.

## 3.2 Exemple — risque système élevé

Si les trois références commencent simultanément à se raréfier, le risque système devient élevé, quand bien même chacune, prise isolément, ne serait qu'en risque « moyen ».

## 3.3 Conséquence

Le risque de disponibilité utilisé dans la décision d'achat (`24-Regret-et-valeur-attente.md`, `29-Algorithme-acquisition-marche.md`) est calculé sur l'ensemble des candidats validés pour une même fonction, et non sur la seule référence actuellement la mieux classée.

---

# 4. Substituabilité

## 4.1 Définition

```text
S(c) = facilité avec laquelle le composant c peut être remplacé par un candidat équivalent
```

La substituabilité est une variable différente du risque de disponibilité : une référence peut être très recherchée (risque élevé) tout en étant hautement substituable (remplacement sans conséquence notable), ou inversement.

## 4.2 Exemple — substituabilité élevée

Samsung 990 Pro indisponible → WD SN850X disponible à caractéristiques et prix comparables.

Faible conséquence. Substituabilité élevée.

## 4.3 Exemple — substituabilité faible

ASUS TUF RTX 5080 à 1 180 € indisponible → les seules alternatives restantes sont nettement plus chères ou moins satisfaisantes.

Conséquence importante. Substituabilité faible.

## 4.4 Effet sur la décision

Cette variable change complètement la lecture d'une même situation de stock. Une rupture sur un composant à substituabilité élevée est un non-évènement pour la décision. Une rupture sur un composant à substituabilité faible est un évènement critique.

---

# 5. Coût de substitution

## 5.1 Définition

La substituabilité n'est pas seulement binaire (oui/non). Le moteur calcule un coût :

```text
C_sub(c) = coût engendré par la disparition du candidat actuel
         = prix de la meilleure alternative acceptable − prix du candidat actuel
```

Le coût de substitution peut inclure, lorsque les données sont disponibles, un écart qualitatif converti en équivalent monétaire (perte de score, perte de fonctionnalité), en plus de l'écart de prix.

## 5.2 Exemple — coût de substitution faible

TUF = 1 199 € ; meilleure alternative acceptable = 1 229 € → `C_sub` = 30 €.

Une disparition de la TUF n'est pas très inquiétante.

## 5.3 Exemple — coût de substitution élevé

TUF = 1 199 € ; alternative = 1 399 € → `C_sub` = 200 €.

Attendre devient beaucoup plus dangereux : le coût d'un pari perdu (attendre puis devoir se rabattre sur l'alternative) est significatif.

## 5.4 Utilisation

`C_sub(c)` est l'une des entrées directes du calcul du regret d'attente (`24-Regret-et-valeur-attente.md`) et de la priorité d'achat dynamique (`25-Dependances-et-priorite-achat.md`).

---

# 6. Combinaison des deux variables

| Substituabilité | Risque de disponibilité | Lecture |
| ---------------- | ------------------------ | ------- |
| Élevée | Faible ou moyen | Situation confortable. Attendre est peu risqué. |
| Élevée | Élevé ou critique | Rupture probable mais peu coûteuse. Attendre reste acceptable. |
| Faible | Faible ou moyen | Peu de risque immédiat, mais surveillance renforcée recommandée. |
| Faible | Élevé ou critique | Situation critique. Le coût d'un pari perdu est élevé et sa probabilité n'est pas négligeable. |

Cette combinaison alimente directement le calcul de la valeur de l'attente décrit en `24-Regret-et-valeur-attente.md`.

---

# 7. Traçabilité

Pour chaque référence candidate, le rapport d'acquisition doit conserver :

* le niveau de `R_dispo` retenu et les indices l'ayant motivé ;
* la liste des candidats considérés pour l'évaluation du risque système ;
* la valeur de `S(c)` et sa justification ;
* le calcul de `C_sub(c)` et l'alternative retenue pour ce calcul.

---

# 8. Principe final

Le risque qui compte n'est jamais celui d'une référence isolée, mais celui de perdre l'accès à une solution acceptable pour une fonction donnée. La substituabilité détermine si ce risque a un coût négligeable ou significatif. Une décision d'achat fondée uniquement sur l'état de stock d'une seule référence, sans tenir compte de ses alternatives, est une décision mal informée.
