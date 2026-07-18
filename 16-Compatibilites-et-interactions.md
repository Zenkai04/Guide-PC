# Compatibilités et interactions

## 1. Objet

Ce document définit les règles permettant d'évaluer la cohérence globale d'une configuration.

Les documents précédents analysent chaque composant individuellement.

Celui-ci étudie leurs interactions.

L'objectif n'est plus de sélectionner les meilleurs composants pris isolément, mais de construire un système cohérent, équilibré et adapté à sa mission.

Toutes les règles générales du guide restent applicables.

---

# 2. Vision systémique

Un ordinateur est un système composé de sous-systèmes en interaction.

Chaque composant influence les performances, la consommation, la stabilité et les possibilités d'évolution des autres.

Les performances globales résultent de ces interactions et non de la simple addition des performances individuelles.

---

# 3. Familles d'interactions

Le moteur distingue plusieurs catégories d'interactions.

## Interactions fonctionnelles

Déterminent si les composants peuvent fonctionner ensemble.

Exemples :

* compatibilité CPU / carte mère ;
* compatibilité RAM / contrôleur mémoire ;
* compatibilité GPU / alimentation.

---

## Interactions physiques

Déterminent si les composants peuvent être installés ensemble.

Exemples :

* dimensions ;
* connecteurs ;
* espace disponible ;
* circulation de l'air.

---

## Interactions électriques

Concernent :

* puissance ;
* alimentation ;
* stabilité des tensions ;
* pics de consommation.

---

## Interactions thermiques

Concernent :

* dissipation de chaleur ;
* température interne ;
* flux d'air ;
* throttling.

---

## Interactions logicielles

Concernent :

* pilotes ;
* BIOS/UEFI ;
* systèmes d'exploitation ;
* API ;
* firmwares.

---

## Interactions ergonomiques

Concernent :

* bruit ;
* maintenance ;
* accessibilité ;
* confort d'utilisation.

---

## Interactions économiques

Concernent :

* coût global ;
* coût d'évolution ;
* coût énergétique ;
* coût total de possession.

---

# 4. Compatibilités obligatoires

Le moteur vérifie notamment :

## CPU ↔ Carte mère

* socket ;
* chipset ;
* BIOS ;
* alimentation.

---

## CPU ↔ RAM

* type ;
* fréquence ;
* capacité ;
* ECC.

---

## GPU ↔ Carte mère

* PCIe ;
* espace.

---

## GPU ↔ Boîtier

* longueur ;
* épaisseur.

---

## GPU ↔ Alimentation

* puissance ;
* connecteurs ;
* pics transitoires.

---

## Refroidissement ↔ Boîtier

* dimensions ;
* radiateurs ;
* ventilation.

---

## Stockage ↔ Carte mère

* SATA ;
* M.2 ;
* PCIe ;
* partage de lignes.

---

## Écran ↔ GPU

* résolution ;
* fréquence ;
* HDR ;
* VRR.

---

## Périphériques ↔ Connectique

* interfaces ;
* pilotes.

---

# 5. Interactions de performances

Le moteur analyse notamment :

## Limitation CPU

Le CPU limite le GPU.

---

## Limitation GPU

Le GPU limite le CPU.

---

## Limitation mémoire

Capacité insuffisante.

Latence excessive.

Bande passante insuffisante.

---

## Limitation stockage

Temps d'accès.

IOPS.

Saturation.

---

## Limitation thermique

Fréquences réduites.

---

## Limitation électrique

Pics.

Instabilités.

---

# 6. Goulots d'étranglement

Le moteur identifie :

* les ressources saturées ;
* les ressources sous-utilisées ;
* les chaînes de transfert limitées.

Chaque goulot est qualifié selon :

* sa fréquence ;
* son impact ;
* son coût de correction.

---

# 7. Équilibre système

Une configuration équilibrée est une configuration dans laquelle aucune ressource essentielle n'est durablement sous-dimensionnée ou inutilement surdimensionnée par rapport aux autres.

Le moteur évalue notamment :

* équilibre des performances ;
* équilibre énergétique ;
* équilibre thermique ;
* équilibre économique ;
* équilibre d'évolutivité.

---

# 8. Marges

Le moteur calcule les marges disponibles pour :

* alimentation ;
* refroidissement ;
* mémoire ;
* stockage ;
* ports disponibles ;
* lignes PCIe.

Ces marges conditionnent les possibilités d'évolution.

---

# 9. Ressources partagées

Certaines ressources sont communes à plusieurs composants.

Exemples :

* lignes PCIe ;
* bande passante mémoire ;
* alimentation ;
* refroidissement ;
* ports USB.

Le moteur vérifie les conflits potentiels.

---

# 10. Dépendances

Le moteur identifie les dépendances fortes.

Exemples :

* changement de socket ;
* changement de génération mémoire ;
* remplacement imposant une nouvelle alimentation.

Chaque dépendance est documentée.

---

# 11. Scénarios d'évolution

Le moteur simule notamment :

* ajout de RAM ;
* remplacement du GPU ;
* changement du CPU ;
* ajout de stockage ;
* ajout d'écrans.

Pour chaque scénario :

* faisabilité ;
* coût ;
* composants impactés.

---

# 12. Robustesse globale

Le moteur évalue la capacité du système à conserver :

* ses performances ;
* sa stabilité ;
* sa sécurité ;

malgré :

* une augmentation des charges ;
* une évolution des usages ;
* une panne d'un composant non critique ;
* des évolutions matérielles.

---

# 13. Cohérence globale

Le moteur produit une analyse qualitative de la configuration.

Il répond notamment aux questions suivantes :

* Les composants sont-ils adaptés les uns aux autres ?
* Existe-t-il des ressources inutilisées ?
* Existe-t-il des ressources insuffisantes ?
* La stratégie budgétaire est-elle cohérente ?
* Les possibilités d'évolution sont-elles suffisantes ?

---

# 14. Rapport d'interactions

Le rapport final doit expliquer :

* les interactions importantes ;
* les compatibilités vérifiées ;
* les incompatibilités détectées ;
* les goulots d'étranglement ;
* les marges disponibles ;
* les risques d'évolution ;
* les hypothèses retenues.

Toutes les conclusions doivent être traçables et reproductibles.
