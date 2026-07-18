# GPU

## 1. Objet

Ce document définit les règles de sélection d'un processeur graphique (GPU).

Il décrit :

* son rôle dans le système ;
* les ressources qu'il met à disposition ;
* les caractéristiques à collecter ;
* les critères éliminatoires ;
* les vérifications ;
* les mesures exploitables ;
* les métriques ;
* les interactions avec les autres composants ;
* les critères de décision ;
* les considérations de durée de vie et d'évolutivité.

Toutes les règles générales du guide restent applicables.

---

# 2. Mission du GPU

Le GPU est un processeur spécialisé dans l'exécution massive de calculs parallèles.

Sa mission est d'accélérer les traitements dont le parallélisme est important.

Selon la mission du système, il peut être :

* le composant directeur ;
* un accélérateur spécialisé ;
* ou un composant secondaire.

---

# 3. Fonctions assurées

Le GPU peut intervenir notamment dans :

* affichage graphique ;
* rendu 3D ;
* jeux vidéo ;
* ray tracing ;
* calcul parallèle (GPGPU) ;
* intelligence artificielle ;
* simulation ;
* traitement photo ;
* montage vidéo ;
* encodage matériel ;
* décodage matériel ;
* calcul scientifique.

---

# 4. Ressources fournies

Le GPU met principalement à disposition les ressources suivantes.

## Ressources de calcul

* puissance de calcul parallèle ;
* unités de calcul ;
* accélérateurs spécialisés (Tensor, Matrix, AI, etc.) ;
* accélérateurs de ray tracing.

---

## Ressources mémoire

* VRAM ;
* bande passante mémoire ;
* largeur du bus mémoire ;
* cache graphique.

---

## Ressources vidéo

* moteurs d'encodage ;
* moteurs de décodage ;
* codecs supportés ;
* accélération matérielle.

---

## Ressources d'affichage

* nombre maximal d'écrans ;
* résolutions supportées ;
* taux de rafraîchissement ;
* HDR ;
* VRR ;
* DisplayPort ;
* HDMI.

---

## Ressources logicielles

* API graphiques ;
* CUDA, ROCm, OpenCL ou équivalent ;
* DirectX ;
* Vulkan ;
* OpenGL ;
* bibliothèques IA.

---

# 5. Caractéristiques constructeur

Les informations suivantes doivent être collectées.

## Architecture

* constructeur ;
* famille ;
* génération ;
* procédé de fabrication.

---

## Calcul

* unités de calcul ;
* fréquence de base ;
* fréquence boost ;
* puissance théorique.

---

## Mémoire

* capacité VRAM ;
* type ;
* fréquence ;
* bande passante ;
* largeur du bus ;
* cache.

---

## Consommation

* TBP/TGP/TDP ;
* alimentation requise ;
* connecteurs.

---

## Dimensions

* longueur ;
* hauteur ;
* épaisseur ;
* nombre de slots.

---

## Connectique

* DisplayPort ;
* HDMI ;
* USB-C éventuel.

---

# 6. Critères éliminatoires

Le GPU est rejeté immédiatement si :

## Compatibilité

* longueur incompatible avec le boîtier ;
* alimentation insuffisante ;
* connecteurs absents ;
* API indispensable absente ;
* framework requis non supporté.

---

## Mémoire

* VRAM insuffisante ;
* bande passante insuffisante lorsque la mission l'exige.

---

## Performances

* performances minimales non atteintes ;
* accélération obligatoire absente.

---

## Contraintes

* consommation supérieure à la limite imposée ;
* coût supérieur au budget sans justification.

---

# 7. Vérifications

Le moteur vérifie notamment :

## Compatibilité physique

* dimensions ;
* nombre de slots ;
* dégagement interne.

---

## Compatibilité électrique

* puissance disponible ;
* connecteurs ;
* pics de consommation.

---

## Compatibilité logicielle

* pilotes ;
* systèmes d'exploitation ;
* frameworks IA ;
* moteurs de rendu.

---

## Compatibilité affichage

* nombre d'écrans ;
* résolution ;
* fréquence ;
* HDR ;
* VRR.

---

# 8. Mesures exploitables

Les mesures doivent être représentatives de la mission.

## Jeux

* FPS moyens ;
* FPS minimum ;
* stabilité des FPS ;
* consommation ;
* température.

---

## Création

* temps de rendu ;
* accélération Blender ;
* accélération Adobe ;
* accélération DaVinci Resolve.

---

## Intelligence artificielle

* vitesse d'entraînement ;
* vitesse d'inférence ;
* utilisation de la VRAM ;
* débit mémoire.

---

## Calcul scientifique

* temps d'exécution ;
* débit de calcul.

---

## Vidéo

* vitesse d'encodage ;
* vitesse de décodage ;
* qualité d'encodage.

---

## Énergie

* consommation au repos ;
* consommation moyenne ;
* consommation maximale.

---

## Thermique

* température ;
* fréquence soutenue ;
* bruit.

---

# 9. Métriques

Le moteur peut calculer notamment :

## Économiques

* Performance/€
* FPS/€
* Images rendues/€
* Temps gagné/€

---

## Énergétiques

* Performance/W
* FPS/W
* Rendement énergétique.

---

## Mémoire

* Performance/Go de VRAM ;
* Utilisation moyenne de la VRAM ;
* Coût/Go de VRAM.

---

## Long terme

* Indice d'évolutivité ;
* Indice de remplaçabilité ;
* Indice de robustesse ;
* Durée de pertinence estimée.

---

# 10. Interactions

Le GPU interagit principalement avec :

## CPU

* limitation CPU ;
* préparation des commandes.

---

## Carte mère

* PCI Express ;
* espace disponible.

---

## Alimentation

* puissance ;
* connecteurs ;
* pics de charge.

---

## Refroidissement

* circulation d'air ;
* capacité thermique.

---

## Boîtier

* dimensions ;
* ventilation.

---

## Écran

* résolution ;
* fréquence ;
* HDR ;
* VRR.

---

# 11. Critères de décision

Le GPU est sélectionné selon :

1. adéquation à la mission ;
2. compatibilité ;
3. VRAM suffisante ;
4. performances utiles ;
5. consommation ;
6. bruit ;
7. coût ;
8. évolutivité.

Le moteur privilégie toujours les performances réellement exploitables.

---

# 12. Durée de vie

Le moteur estime notamment :

* durée de pertinence graphique ;
* durée de pertinence IA ;
* durée du support logiciel ;
* risque de saturation de la VRAM ;
* possibilité de réutilisation.

---

# 13. Risques

Le moteur évalue notamment :

* VRAM insuffisante ;
* consommation excessive ;
* dépendance à un framework propriétaire ;
* limitation de bande passante ;
* incompatibilité future des pilotes ;
* obsolescence rapide.

Chaque risque doit être documenté.

---

# 14. Rapport de décision

Le rapport doit préciser :

* pourquoi ce GPU a été retenu ;
* pourquoi les autres modèles ont été rejetés ;
* quelles mesures ont été utilisées ;
* quelles métriques ont été calculées ;
* quelles hypothèses ont été retenues ;
* quelles limites subsistent.

Le rapport doit être entièrement reproductible.
