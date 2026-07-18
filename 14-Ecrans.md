# Écrans

## 1. Objet

Ce document définit les règles de sélection des écrans.

L'écran constitue l'interface visuelle principale entre le système informatique et l'utilisateur.

Il transforme les informations numériques produites par le système en informations visuelles perceptibles.

Sa sélection influence directement :

* le confort d'utilisation ;
* la productivité ;
* l'immersion ;
* la fidélité de restitution ;
* la fatigue visuelle ;
* l'expérience utilisateur.

Toutes les règles générales du guide restent applicables.

---

# 2. Mission

La mission de l'écran est de restituer les informations visuelles produites par le système avec une qualité adaptée à la mission.

L'écran ne crée aucun calcul.

Il restitue les résultats produits par les autres composants.

La qualité de cette restitution dépend autant des capacités de l'écran que des capacités perceptives de l'utilisateur.

---

# 3. Ressources fournies

## Surface d'affichage

Espace disponible pour présenter les informations.

---

## Définition

Nombre de pixels disponibles.

---

## Fréquence d'affichage

Nombre maximal d'images affichées par seconde.

---

## Fidélité colorimétrique

Capacité à reproduire fidèlement les couleurs.

---

## Luminosité

Capacité à rester lisible selon les conditions d'éclairage.

---

## Contraste

Capacité à distinguer les différences de luminance.

---

## Temps de réponse

Temps nécessaire pour modifier l'état d'un pixel.

---

## Connectivité

Interfaces permettant la communication avec le système.

---

# 4. Capacités offertes

L'écran peut permettre notamment :

* le travail bureautique ;
* le développement logiciel ;
* la création graphique ;
* la retouche photo ;
* le montage vidéo ;
* le jeu vidéo ;
* la simulation ;
* l'affichage multi-écrans.

Ces capacités dépendent de la combinaison des ressources précédentes.

---

# 5. Caractéristiques constructeur

Les informations suivantes doivent être collectées.

## Dalle

* IPS ;
* VA ;
* TN ;
* OLED ;
* Mini-LED ;
* autres technologies.

---

## Dimensions

* diagonale ;
* largeur ;
* hauteur.

---

## Définition

* Full HD ;
* QHD ;
* UHD ;
* autres.

---

## Fréquence

* fréquence maximale ;
* fréquence variable (VRR).

---

## Couleurs

* profondeur de couleur ;
* couverture des espaces colorimétriques (sRGB, DCI-P3, Adobe RGB, etc.) ;
* précision colorimétrique (ΔE lorsque disponible).

---

## Luminosité

* luminosité typique ;
* luminosité HDR.

---

## Contraste

* contraste statique ;
* contraste dynamique lorsque pertinent.

---

## Connectique

* DisplayPort ;
* HDMI ;
* USB-C ;
* hub USB ;
* KVM éventuel.

---

## Ergonomie

* réglage en hauteur ;
* inclinaison ;
* rotation ;
* pivot.

---

# 6. Critères éliminatoires

L'écran est rejeté immédiatement si :

## Compatibilité

* résolution incompatible avec la mission ;
* connectique incompatible ;
* taille incompatible avec les contraintes.

---

## Qualité

* fidélité colorimétrique insuffisante lorsque critique ;
* fréquence insuffisante pour la mission.

---

## Contraintes

* coût supérieur au budget sans justification ;
* indisponibilité.

---

# 7. Vérifications

Le moteur vérifie notamment :

## Compatibilité GPU

* résolution ;
* fréquence ;
* bande passante vidéo.

---

## Compatibilité bureau

* dimensions ;
* supports VESA ;
* encombrement.

---

## Compatibilité utilisateur

* distance de vision ;
* nombre d'écrans ;
* ergonomie.

---

## Compatibilité logicielle

* HDR ;
* gestion multi-écrans.

---

# 8. Mesures exploitables

Les mesures doivent être réalisées dans des conditions représentatives.

## Qualité d'image

* précision colorimétrique ;
* contraste réel ;
* luminosité réelle ;
* uniformité.

---

## Fluidité

* fréquence réelle ;
* temps de réponse ;
* retard à l'affichage (input lag).

---

## Ergonomie

* confort d'utilisation ;
* lisibilité ;
* fatigue visuelle.

---

## Consommation

* consommation moyenne ;
* consommation HDR.

---

# 9. Métriques

Le moteur peut calculer notamment :

## Qualité

* densité de pixels (PPI) ;
* surface utile ;
* pixels par euro.

---

## Économiques

* coût par pouce ;
* coût par pixel ;
* coût par Hz.

---

## Long terme

* indice de confort ;
* indice d'évolutivité ;
* indice de robustesse ;
* indice de réutilisation.

---

# 10. Interactions

L'écran interagit principalement avec :

## GPU

* résolution ;
* fréquence ;
* VRR ;
* HDR.

---

## Utilisateur

* distance d'observation ;
* champ de vision ;
* posture.

---

## Bureau

* espace disponible ;
* bras articulé ;
* disposition multi-écrans.

---

## Environnement

* éclairage ambiant ;
* reflets ;
* luminosité.

---

# 11. Critères de décision

L'écran est sélectionné selon :

1. adéquation à la mission ;
2. confort visuel ;
3. fidélité de restitution ;
4. fluidité ;
5. ergonomie ;
6. évolutivité ;
7. coût.

Le moteur privilégie l'écran offrant la meilleure qualité perceptible pour l'utilisateur dans son environnement réel.

---

# 12. Durée de vie

Le moteur évalue notamment :

* durée de vie de la dalle ;
* risque de marquage lorsque pertinent ;
* disponibilité des interfaces futures ;
* possibilité de réutilisation ;
* évolution des besoins.

---

# 13. Risques

Les principaux risques sont :

* résolution surdimensionnée ou insuffisante ;
* fréquence inutilement élevée ;
* fatigue visuelle ;
* mauvaise fidélité colorimétrique ;
* luminosité insuffisante ;
* incompatibilité avec les usages futurs ;
* connectique limitée.

Chaque risque doit être documenté.

---

# 14. Rapport de décision

Le rapport final doit expliquer :

* pourquoi cet écran a été retenu ;
* pourquoi sa résolution est adaptée ;
* pourquoi sa fréquence est suffisante ;
* pourquoi sa qualité d'image répond à la mission ;
* quelles possibilités d'évolution existent ;
* quelles mesures ont été utilisées ;
* quelles métriques ont été calculées ;
* quelles hypothèses subsistent.

La décision doit être entièrement traçable et reproductible.
