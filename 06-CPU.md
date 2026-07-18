# CPU

## 1. Objet

Ce document définit les règles de sélection d'un processeur (CPU).

Il décrit :

* son rôle dans le système ;
* les caractéristiques à collecter ;
* les critères éliminatoires ;
* les vérifications de compatibilité ;
* les mesures pertinentes ;
* les métriques calculées ;
* les règles de décision ;
* les interactions avec les autres composants.

Toutes les règles générales restent applicables.

---

# 2. Mission du CPU

Le processeur est le composant chargé d'exécuter les instructions générales du système.

Il orchestre les traitements, coordonne les échanges entre les composants et exécute les tâches qui ne sont pas déléguées à des accélérateurs spécialisés.

Selon la mission du système, il peut devenir :

* le composant directeur ;
* un composant de soutien ;
* ou un composant secondaire.

Le niveau d'investissement dépend donc directement de la mission.

---

# 3. Fonctions assurées

Le CPU intervient notamment dans :

* l'exécution du système d'exploitation ;
* les applications bureautiques ;
* la compilation ;
* les calculs scientifiques ;
* la compression ;
* le chiffrement ;
* la virtualisation ;
* la logique des jeux ;
* la préparation des commandes GPU ;
* certaines tâches d'intelligence artificielle ;
* la gestion des périphériques.

---

# 4. Caractéristiques constructeur

Les caractéristiques suivantes doivent être collectées lorsqu'elles sont disponibles.

## Architecture

* constructeur
* famille
* génération
* microarchitecture
* procédé de fabrication

---

## Calcul

* nombre de cœurs
* type des cœurs
* nombre de threads
* fréquence de base
* fréquence turbo
* fréquence soutenue

---

## Mémoire

* cache L1
* cache L2
* cache L3
* cache total

---

## Contrôleur mémoire

* type de mémoire
* fréquence maximale
* nombre de canaux
* ECC
* capacité maximale

---

## Connectivité

* socket
* lignes PCI Express
* version PCI Express

---

## Fonctionnalités

* iGPU
* virtualisation
* AES
* AVX
* AVX2
* AVX-512
* SMT / HyperThreading
* technologies d'économie d'énergie

---

## Consommation

* TDP officiel
* puissance maximale annoncée
* limites de puissance

---

# 5. Critères éliminatoires

Le CPU est rejeté immédiatement si l'un des critères suivants est rencontré.

## Compatibilité

* socket incompatible
* mémoire incompatible
* instructions indispensables absentes
* virtualisation obligatoire absente
* ECC obligatoire absent

---

## Performances

* performances minimales non atteintes pour la mission
* nombre minimal de cœurs insuffisant
* mémoire adressable insuffisante

---

## Contraintes

* consommation supérieure à la limite imposée
* coût supérieur au budget sans justification
* disponibilité inexistante

Les critères éliminatoires sont évalués avant toute notation.

---

# 6. Vérifications

Les vérifications suivantes doivent être réalisées.

## Compatibilité carte mère

* socket
* BIOS
* chipset
* alimentation CPU

---

## Compatibilité mémoire

* type
* fréquence
* capacité
* nombre de barrettes

---

## Compatibilité refroidissement

* dissipation thermique
* hauteur du refroidisseur
* capacité du système de refroidissement

---

## Compatibilité alimentation

* puissance disponible
* connecteurs nécessaires

---

## Compatibilité logicielle

* système d'exploitation
* hyperviseur
* compilateur
* logiciels professionnels

---

# 7. Mesures exploitables

Les mesures doivent être privilégiées lorsqu'elles sont disponibles.

## Performances générales

* performance mono-cœur
* performance multi-cœur
* IPC mesuré
* temps de compilation
* temps de rendu CPU
* temps d'encodage

---

## Jeux

* FPS moyens
* FPS minimum
* stabilité des FPS
* limitation CPU

---

## Intelligence artificielle

* vitesse d'inférence CPU
* vitesse d'entraînement CPU

---

## Consommation

* puissance au repos
* puissance en charge
* puissance maximale

---

## Température

* température moyenne
* température maximale
* fréquence soutenue

---

## Bruit

Indirectement via les besoins de refroidissement.

---

# 8. Métriques

Les métriques suivantes peuvent être calculées.

## Économiques

* Performance/€
* Performance utile/€
* Coût annuel
* Rendement marginal

---

## Énergétiques

* Performance/W
* Coût énergétique annuel

---

## Performances

* Performance/thread
* Performance/cœur
* Performance/cache
* Temps gagné/€

---

## Long terme

* Indice d'évolutivité
* Indice de robustesse
* Indice de remplaçabilité
* Coût d'évolution

---

# 9. Interactions

Le CPU interagit fortement avec :

## Carte mère

* socket
* VRM
* BIOS
* chipset

---

## Mémoire

* fréquence
* latence
* capacité
* nombre de canaux

---

## GPU

* limitation CPU
* lignes PCIe
* préparation des commandes

---

## Refroidissement

* puissance thermique
* fréquence soutenue
* bruit

---

## Alimentation

* consommation
* pics de puissance

---

# 10. Critères de décision

Le CPU est sélectionné selon :

1. adéquation à la mission ;
2. respect des contraintes ;
3. compatibilité ;
4. performances utiles ;
5. coût ;
6. consommation ;
7. évolutivité ;
8. fiabilité.

Le moteur privilégie le processeur présentant le meilleur compromis.

---

# 11. Durée de vie

Le moteur estime :

* durée de pertinence ;
* durée de support ;
* possibilité d'évolution sur la plateforme ;
* risque d'obsolescence.

---

# 12. Risques

Les principaux risques sont :

* changement de socket ;
* limitation mémoire ;
* limitation PCIe ;
* consommation excessive ;
* refroidissement insuffisant ;
* évolution logicielle.

Chaque risque doit être qualifié.

---

# 13. Rapport de décision

Le rapport doit expliquer :

* pourquoi ce CPU a été retenu ;
* quelles alternatives ont été étudiées ;
* quels critères ont conduit au rejet des autres modèles ;
* quelles mesures ont été utilisées ;
* quelles métriques ont été calculées ;
* quelles hypothèses ont été retenues ;
* quelles limites subsistent.

La décision doit être entièrement traçable et reproductible.
