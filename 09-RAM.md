# Mémoire vive (RAM)

## 1. Objet

Ce document définit les règles de sélection de la mémoire vive (RAM).

La RAM constitue l'espace de travail temporaire du système.

Elle stocke les données et les instructions utilisées activement par le processeur et, dans certains cas, par le processeur graphique intégré.

Sa sélection influence directement :

* la fluidité du système ;
* les performances du processeur ;
* les performances de certaines applications ;
* la capacité à exécuter plusieurs tâches simultanément ;
* les possibilités d'évolution.

Toutes les règles générales du guide restent applicables.

---

# 2. Mission

La mission de la RAM est de fournir un espace de stockage temporaire rapide permettant aux processeurs d'accéder aux données nécessaires avec une latence faible et une bande passante suffisante.

La RAM ne produit aucun calcul.

Elle réduit les attentes du processeur et évite les accès beaucoup plus lents au stockage permanent.

---

# 3. Ressources fournies

## Capacité

La mémoire disponible pour :

* le système d'exploitation ;
* les applications ;
* les machines virtuelles ;
* les jeux ;
* les caches logiciels.

---

## Bande passante

Débit maximal de transfert entre la RAM et le contrôleur mémoire.

---

## Latence

Temps nécessaire avant qu'une donnée demandée puisse commencer à être transférée.

---

## Disponibilité

Capacité à maintenir suffisamment de mémoire libre afin d'éviter :

* la pagination ;
* le swapping ;
* les ralentissements importants.

---

## Fiabilité

Selon les configurations :

* ECC ;
* détection/correction d'erreurs ;
* stabilité.

---

# 4. Capacités offertes

La RAM peut permettre notamment :

* l'exécution simultanée de nombreuses applications ;
* la virtualisation ;
* le traitement de jeux de données volumineux ;
* le rendu 3D ;
* le montage vidéo ;
* les simulations ;
* l'entraînement de modèles IA sur CPU ;
* les caches importants.

Ces capacités dépendent principalement de la capacité disponible avant la vitesse.

---

# 5. Caractéristiques constructeur

Les informations suivantes doivent être collectées.

## Technologie

* DDR4
* DDR5
* LPDDR
* ECC ou non ECC

---

## Capacité

* capacité par barrette ;
* capacité totale.

---

## Organisation

* nombre de barrettes ;
* nombre de rangs (Ranks) ;
* organisation des puces si disponible.

---

## Performances

* fréquence effective (MT/s) ;
* timings principaux (CL, tRCD, tRP, tRAS...) ;
* tension.

---

## Compatibilité

* profils XMP/EXPO ;
* fréquence JEDEC ;
* capacité maximale certifiée.

---

## Format

* DIMM ;
* SO-DIMM.

---

# 6. Critères éliminatoires

La RAM est rejetée immédiatement si :

## Compatibilité

* technologie incompatible ;
* format incompatible ;
* ECC obligatoire absent ;
* profil mémoire incompatible lorsque requis.

---

## Capacité

* capacité insuffisante pour la mission ;
* capacité maximale de la carte mère dépassée.

---

## Contraintes

* coût supérieur au budget sans justification ;
* indisponibilité.

---

# 7. Vérifications

Le moteur vérifie notamment :

## Compatibilité carte mère

* type de mémoire ;
* fréquence supportée ;
* capacité maximale ;
* nombre de slots.

---

## Compatibilité CPU

* contrôleur mémoire ;
* fréquence supportée ;
* ECC.

---

## Configuration

* dual channel ;
* quad channel lorsque pertinent ;
* symétrie des modules.

---

## Refroidissement

* hauteur des barrettes ;
* compatibilité avec le ventirad.

---

# 8. Mesures exploitables

Les mesures doivent être adaptées à la mission.

## Performances mémoire

* bande passante réelle ;
* latence réelle (ns) ;
* temps d'accès.

---

## Applications

* temps de compilation ;
* temps de rendu ;
* performances des bases de données ;
* performances des machines virtuelles.

---

## Jeux

* FPS moyens ;
* FPS minimum ;
* stabilité.

---

## Système

* taux d'utilisation mémoire ;
* taux de pagination ;
* occupation maximale observée.

---

## Fiabilité

* stabilité sous charge ;
* erreurs mémoire détectées.

---

# 9. Métriques

Le moteur peut calculer notamment :

## Économiques

* coût/Go ;
* coût par Go/s ;
* coût par ns de latence.

---

## Performances

* bande passante par euro ;
* capacité par euro ;
* latence réelle.

---

## Utilisation

* taux d'utilisation moyen ;
* marge mémoire disponible ;
* capacité inutilisée.

---

## Long terme

* indice d'évolutivité ;
* indice de remplaçabilité ;
* indice de saturation.

---

# 10. Interactions

La RAM interagit principalement avec :

## CPU

* contrôleur mémoire ;
* nombre de canaux ;
* cache.

---

## Carte mère

* slots ;
* fréquence ;
* alimentation.

---

## GPU intégré

* partage de mémoire ;
* bande passante.

---

## Stockage

* pagination ;
* caches.

---

## Applications

* machines virtuelles ;
* bases de données ;
* IA ;
* rendu.

---

# 11. Critères de décision

La RAM est sélectionnée selon l'ordre suivant :

1. capacité suffisante ;
2. compatibilité ;
3. stabilité ;
4. possibilité d'évolution ;
5. bande passante adaptée ;
6. latence adaptée ;
7. coût.

La capacité est prioritaire sur les performances lorsque la mémoire disponible est insuffisante.

---

# 12. Durée de vie

Le moteur évalue notamment :

* possibilité d'ajouter des modules ;
* durée probable avant saturation ;
* pérennité de la technologie ;
* disponibilité future des modules compatibles.

---

# 13. Risques

Les principaux risques sont :

* capacité insuffisante ;
* mélange de modules incompatibles ;
* perte du dual channel ;
* instabilité des profils XMP/EXPO ;
* fréquence excessive nécessitant des réglages complexes ;
* obsolescence de la plateforme.

Chaque risque doit être documenté.

---

# 14. Rapport de décision

Le rapport doit expliquer :

* pourquoi cette capacité a été retenue ;
* pourquoi cette fréquence est suffisante ;
* pourquoi cette latence est acceptable ;
* quelles possibilités d'évolution existent ;
* quelles alternatives ont été rejetées ;
* quelles mesures ont été utilisées ;
* quelles métriques ont été calculées ;
* quelles hypothèses subsistent.

La décision doit être entièrement traçable et reproductible.
