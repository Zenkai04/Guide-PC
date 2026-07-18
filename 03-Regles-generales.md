# Règles générales

## 1. Objet

Ce document définit les règles universelles applicables à toute décision prise par le moteur de sélection.

Ces règles sont indépendantes des composants.

Elles constituent le référentiel de décision de l'ensemble du guide.

Aucune règle spécifique à un composant ne peut les contredire.

---

# 2. Principes fondamentaux

Toute décision doit respecter les principes suivants.

## Règle 1 — La mission est prioritaire

La sélection d'un composant doit toujours être justifiée par la mission du système.

Une caractéristique sans utilité pour la mission ne constitue pas un avantage.

---

## Règle 2 — Les contraintes priment sur les préférences

Les contraintes obligatoires doivent être satisfaites avant toute optimisation.

Une préférence utilisateur ne peut jamais justifier une violation d'une contrainte technique ou fonctionnelle.

---

## Règle 3 — Les critères éliminatoires sont absolus

Tout composant qui ne satisfait pas un critère éliminatoire est rejeté.

Il ne participe ni à la notation ni au classement.

---

## Règle 4 — La compatibilité est obligatoire

Un composant performant mais incompatible est considéré comme inutilisable.

La compatibilité doit être vérifiée avant toute comparaison de performances.

---

## Règle 5 — Une mesure prévaut sur une caractéristique

Lorsqu'une mesure fiable est disponible, elle est prioritaire sur une caractéristique constructeur.

Exemple :

Une fréquence plus élevée n'implique pas automatiquement une meilleure performance.

---

## Règle 6 — Une métrique prévaut sur une valeur isolée

Une donnée brute ne suffit pas à comparer deux composants.

Les comparaisons doivent utiliser des métriques adaptées.

Exemple :

Performance/€

Performance/W

Coût annuel

Latence réelle

---

## Règle 7 — Les hypothèses ne sont jamais des faits

Toute information non vérifiée doit être identifiée comme une hypothèse.

Une décision importante ne doit pas reposer uniquement sur une hypothèse.

---

## Règle 8 — Les optimisations ne doivent jamais dégrader une exigence

Toute optimisation doit préserver les exigences obligatoires.

Une réduction du coût ne justifie pas une perte de fonctionnalité indispensable.

---

## Règle 9 — La simplicité est préférable à complexité équivalente

Deux solutions apportant le même résultat doivent être départagées en faveur de la plus simple à installer, maintenir et faire évoluer.

---

## Règle 10 — Toute décision doit être justifiable

Chaque décision doit pouvoir être expliquée à partir :

* des données d'entrée ;
* des règles appliquées ;
* des mesures ;
* des métriques calculées.

---

# 3. Classification des informations

Toute information utilisée par le moteur appartient à une seule catégorie.

## 3.1 Caractéristique

Information déclarée par le constructeur.

Exemples :

* fréquence ;
* capacité ;
* nombre de cœurs.

---

## 3.2 Mesure

Information issue d'un essai reproductible.

Exemples :

* consommation réelle ;
* FPS ;
* température.

---

## 3.3 Vérification

Résultat d'un contrôle logique.

Exemples :

* socket compatible ;
* hauteur suffisante ;
* connecteur présent.

Résultats possibles :

* Validé
* Rejeté
* Inconnu

---

## 3.4 Métrique

Valeur calculée.

Exemples :

Performance/€

Performance/W

Coût/Téraoctet

Latence réelle

---

## 3.5 Estimation

Valeur calculée à partir d'hypothèses.

Toujours identifiée comme telle.

---

## 3.6 Hypothèse

Information non garantie.

Elle ne doit jamais être présentée comme une certitude.

---

# 4. Hiérarchie des critères

Les critères sont évalués dans l'ordre suivant.

```text
Critères éliminatoires

↓

Critères de validation

↓

Critères de compatibilité

↓

Critères économiques

↓

Critères d'optimisation

↓

Critères de confort
```

Un niveau ne peut jamais compenser l'échec d'un niveau supérieur.

---

# 5. Règles de rejet

Un composant est immédiatement rejeté si :

* une exigence obligatoire n'est pas satisfaite ;
* une incompatibilité est détectée ;
* le budget maximal est dépassé sans alternative ;
* une performance minimale n'est pas atteinte ;
* une capacité minimale est insuffisante ;
* une contrainte physique est violée.

Les composants rejetés ne reçoivent aucune note.

---

# 6. Règles de validation

Un composant valide doit :

* satisfaire tous les critères éliminatoires ;
* satisfaire les exigences fonctionnelles ;
* être compatible avec les autres composants ;
* respecter les contraintes.

La validation est binaire.

---

# 7. Règles de notation

La notation ne concerne que les composants validés.

Chaque composant reçoit plusieurs notes indépendantes.

Exemples :

* adéquation à la mission ;
* performance utile ;
* coût ;
* efficacité énergétique ;
* évolutivité ;
* fiabilité ;
* maintenabilité ;
* bruit.

Les notes ne remplacent jamais les vérifications.

---

# 8. Règles de comparaison

Deux composants ne peuvent être comparés que si :

* ils remplissent la même fonction ;
* ils sont compatibles avec la même configuration ;
* leurs mesures sont comparables ;
* les protocoles de mesure sont compatibles.

Une comparaison de mesures obtenues dans des conditions différentes doit être signalée.

---

# 9. Règles économiques

Le composant le moins cher n'est pas automatiquement le meilleur.

Le composant le plus performant ne l'est pas davantage.

Le coût doit toujours être rapporté au bénéfice utile.

Le guide privilégie les métriques telles que :

* Performance/€
* Performance/W
* Coût total de possession
* Coût annuel
* Gain par euro investi

---

# 10. Règles d'évolutivité

L'évolutivité est évaluée selon :

* les possibilités techniques ;
* le coût futur des mises à niveau ;
* la disponibilité probable des composants ;
* la durée de support de la plateforme ;
* les besoins futurs plausibles.

Une évolutivité inutile ne justifie pas un surcoût important.

---

# 11. Règles de confiance

Chaque information utilisée par le moteur doit être associée à un niveau de confiance.

| Niveau | Signification                                  |
| ------ | ---------------------------------------------- |
| A      | Vérifié par mesure ou documentation officielle |
| B      | Confirmé par plusieurs sources cohérentes      |
| C      | Estimation raisonnable                         |
| D      | Hypothèse ou prévision                         |

Les critères éliminatoires doivent s'appuyer en priorité sur des données de niveau A ou B.

---

# 12. Règles d'incertitude

Lorsqu'une information est incertaine :

* son origine doit être précisée ;
* son impact potentiel doit être évalué ;
* la décision doit rester robuste si cette hypothèse est infirmée.

Une décision fragile doit être signalée dans le rapport final.

---

# 13. Règles de cohérence système

Chaque composant est évalué individuellement puis collectivement.

La configuration finale doit être cohérente sur les plans :

* électrique ;
* thermique ;
* mécanique ;
* logiciel ;
* économique ;
* fonctionnel.

Une incohérence globale peut invalider une configuration composée uniquement de composants individuellement valides.

---

# 14. Règles de traçabilité

Toute décision doit être traçable.

Le moteur doit être capable d'indiquer :

* les données d'entrée utilisées ;
* les règles appliquées ;
* les mesures retenues ;
* les métriques calculées ;
* les alternatives écartées ;
* la justification finale.

Aucune décision ne doit dépendre d'une préférence implicite ou d'une opinion non documentée.

---

# 15. Règles de reproductibilité

À données d'entrée identiques et à règles identiques, le moteur doit produire le même résultat.

Toute variation de résultat doit pouvoir être expliquée par :

* une modification des données d'entrée ;
* une mise à jour des mesures ;
* une évolution des règles ;
* une évolution des prix ou de la disponibilité.

---

# 16. Règles de neutralité

Le moteur ne doit favoriser :

* aucune marque ;
* aucun constructeur ;
* aucune architecture ;
* aucune technologie.

Les décisions doivent être fondées exclusivement sur les critères définis dans le guide.

---

# 17. Règles de robustesse

Une décision est dite robuste lorsqu'une variation modérée :

* du budget ;
* des prix ;
* des performances ;
* ou des besoins

ne conduit pas immédiatement à une configuration totalement différente.

Le moteur doit privilégier les solutions robustes lorsque plusieurs solutions présentent des performances comparables.

---

# 18. Règle de gain significatif

Un surcoût n'est justifié que si le bénéfice est mesurable et pertinent pour la mission.

À titre indicatif :

* gain < 10 % : généralement insuffisant ;
* gain entre 10 % et 20 % : à analyser ;
* gain entre 20 % et 40 % : significatif ;
* gain supérieur à 40 % : évolution majeure.

Ces seuils ne remplacent jamais l'analyse du contexte.

---

# 19. Règle de performance utile

Le moteur privilégie la performance utile.

Une amélioration n'a de valeur que si elle est observable dans les usages définis.

Les performances théoriques ne doivent jamais être utilisées seules pour justifier un choix.

---

# 20. Règle finale

La meilleure configuration n'est ni la moins chère ni la plus performante.

C'est celle qui satisfait la mission, respecte toutes les contraintes, présente un coût justifié, reste cohérente au niveau du système et conserve une capacité d'évolution adaptée à sa durée de vie prévue.
