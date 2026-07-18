# Stratégie de durée de vie

## 1. Objet

Ce document définit la méthode permettant de concevoir une configuration informatique en tenant compte de sa durée de vie prévue et de son évolution dans le temps.

L'objectif n'est pas de maximiser les performances au moment de l'achat.

L'objectif est de maximiser la valeur créée pendant toute la durée d'utilisation du système.

La stratégie de durée de vie influence directement :

* le choix des composants ;
* l'allocation du budget ;
* les possibilités d'évolution ;
* le coût total de possession ;
* le calendrier des mises à niveau.

---

# 2. Principes fondamentaux

## Principe 1 — Le système évolue

Un ordinateur n'est pas un objet figé.

Pendant sa durée de vie, les besoins, les logiciels, les performances requises, les prix et les technologies évoluent.

La stratégie doit intégrer cette évolution.

---

## Principe 2 — Les composants vieillissent différemment

Tous les composants ne deviennent pas obsolètes au même rythme.

Chaque famille de composants possède son propre cycle de vie.

---

## Principe 3 — La plateforme est plus durable que certains composants

La plateforme (boîtier, alimentation, carte mère selon les cas) est généralement conçue pour durer plus longtemps que les composants soumis aux plus fortes évolutions technologiques.

Le guide doit privilégier les investissements durables lorsque cela est économiquement justifié.

---

## Principe 4 — Une mise à niveau est une stratégie

L'objectif n'est pas forcément d'acheter immédiatement le composant le plus performant.

Dans certains cas, acheter un composant intermédiaire puis prévoir son remplacement est plus rentable.

---

# 3. Les différentes durées de vie

Le guide distingue plusieurs notions.

## Durée de fonctionnement

Temps pendant lequel le composant reste opérationnel.

---

## Durée de pertinence

Temps pendant lequel le composant reste adapté à la mission.

---

## Durée de support

Temps pendant lequel le constructeur ou l'écosystème assurent encore :

* pilotes ;
* mises à jour ;
* correctifs ;
* compatibilité logicielle.

---

## Durée économique

Temps pendant lequel conserver le composant reste plus rentable que le remplacer.

---

## Durée stratégique

Période prévue par l'utilisateur avant un remplacement volontaire.

---

# 4. Classification des composants

Les composants ne sont pas conçus pour être conservés pendant la même durée.

Le moteur doit tenir compte de cette différence.

## Très longue durée

Exemples :

* boîtier ;
* écran ;
* certains systèmes de refroidissement ;
* certains périphériques.

Ces composants peuvent être réutilisés sur plusieurs générations de machines.

---

## Longue durée

Exemples :

* alimentation de qualité ;
* stockage secondaire ;
* certains SSD ;
* certains ventirads.

---

## Durée moyenne

Exemples :

* carte mère ;
* processeur ;
* mémoire.

La durée dépend fortement de l'évolution des plateformes.

---

## Durée courte

Exemples :

* carte graphique dans une machine de jeu ;
* SSD système soumis à de fortes écritures.

---

# 5. Obsolescence

Le moteur distingue plusieurs formes d'obsolescence.

## Obsolescence fonctionnelle

Le composant ne permet plus de réaliser la mission.

---

## Obsolescence technique

Le composant fonctionne mais n'est plus compatible avec les technologies nécessaires.

---

## Obsolescence économique

Le coût de conservation devient supérieur au bénéfice.

---

## Obsolescence logicielle

Le support logiciel disparaît.

---

## Obsolescence énergétique

La consommation devient disproportionnée.

---

# 6. Évolutivité

Une possibilité d'évolution est pertinente uniquement si :

* elle est techniquement réalisable ;
* son coût futur est raisonnable ;
* elle répond à un besoin plausible ;
* elle est compatible avec la stratégie globale.

Une évolution théorique ne constitue pas une valeur en soi.

---

# 7. Marges de sécurité

Le moteur doit déterminer des marges adaptées.

Exemples :

* puissance de l'alimentation ;
* capacité mémoire ;
* stockage disponible ;
* capacité thermique.

Une marge insuffisante réduit la durée de vie.

Une marge excessive peut représenter un gaspillage.

---

# 8. Planification des mises à niveau

Lorsque des évolutions sont prévues, elles doivent être planifiées.

Pour chaque évolution :

* composant concerné ;
* période estimée ;
* déclencheur ;
* coût estimé ;
* impact attendu.

Exemple :

```text id="j5m1we"
Année 0 : Configuration initiale

↓

Année 3 : Ajout de RAM

↓

Année 5 : Remplacement du GPU

↓

Année 8 : Ajout de stockage

↓

Année 10 : Remplacement de la plateforme
```

---

# 9. Déclencheurs de remplacement

Un remplacement ne doit pas être déclenché uniquement par la sortie d'une nouvelle génération.

Les déclencheurs peuvent être :

* performances insuffisantes ;
* panne ;
* coût énergétique ;
* incompatibilité ;
* nouveau besoin ;
* coût de maintenance.

---

# 10. Analyse du coût sur le cycle de vie

Le moteur doit comparer plusieurs stratégies.

Exemple :

Stratégie A :

Configuration très haut de gamme conservée dix ans.

---

Stratégie B :

Configuration intermédiaire avec remplacement du GPU à mi-parcours.

---

Stratégie C :

Configuration plus économique avec deux évolutions majeures.

Le choix dépend du coût total et de la valeur créée.

---

# 11. Réutilisation

Avant toute acquisition, le moteur doit identifier les composants pouvant être conservés.

Exemples :

* boîtier ;
* alimentation ;
* SSD ;
* écrans ;
* périphériques.

La réutilisation est prioritaire lorsqu'elle ne dégrade pas la mission.

---

# 12. Gestion des risques

Le moteur doit évaluer :

* risque d'obsolescence rapide ;
* risque de fin de support ;
* risque de changement de plateforme ;
* risque de pénurie ;
* risque d'incompatibilité future.

Les risques doivent être signalés dans le rapport final.

---

# 13. Horizon de décision

Toutes les décisions ne sont pas prises avec le même horizon.

## Court terme

0 à 2 ans

---

## Moyen terme

2 à 5 ans

---

## Long terme

5 à 10 ans

Le moteur doit préciser l'horizon auquel se rapporte chaque recommandation.

---

# 14. Coût d'évolution

Chaque stratégie doit intégrer le coût des évolutions futures.

Exemples :

* remplacement d'un GPU ;
* ajout de mémoire ;
* changement de carte mère ;
* remplacement d'un SSD.

Le coût d'achat initial ne suffit jamais à comparer deux stratégies.

---

# 15. Robustesse

Une stratégie est robuste lorsqu'elle reste pertinente malgré :

* une augmentation des besoins ;
* une baisse du budget futur ;
* une évolution des logiciels ;
* une variation des prix.

Le moteur doit privilégier les stratégies robustes lorsque leur coût reste raisonnable.

---

# 16. Réversibilité

Une décision est réversible lorsqu'elle permet une modification ultérieure à faible coût.

Exemples :

* ajout de mémoire ;
* ajout de stockage ;
* remplacement d'un GPU.

Une décision irréversible doit être justifiée.

---

# 17. Coût d'anticipation

Anticiper un besoin futur peut être rentable.

Cependant, une anticipation excessive peut immobiliser inutilement du budget.

Le moteur doit rechercher le meilleur équilibre entre :

* anticipation ;
* flexibilité ;
* coût.

---

# 18. Valeur résiduelle

Le moteur peut prendre en compte :

* valeur de revente ;
* possibilité de réemploi ;
* compatibilité avec une future configuration.

La valeur résiduelle contribue au coût total de possession.

---

# 19. Indicateurs

Le moteur peut calculer notamment :

* coût annuel moyen ;
* coût par année utile ;
* coût d'évolution ;
* durée de pertinence estimée ;
* indice de réutilisation ;
* indice d'obsolescence ;
* indice d'évolutivité ;
* indice de robustesse.

Ces indicateurs permettent de comparer plusieurs stratégies de cycle de vie.

---

# 20. Traçabilité

Le rapport final doit expliquer :

* pourquoi certains composants sont prévus pour durer longtemps ;
* lesquels sont considérés comme évolutifs ;
* lesquels sont susceptibles d'être remplacés ;
* à quel moment ;
* pour quelles raisons.

---

# 21. Principe final

La meilleure stratégie n'est pas celle qui maximise les performances au moment de l'achat.

C'est celle qui fournit le meilleur équilibre entre :

* performances utiles ;
* coût total sur la durée de vie ;
* facilité d'évolution ;
* maîtrise des risques ;
* réutilisation des composants ;
* adaptation aux besoins futurs.

Une stratégie est considérée comme optimale lorsqu'elle minimise le coût global de possession tout en maintenant le niveau de service attendu pendant toute la durée de vie prévue du système.
