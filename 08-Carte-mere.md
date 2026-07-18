# Carte mère

## 1. Objet

Ce document définit les règles de sélection d'une carte mère.

La carte mère constitue l'infrastructure principale du système.

Elle assure :

* l'interconnexion des composants ;
* la distribution de l'alimentation ;
* la synchronisation des échanges ;
* la gestion des interfaces ;
* les possibilités d'extension ;
* une partie de la stratégie d'évolutivité.

Sa sélection influence directement les possibilités présentes et futures du système.

Toutes les règles générales du guide restent applicables.

---

# 2. Mission

La mission de la carte mère est de fournir une plateforme stable, compatible et évolutive permettant à l'ensemble des composants de fonctionner ensemble.

Elle ne cherche pas à produire des performances.

Elle cherche à permettre aux autres composants d'exprimer leurs performances.

---

# 3. Ressources fournies

## Infrastructure processeur

* socket CPU ;
* chipset ;
* VRM ;
* alimentation CPU ;
* horloges système.

---

## Infrastructure mémoire

* emplacements DIMM ;
* nombre de canaux ;
* capacité maximale ;
* compatibilité ECC ;
* fréquences supportées.

---

## Infrastructure PCI Express

* lignes PCIe ;
* versions PCIe ;
* répartition des lignes ;
* nombre de ports d'extension.

---

## Infrastructure stockage

* ports SATA ;
* emplacements M.2 ;
* compatibilité NVMe ;
* RAID éventuel.

---

## Infrastructure réseau

* Ethernet ;
* Wi-Fi ;
* Bluetooth.

---

## Infrastructure USB

* USB2 ;
* USB3 ;
* USB4 ;
* USB-C ;
* connecteurs internes.

---

## Infrastructure audio

* codec audio ;
* sorties audio ;
* entrées audio.

---

## Infrastructure firmware

* BIOS/UEFI ;
* Secure Boot ;
* TPM ;
* fonctions de récupération.

---

# 4. Capacités offertes

La carte mère peut permettre :

* l'installation du processeur choisi ;
* l'ajout de mémoire ;
* l'installation de cartes PCIe ;
* l'ajout de SSD ;
* le remplacement du processeur ;
* l'extension du stockage ;
* la connexion de périphériques ;
* le support de plusieurs écrans via iGPU ;
* certaines fonctions professionnelles (ECC, virtualisation, RAID, etc.).

Ces capacités dépendent des ressources précédentes.

---

# 5. Caractéristiques constructeur

Les informations suivantes doivent être collectées.

## Compatibilité

* socket ;
* chipset ;
* format ;
* génération supportée.

---

## VRM

* nombre de phases ;
* qualité des étages d'alimentation ;
* refroidissement des VRM.

---

## Mémoire

* nombre de slots ;
* capacité maximale ;
* fréquences supportées ;
* ECC.

---

## PCI Express

* version ;
* nombre de lignes ;
* répartition des lignes.

---

## Stockage

* SATA ;
* M.2 ;
* U.2 éventuel.

---

## Réseau

* vitesse Ethernet ;
* Wi-Fi ;
* Bluetooth.

---

## Connectique

* USB ;
* USB-C ;
* Thunderbolt éventuel ;
* sorties vidéo.

---

## Firmware

* BIOS Flashback ;
* double BIOS ;
* TPM ;
* Secure Boot.

---

# 6. Critères éliminatoires

La carte mère est rejetée immédiatement si :

## Compatibilité

* socket incompatible ;
* chipset incompatible avec la mission ;
* format incompatible avec le boîtier.

---

## Mémoire

* nombre de slots insuffisant ;
* capacité maximale insuffisante ;
* type de RAM incompatible.

---

## Stockage

* nombre de ports insuffisant.

---

## Extension

* lignes PCIe insuffisantes.

---

## Réseau

* absence d'une interface obligatoire.

---

## Contraintes

* coût injustifié ;
* indisponibilité.

---

# 7. Vérifications

Le moteur vérifie notamment :

## Compatibilité CPU

* socket ;
* BIOS ;
* génération.

---

## Compatibilité RAM

* type ;
* capacité ;
* fréquence ;
* ECC.

---

## Compatibilité GPU

* PCIe ;
* espace disponible.

---

## Compatibilité stockage

* SATA ;
* NVMe ;
* partage éventuel de lignes.

---

## Compatibilité alimentation

* connecteurs ;
* puissance.

---

## Compatibilité boîtier

* format ;
* entretoises ;
* connecteurs de façade.

---

# 8. Mesures exploitables

Les mesures concernent principalement :

## Alimentation

* stabilité des VRM ;
* température des VRM ;
* efficacité sous charge.

---

## Stockage

* performances réelles des ports M.2 ;
* limitations éventuelles.

---

## Réseau

* débit réel ;
* latence.

---

## USB

* débits mesurés.

---

## BIOS

* temps de démarrage ;
* stabilité.

---

## Consommation

* consommation propre de la carte.

---

# 9. Métriques

Le moteur peut calculer notamment :

## Infrastructure

* coût par port PCIe ;
* coût par port M.2 ;
* coût par port SATA.

---

## Mémoire

* coût par slot mémoire.

---

## Réseau

* coût par Gb/s.

---

## Long terme

* indice d'évolutivité ;
* indice d'extension ;
* indice de réutilisation ;
* indice de robustesse.

---

# 10. Interactions

La carte mère interagit avec l'ensemble du système.

Principalement :

## CPU

* socket ;
* VRM ;
* BIOS.

---

## RAM

* compatibilité ;
* fréquence ;
* capacité.

---

## GPU

* PCIe ;
* espace.

---

## SSD

* M.2 ;
* SATA ;
* partage de lignes.

---

## Boîtier

* format ;
* ventilation.

---

## Alimentation

* connecteurs ;
* puissance.

---

## Refroidissement

* emplacements ventilateurs ;
* pompes AIO ;
* sondes.

---

# 11. Critères de décision

La carte mère est sélectionnée selon :

1. compatibilité ;
2. stabilité ;
3. possibilités d'extension ;
4. qualité de l'alimentation ;
5. connectique ;
6. évolutivité ;
7. coût.

Le moteur privilégie la carte mère la plus adaptée à la stratégie d'évolution plutôt que celle possédant le plus grand nombre de fonctionnalités inutilisées.

---

# 12. Durée de vie

Le moteur évalue notamment :

* durée probable du socket ;
* durée de support BIOS ;
* évolutions CPU possibles ;
* possibilités d'extension ;
* pérennité des interfaces.

---

# 13. Risques

Les principaux risques sont :

* changement de socket ;
* BIOS obsolète ;
* VRM insuffisants ;
* manque de lignes PCIe ;
* manque d'emplacements mémoire ;
* saturation des ports M.2 ;
* partage de ressources limitant les performances.

Chaque risque doit être documenté.

---

# 14. Rapport de décision

Le rapport final doit expliquer :

* pourquoi cette carte mère a été retenue ;
* quelles ressources elle apporte ;
* quelles capacités elle offre ;
* quelles évolutions elle permettra ;
* quelles limites existent ;
* pourquoi les autres cartes ont été écartées.

La décision doit être entièrement traçable et reproductible.
