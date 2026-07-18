# Alimentation (PSU)

## 1. Objet

Ce document définit les règles de sélection d'une alimentation électrique (PSU).

L'alimentation constitue la source d'énergie du système.

Elle convertit le courant alternatif du réseau électrique en tensions continues stables nécessaires au fonctionnement des composants.

Sa sélection influence directement :

* la stabilité du système ;
* la sécurité des composants ;
* la consommation énergétique ;
* le niveau sonore ;
* la fiabilité globale ;
* les possibilités d'évolution.

Toutes les règles générales du guide restent applicables.

---

# 2. Mission

La mission de l'alimentation est de fournir une énergie stable, fiable et suffisante à l'ensemble des composants, quelles que soient les variations de charge.

Elle doit également protéger le système contre les anomalies électriques et fonctionner avec un rendement élevé.

Elle ne crée aucune performance informatique, mais conditionne la stabilité et la longévité de tous les autres composants.

---

# 3. Ressources fournies

## Puissance disponible

Énergie électrique pouvant être fournie de manière continue.

---

## Stabilité électrique

Maintien des tensions dans les plages spécifiées malgré les variations de charge.

---

## Gestion des pics

Capacité à absorber des appels de puissance brefs sans provoquer d'instabilité.

---

## Rendement

Proportion de l'énergie consommée réellement délivrée aux composants.

---

## Protection

Mécanismes de protection contre :

* surtension ;
* sous-tension ;
* surintensité ;
* surcharge ;
* court-circuit ;
* surchauffe.

---

## Connectivité

Alimentation des différents composants via les connecteurs adaptés.

---

# 4. Capacités offertes

Une alimentation peut permettre notamment :

* le fonctionnement stable de composants à forte consommation ;
* les évolutions futures du système ;
* un fonctionnement silencieux grâce à un rendement élevé ;
* une meilleure efficacité énergétique ;
* une meilleure protection du matériel ;
* une plus grande durée de vie des composants alimentés.

---

# 5. Caractéristiques constructeur

Les informations suivantes doivent être collectées.

## Puissance

* puissance nominale ;
* puissance sur le rail +12 V ;
* puissance maximale temporaire si documentée.

---

## Rendement

* certification (80 PLUS ou équivalent) ;
* courbe de rendement selon la charge.

---

## Rails

* mono-rail ou multi-rails ;
* intensité maximale par rail.

---

## Connectique

* ATX ;
* EPS ;
* PCIe ;
* 12V-2x6 / 12VHPWR si applicable ;
* SATA ;
* Molex.

---

## Refroidissement

* diamètre du ventilateur ;
* mode semi-passif ;
* contrôle thermique.

---

## Qualité interne

* topologie ;
* condensateurs ;
* protections implémentées ;
* garantie constructeur.

---

## Format

* ATX ;
* SFX ;
* SFX-L ;
* autres formats.

---

# 6. Critères éliminatoires

L'alimentation est rejetée immédiatement si :

## Puissance

* puissance insuffisante pour la configuration.

---

## Compatibilité

* format incompatible avec le boîtier ;
* connecteurs insuffisants.

---

## Sécurité

* protections essentielles absentes ;
* qualité insuffisante pour la mission.

---

## Contraintes

* coût supérieur au budget sans justification ;
* indisponibilité.

---

# 7. Vérifications

Le moteur vérifie notamment :

## Compatibilité boîtier

* format ;
* longueur ;
* ventilation.

---

## Compatibilité composants

* CPU ;
* GPU ;
* stockage ;
* cartes d'extension.

---

## Consommation

* puissance moyenne ;
* puissance maximale ;
* pics transitoires.

---

## Évolutions futures

* marge de puissance ;
* connecteurs disponibles.

---

# 8. Mesures exploitables

Les mesures doivent être réalisées dans des conditions représentatives.

## Rendement

* rendement à 10 %, 20 %, 50 % et 100 % de charge ;
* consommation au repos.

---

## Régulation

* stabilité des tensions ;
* variations sous charge.

---

## Bruit électrique

* ondulation (ripple) ;
* bruit résiduel.

---

## Thermique

* température ;
* vitesse du ventilateur.

---

## Acoustique

* niveau sonore ;
* comportement en montée en charge.

---

## Sécurité

* comportement lors des pics ;
* comportement en surcharge.

---

# 9. Métriques

Le moteur peut calculer notamment :

## Économiques

* coût/W ;
* coût/W réellement exploitable ;
* coût annuel énergétique.

---

## Énergétiques

* rendement moyen pondéré ;
* pertes thermiques annuelles ;
* consommation annuelle estimée.

---

## Long terme

* indice de robustesse ;
* indice de réutilisation ;
* indice de remplaçabilité ;
* coût total d'exploitation.

---

# 10. Interactions

L'alimentation interagit avec l'ensemble du système.

Principalement :

## CPU

* alimentation stable ;
* pics de consommation.

---

## GPU

* puissance ;
* connecteurs ;
* pics transitoires.

---

## Carte mère

* alimentation principale ;
* EPS CPU.

---

## Refroidissement

* chaleur dissipée par l'alimentation ;
* impact sur le flux d'air.

---

## Boîtier

* compatibilité physique ;
* circulation de l'air.

---

# 11. Critères de décision

L'alimentation est sélectionnée selon :

1. compatibilité ;
2. sécurité ;
3. stabilité électrique ;
4. puissance réellement nécessaire ;
5. qualité des protections ;
6. rendement ;
7. niveau sonore ;
8. évolutivité ;
9. coût.

Le moteur privilégie une alimentation fiable et adaptée à la charge réelle plutôt qu'une puissance excessive sans justification.

---

# 12. Durée de vie

Le moteur évalue notamment :

* durée probable des composants internes ;
* qualité des condensateurs ;
* durée de garantie ;
* possibilité de réutilisation dans une future configuration ;
* capacité à accompagner des évolutions matérielles.

---

# 13. Risques

Les principaux risques sont :

* puissance insuffisante ;
* alimentation surdimensionnée sans bénéfice ;
* protections incomplètes ;
* mauvais rendement ;
* bruit important ;
* vieillissement prématuré ;
* instabilité électrique lors des pics de charge.

Chaque risque doit être documenté.

---

# 14. Rapport de décision

Le rapport final doit expliquer :

* pourquoi cette alimentation a été retenue ;
* pourquoi sa puissance est adaptée ;
* quelles marges de sécurité ont été retenues ;
* quelles évolutions elle permettra ;
* pourquoi les autres modèles ont été écartés ;
* quelles mesures ont été utilisées ;
* quelles métriques ont été calculées ;
* quelles hypothèses subsistent.

La décision doit être entièrement traçable et reproductible.
