# Refroidissement

## 1. Objet

Ce document définit les règles de sélection du système de refroidissement.

Le refroidissement constitue le système de gestion thermique du PC.

Sa mission est d'évacuer l'énergie thermique produite par les composants afin de maintenir leurs températures dans des plages compatibles avec leurs performances, leur stabilité et leur durée de vie.

Sa sélection influence directement :

* les performances soutenues ;
* la stabilité ;
* le niveau sonore ;
* la consommation ;
* la fiabilité ;
* la longévité des composants.

Toutes les règles générales du guide restent applicables.

---

# 2. Mission

La mission du système de refroidissement est de transporter puis de dissiper la chaleur produite par les composants vers l'environnement extérieur.

Le refroidissement ne crée aucune puissance de calcul.

Il permet aux composants de conserver leurs performances en limitant le throttling thermique et le vieillissement.

---

# 3. Ressources fournies

## Capacité de dissipation

Puissance thermique pouvant être évacuée de manière continue.

---

## Transport thermique

Capacité à transférer rapidement la chaleur :

* du CPU ;
* du GPU ;
* des VRM ;
* des SSD ;
* des autres composants.

---

## Débit d'air

Capacité à renouveler l'air à l'intérieur du boîtier.

---

## Pression statique

Capacité à faire traverser l'air au travers des radiateurs et filtres.

---

## Régulation

Capacité à adapter automatiquement la vitesse des ventilateurs selon la charge thermique.

---

## Niveau sonore

Capacité à maintenir un bruit acceptable pour la mission.

---

# 4. Capacités offertes

Le système de refroidissement peut permettre notamment :

* le maintien des fréquences Turbo ;
* la réduction du throttling ;
* une meilleure stabilité ;
* une diminution du bruit ;
* une augmentation de la durée de vie des composants ;
* des évolutions futures vers des composants plus exigeants.

---

# 5. Caractéristiques constructeur

Les informations suivantes doivent être collectées.

## Type

* refroidissement à air ;
* refroidissement liquide AIO ;
* boucle liquide personnalisée ;
* passif.

---

## Compatibilité

* sockets compatibles ;
* dimensions ;
* hauteur maximale ;
* dégagement mémoire.

---

## Ventilateurs

* diamètre ;
* vitesse ;
* PWM ;
* débit d'air annoncé ;
* pression statique annoncée.

---

## Radiateur

* matériau ;
* surface d'échange ;
* nombre de caloducs ;
* dimensions.

---

## Pompe (si applicable)

* vitesse ;
* consommation ;
* durée de vie annoncée.

---

## Niveau sonore annoncé

* bruit minimal ;
* bruit maximal.

---

# 6. Critères éliminatoires

Le système de refroidissement est rejeté immédiatement si :

## Compatibilité

* socket incompatible ;
* dimensions incompatibles avec le boîtier ;
* incompatibilité avec les modules mémoire.

---

## Performances

* capacité thermique insuffisante pour la mission.

---

## Contraintes

* coût supérieur au budget sans justification ;
* indisponibilité.

---

# 7. Vérifications

Le moteur vérifie notamment :

## Compatibilité CPU

* socket ;
* puissance thermique.

---

## Compatibilité boîtier

* hauteur ;
* longueur du radiateur ;
* emplacements disponibles.

---

## Compatibilité RAM

* dégagement des barrettes.

---

## Compatibilité ventilation

* sens des flux d'air ;
* nombre de ventilateurs.

---

## Compatibilité alimentation

* alimentation de la pompe ;
* connecteurs PWM.

---

# 8. Mesures exploitables

Les mesures doivent être réalisées dans des conditions représentatives.

## Température

* CPU ;
* GPU ;
* SSD ;
* VRM ;
* air interne.

---

## Performances

* fréquence soutenue ;
* durée avant throttling ;
* stabilité thermique.

---

## Bruit

* niveau sonore ;
* évolution avec la charge.

---

## Ventilation

* vitesse des ventilateurs ;
* débit réel.

---

## Consommation

* consommation des ventilateurs ;
* consommation de la pompe.

---

# 9. Métriques

Le moteur peut calculer notamment :

## Thermiques

* °C/W ;
* température maximale sous charge ;
* marge thermique disponible.

---

## Acoustiques

* performances/dB ;
* température/dB.

---

## Économiques

* coût/W dissipé ;
* coût annuel énergétique.

---

## Long terme

* indice de robustesse ;
* indice de remplaçabilité ;
* indice d'évolutivité ;
* coût d'entretien.

---

# 10. Interactions

Le refroidissement interagit avec l'ensemble du système.

Principalement :

## CPU

* température ;
* fréquence soutenue.

---

## GPU

* température interne du boîtier.

---

## Carte mère

* refroidissement des VRM ;
* circulation d'air.

---

## SSD

* limitation du throttling thermique.

---

## Boîtier

* flux d'air ;
* pression interne.

---

## Alimentation

* température ambiante.

---

# 11. Critères de décision

Le système de refroidissement est sélectionné selon :

1. compatibilité ;
2. capacité thermique ;
3. stabilité ;
4. niveau sonore ;
5. facilité de maintenance ;
6. évolutivité ;
7. coût.

Le moteur privilégie toujours la solution permettant de maintenir durablement les performances attendues dans les conditions réelles d'utilisation.

---

# 12. Durée de vie

Le moteur évalue notamment :

* durée de vie des ventilateurs ;
* durée de vie de la pompe (si applicable) ;
* facilité de remplacement des ventilateurs ;
* entretien nécessaire ;
* compatibilité avec de futurs composants.

---

# 13. Risques

Les principaux risques sont :

* refroidissement insuffisant ;
* bruit excessif ;
* encrassement ;
* panne de ventilateur ;
* panne de pompe ;
* mauvais flux d'air ;
* vieillissement de la pâte thermique ;
* throttling thermique.

Chaque risque doit être documenté.

---

# 14. Rapport de décision

Le rapport final doit expliquer :

* pourquoi cette solution thermique a été retenue ;
* pourquoi sa capacité de dissipation est suffisante ;
* comment les flux d'air ont été organisés ;
* quelles marges thermiques sont disponibles ;
* quelles évolutions futures restent possibles ;
* quelles mesures ont été utilisées ;
* quelles métriques ont été calculées ;
* quelles hypothèses subsistent.

La décision doit être entièrement traçable et reproductible.
