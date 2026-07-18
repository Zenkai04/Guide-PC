# Stockage

## 1. Objet

Ce document définit les règles de sélection des dispositifs de stockage.

Le stockage constitue la mémoire permanente du système.

Il assure la conservation, la lecture et l'écriture des données sur le long terme.

Sa sélection influence directement :

* les temps de démarrage ;
* les temps de chargement ;
* la réactivité générale ;
* les performances des applications manipulant de grands volumes de données ;
* la sécurité des données ;
* la stratégie de sauvegarde et d'évolution.

Toutes les règles générales du guide restent applicables.

---

# 2. Mission

La mission du stockage est de conserver durablement les données tout en fournissant des performances adaptées aux besoins de la mission.

Le stockage ne participe généralement pas aux calculs.

Il alimente les autres composants en données et en programmes.

---

# 3. Ressources fournies

## Capacité

Espace disponible pour :

* système d'exploitation ;
* applications ;
* données utilisateur ;
* jeux ;
* sauvegardes locales ;
* machines virtuelles.

---

## Débit

Capacité maximale de lecture et d'écriture des données.

---

## Latence

Temps nécessaire avant le début d'un accès aux données.

---

## IOPS

Nombre maximal d'opérations d'entrée/sortie réalisables par unité de temps.

---

## Endurance

Capacité à supporter les écritures au cours de sa durée de vie.

---

## Fiabilité

Capacité à conserver les données sans erreur ni défaillance.

---

# 4. Capacités offertes

Le stockage peut permettre notamment :

* le démarrage rapide du système ;
* le lancement rapide des applications ;
* le traitement de grands fichiers ;
* l'hébergement de machines virtuelles ;
* les bases de données ;
* le montage vidéo ;
* les bibliothèques IA ;
* les sauvegardes locales.

Ces capacités dépendent autant de l'organisation du stockage que des performances de chaque support.

---

# 5. Caractéristiques constructeur

Les informations suivantes doivent être collectées.

## Technologie

* SSD SATA ;
* SSD NVMe ;
* HDD ;
* mémoire flash utilisée (SLC, MLC, TLC, QLC...) ;
* contrôleur.

---

## Interface

* SATA ;
* PCI Express ;
* NVMe ;
* version PCIe.

---

## Capacité

* capacité utile ;
* capacité brute lorsque disponible.

---

## Performances annoncées

* lecture séquentielle ;
* écriture séquentielle ;
* IOPS lecture ;
* IOPS écriture.

---

## Endurance

* TBW ;
* DWPD lorsque disponible ;
* MTBF.

---

## Cache

* DRAM ;
* HMB ;
* cache SLC dynamique ou fixe.

---

## Consommation

* repos ;
* activité.

---

# 6. Critères éliminatoires

Le stockage est rejeté immédiatement si :

## Compatibilité

* interface incompatible ;
* format incompatible ;
* protocole incompatible.

---

## Capacité

* capacité insuffisante.

---

## Endurance

* endurance insuffisante pour la charge prévue.

---

## Contraintes

* coût supérieur au budget sans justification ;
* indisponibilité.

---

# 7. Vérifications

Le moteur vérifie notamment :

## Compatibilité carte mère

* M.2 ;
* SATA ;
* PCIe ;
* partage de lignes.

---

## Compatibilité boîtier

* emplacement physique.

---

## Compatibilité thermique

* dissipateur ;
* circulation d'air.

---

## Compatibilité système

* prise en charge du démarrage ;
* pilotes.

---

# 8. Mesures exploitables

Les mesures doivent refléter les usages réels.

## Séquentiel

* lecture ;
* écriture.

---

## Aléatoire

* lecture 4K ;
* écriture 4K.

---

## Soutenu

* performances après saturation du cache ;
* stabilité du débit.

---

## Latence

* latence moyenne ;
* latence maximale.

---

## Endurance

* usure mesurée ;
* température.

---

## Temps réels

* démarrage du système ;
* lancement des applications ;
* chargement des jeux ;
* import/export de gros fichiers.

---

# 9. Métriques

Le moteur peut calculer notamment :

## Économiques

* coût/Go ;
* coût/TBW ;
* coût/IOPS.

---

## Performances

* Go/s par euro ;
* IOPS par euro ;
* temps gagné par euro.

---

## Fiabilité

* coût annuel estimé ;
* endurance annuelle disponible.

---

## Long terme

* indice d'évolutivité ;
* indice de saturation ;
* indice de robustesse ;
* indice de remplaçabilité.

---

# 10. Interactions

Le stockage interagit principalement avec :

## Carte mère

* PCIe ;
* SATA ;
* M.2 ;
* partage de ressources.

---

## CPU

* contrôleur PCIe ;
* accès mémoire.

---

## RAM

* pagination ;
* caches.

---

## Applications

* bases de données ;
* virtualisation ;
* IA ;
* montage vidéo ;
* jeux.

---

## Refroidissement

* température ;
* throttling.

---

# 11. Critères de décision

Le stockage est sélectionné selon :

1. capacité suffisante ;
2. compatibilité ;
3. fiabilité ;
4. endurance adaptée ;
5. performances utiles ;
6. évolutivité ;
7. coût.

Le moteur privilégie toujours les performances réellement exploitées par la mission.

---

# 12. Durée de vie

Le moteur évalue notamment :

* usure prévisible ;
* endurance restante estimée ;
* possibilité d'ajout de nouveaux supports ;
* pérennité de l'interface.

---

# 13. Risques

Les principaux risques sont :

* capacité insuffisante ;
* saturation rapide ;
* throttling thermique ;
* absence de DRAM lorsque problématique ;
* usure prématurée ;
* perte de données ;
* dépendance à un seul support.

Chaque risque doit être documenté.

---

# 14. Rapport de décision

Le rapport final doit expliquer :

* pourquoi cette architecture de stockage a été retenue ;
* pourquoi cette capacité est suffisante ;
* pourquoi cette endurance est adaptée ;
* pourquoi les autres solutions ont été rejetées ;
* quelles mesures ont été utilisées ;
* quelles métriques ont été calculées ;
* quelles hypothèses subsistent.

La décision doit être entièrement traçable et reproductible.
