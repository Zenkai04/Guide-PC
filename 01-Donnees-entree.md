# Données d'entrée

## 1. Objet

Ce document définit l'ensemble des informations pouvant être fournies au moteur de décision avant toute sélection de composants.

Aucune décision ne doit être prise dans ce document.

Son objectif est uniquement de normaliser les données d'entrée.

Chaque donnée possède :

* un identifiant ;
* un type ;
* un caractère obligatoire ou optionnel ;
* une unité si nécessaire ;
* une plage de valeurs ;
* un niveau de confiance éventuel.

---

# 2. Catégories

Les données sont réparties dans les catégories suivantes :

1. Mission
2. Charges de travail
3. Contraintes
4. Budget
5. Durée de vie
6. Environnement
7. Équipements existants
8. Préférences utilisateur
9. Évolution prévue
10. Données calculées

---

# 3. Mission

## Mission principale

**Identifiant**

MISSION_PRIMARY

**Type**

Liste

**Obligatoire**

Oui

**Valeurs possibles**

* Bureautique
* Développement
* Jeu vidéo
* Création graphique
* Montage vidéo
* Rendu 3D
* Intelligence artificielle
* Virtualisation
* Serveur personnel
* Calcul scientifique
* Polyvalent
* Autre

---

## Missions secondaires

MISSION_SECONDARY

Liste

Optionnel

Plusieurs valeurs autorisées.

---

## Importance de chaque mission

MISSION_WEIGHT

Type :

Pourcentage

Somme = 100 %

Exemple :

Jeu vidéo : 70 %

Développement : 20 %

Montage : 10 %

---

# 4. Charges de travail

Pour chaque activité, indiquer :

* fréquence
* durée
* criticité

Exemple :

Compilation

Fréquence :

Quotidienne

Durée :

3 h

Criticité :

Élevée

---

Jeux

Résolution

Framerate souhaité

Qualité graphique

Ray tracing

DLSS/FSR autorisé

VR

Nombre d'écrans

---

IA

Framework

CUDA obligatoire

Mémoire GPU minimale

Taille des modèles

---

Virtualisation

Nombre de VM simultanées

RAM totale souhaitée

Stockage réservé

---

# 5. Budget

BUDGET_MIN

Budget minimal

---

BUDGET_TARGET

Budget cible

---

BUDGET_MAX

Budget maximal

---

Monnaie

---

TVA incluse ?

---

Montage inclus ?

---

Écrans inclus ?

---

Périphériques inclus ?

---

# 6. Durée de vie

Durée souhaitée

Années

---

Fréquence de remplacement complète

---

Composants pouvant être remplacés

Liste :

GPU

RAM

SSD

CPU

Carte mère

Alimentation

Boîtier

Refroidissement

---

# 7. Contraintes

Bruit maximal

dB(A)

---

Consommation maximale

Watts

---

Dimensions maximales

Hauteur

Largeur

Profondeur

---

Poids maximal

---

Couleur imposée

---

Format de carte mère

ATX

Micro ATX

Mini ITX

Libre

---

# 8. Environnement

Température ambiante

---

Humidité

---

Altitude (optionnel)

---

Présence d'animaux

---

Présence de poussière

Faible

Moyenne

Élevée

---

Fumeur

Oui

Non

---

Utilisation

Maison

Entreprise

Transport fréquent

---

# 9. Équipements existants

Écrans

Résolution

Fréquence

HDR

VRR

---

Stockage réutilisable

---

GPU conservé

---

Boîtier conservé

---

Licence Windows existante

---

NAS

---

# 10. Préférences

Silence

Priorité de 0 à 10

---

Consommation

0 à 10

---

Performance

0 à 10

---

Esthétique

0 à 10

---

RGB

Oui

Non

---

Overclocking souhaité

Oui

Non

---

Undervolting accepté

Oui

Non

---

Marques interdites

Liste

---

Marques préférées

Liste

---

# 11. Évolution

Ajout de RAM prévu

Oui

Non

---

Ajout de SSD prévu

Oui

Non

---

Changement GPU prévu

Oui

Non

---

Changement CPU prévu

Oui

Non

---

Nombre d'années avant évolution prévue

---

# 12. Sources de données

Chaque donnée doit être accompagnée d'une origine.

Utilisateur

Documentation

Mesure

Estimation

Calcul

Hypothèse

---

# 13. Niveau de confiance

Chaque donnée reçoit un niveau.

A

Mesure vérifiée

B

Déclaration utilisateur

C

Estimation

D

Hypothèse

---

# 14. Données dérivées

Le moteur pourra calculer automatiquement :

* charge CPU estimée ;
* charge GPU estimée ;
* mémoire minimale ;
* VRAM minimale ;
* capacité de stockage minimale ;
* puissance électrique estimée ;
* marge thermique souhaitée ;
* niveau d'évolutivité requis.

Ces valeurs ne sont jamais saisies directement par l'utilisateur.

Elles sont produites à partir des données précédentes.

---

# 15. Validation

Avant toute sélection de composants, le moteur doit vérifier :

* toutes les données obligatoires présentes ;
* aucune incohérence logique ;
* budget valide ;
* mission définie ;
* durée de vie définie ;
* contraintes cohérentes.

Aucune sélection ne doit commencer si cette étape n'est pas validée.
