# Budget et allocation

## 1. Objet

Ce document définit la méthode permettant de transformer un budget global en une allocation cohérente des ressources financières nécessaires à la conception d'une configuration informatique.

Le budget est considéré comme une ressource limitée.

Il doit être distribué de manière à maximiser la valeur créée pour la mission tout en respectant les contraintes définies par l'utilisateur.

Le budget n'est jamais réparti de manière arbitraire ou uniforme.

---

# 2. Principes fondamentaux

L'allocation du budget repose sur les principes suivants.

## Principe 1 — Le budget est une contrainte

Le budget constitue une limite maximale.

Il ne s'agit pas d'un objectif de dépense.

Le moteur doit rechercher la solution satisfaisant la mission avec le coût total le plus faible.

---

## Principe 2 — Toute dépense doit créer une valeur mesurable

Chaque euro investi doit produire un bénéfice identifiable.

Les bénéfices peuvent être :

* une augmentation des performances utiles ;
* une amélioration de la fiabilité ;
* une réduction de la consommation ;
* une diminution du bruit ;
* une meilleure évolutivité ;
* une amélioration de la maintenabilité ;
* une réduction du coût futur.

Une dépense sans bénéfice mesurable n'est pas justifiée.

---

## Principe 3 — La mission dirige l'allocation

Le budget est distribué en fonction de la contribution de chaque composant à la mission.

Le composant directeur reçoit naturellement une part plus importante du budget lorsque son influence sur la mission est dominante.

---

## Principe 4 — Les composants ne sont pas indépendants

Une augmentation du budget d'un composant peut imposer des dépenses supplémentaires sur d'autres composants.

Exemples :

* carte graphique plus puissante → alimentation plus puissante ;
* processeur plus performant → refroidissement plus performant ;
* SSD supplémentaire → carte mère avec davantage d'emplacements.

L'allocation doit être évaluée au niveau du système.

---

# 3. Décomposition du budget

Le budget global est réparti entre plusieurs catégories.

## Budget matériel

Inclut :

* processeur ;
* carte mère ;
* mémoire ;
* carte graphique ;
* stockage ;
* alimentation ;
* refroidissement ;
* boîtier.

---

## Budget logiciel

Inclut éventuellement :

* système d'exploitation ;
* licences ;
* logiciels indispensables.

---

## Budget affichage

Inclut :

* écrans ;
* supports ;
* câbles vidéo.

---

## Budget périphériques

Inclut :

* clavier ;
* souris ;
* casque ;
* webcam ;
* microphone.

---

## Budget exploitation

Inclut :

* consommation électrique estimée ;
* maintenance ;
* remplacements prévus.

---

# 4. Budgets de référence

Le moteur distingue trois niveaux.

## Budget minimal viable

Montant permettant de satisfaire la mission sans marge importante.

---

## Budget cible

Montant offrant le meilleur compromis entre coût, performances et durée de vie.

---

## Budget maximal

Montant que le moteur ne doit jamais dépasser.

Le budget maximal ne constitue pas une obligation de dépense.

---

# 5. Coût total de possession

Le coût d'une configuration ne se limite pas à son prix d'achat.

Le moteur doit prendre en compte, lorsque les données sont disponibles :

* prix d'acquisition ;
* consommation électrique ;
* coût des mises à niveau ;
* coût des remplacements ;
* coût de maintenance ;
* durée de vie estimée.

Le coût total de possession (TCO) est défini par :

```text id="fr4vks"
TCO = Achat
    + Exploitation
    + Maintenance
    + Mises à niveau
    - Valeur résiduelle
```

---

# 6. Coût d'opportunité

Toute dépense possède un coût d'opportunité.

Investir davantage sur un composant réduit le budget disponible pour les autres.

Le moteur doit systématiquement analyser :

* le gain obtenu ;
* le coût supplémentaire ;
* les bénéfices perdus sur les autres composants.

---

# 7. Rendement marginal

Le moteur doit rechercher les zones où le rendement marginal devient faible.

Exemple :

Un processeur coûtant 30 % plus cher pour un gain utile de 5 % présente un rendement marginal défavorable.

Le rendement marginal constitue un indicateur essentiel pour détecter les surdimensionnements.

---

# 8. Allocation dynamique

Le budget n'est jamais réparti à l'aide de pourcentages fixes.

Le moteur applique le processus suivant :

```text id="8ajcva"
Mission

↓

Identification du composant directeur

↓

Identification des composants contraints

↓

Estimation des besoins minimaux

↓

Allocation initiale

↓

Simulation de la configuration

↓

Réallocation si nécessaire

↓

Configuration équilibrée
```

L'allocation est donc le résultat d'un calcul et non d'une règle prédéfinie.

---

# 9. Priorité d'investissement

Les dépenses doivent être classées selon leur impact sur la mission.

Ordre général :

1. satisfaire les exigences obligatoires ;
2. supprimer les goulots d'étranglement ;
3. améliorer les performances utiles ;
4. améliorer la fiabilité ;
5. améliorer l'évolutivité ;
6. améliorer le confort.

Ce classement peut varier selon la mission.

---

# 10. Détection du surdimensionnement

Un composant est considéré comme surdimensionné lorsqu'il apporte principalement des performances ou des fonctionnalités qui ne seront pas exploitées.

Le moteur doit identifier :

* les ressources inutilisées ;
* les marges excessives ;
* les fonctionnalités non employées.

Le surdimensionnement n'est acceptable que s'il réduit le coût total de possession ou améliore significativement la durée de vie.

---

# 11. Détection du sous-dimensionnement

Un composant est considéré comme sous-dimensionné lorsqu'il limite la mission ou réduit fortement la durée de vie prévue.

Le moteur doit détecter :

* les performances insuffisantes ;
* les capacités insuffisantes ;
* les marges de sécurité insuffisantes ;
* les risques de remplacement prématuré.

---

# 12. Réserve budgétaire

Lorsque cela est pertinent, une partie du budget peut rester non consommée.

Cette réserve peut être utilisée ultérieurement pour :

* une mise à niveau ;
* une réparation ;
* un changement de composant.

Le moteur ne cherche pas à consommer systématiquement l'intégralité du budget.

---

# 13. Arbitrages

Lorsque le budget est insuffisant, les arbitrages doivent respecter l'ordre suivant :

1. conserver les exigences obligatoires ;
2. réduire les optimisations ;
3. reporter les évolutions futures ;
4. supprimer les éléments de confort ;
5. réviser la mission avec l'utilisateur.

---

# 14. Justification des surcoûts

Tout surcoût doit être justifié.

Les justifications possibles sont notamment :

* gain mesurable ;
* suppression d'un goulot d'étranglement ;
* réduction de consommation ;
* amélioration de la fiabilité ;
* meilleure évolutivité ;
* diminution du coût futur.

Une simple amélioration théorique ne constitue pas une justification suffisante.

---

# 15. Indicateurs économiques

Le moteur peut calculer notamment :

* Performance/€
* FPS/€
* Temps gagné/€
* Performance/W
* Coût annuel
* TCO
* Retour sur investissement estimé
* Rendement marginal
* Coût de la capacité inutilisée
* Coût des performances inutilisées

Ces indicateurs servent uniquement à comparer des solutions valides.

---

# 16. Réévaluation continue

Toute modification :

* du budget ;
* des prix ;
* de la mission ;
* des contraintes ;

entraîne une nouvelle allocation budgétaire.

L'allocation est recalculée avant toute nouvelle sélection de composants.

---

# 17. Traçabilité

Le rapport final doit expliquer :

* comment le budget a été réparti ;
* pourquoi certains composants ont reçu davantage de ressources ;
* quels arbitrages ont été réalisés ;
* quels surcoûts ont été acceptés ;
* quelles économies ont été retenues.

La répartition du budget doit toujours être reproductible et objectivement justifiée.

---

# 18. Principe final

Le meilleur budget n'est pas celui qui est entièrement dépensé.

C'est celui qui maximise la valeur créée pour la mission tout en minimisant le coût total sur la durée de vie prévue du système.

Une allocation est considérée comme optimale lorsqu'aucune redistribution du budget ne permet d'obtenir une amélioration plus importante de la mission sans augmenter le coût total ou dégrader une exigence obligatoire.
