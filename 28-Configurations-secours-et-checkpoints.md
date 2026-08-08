---

title: "Configurations de secours et checkpoints"
description: "Utilisation des configurations candidates comme plans de secours, recomposition automatique, et trois niveaux de recalcul du marché."
version: "1.0"
--------------

# Configurations de secours et checkpoints

## 1. Objet

Ce document définit deux mécanismes qui exploitent directement le résultat du moteur de composition pendant la campagne d'achat :

* l'usage des configurations candidates comme plans de secours, et non comme une configuration unique accompagnée de curiosités ;
* la fréquence à laquelle le moteur doit recalculer l'état du marché, sans recalculer inutilement ce qui n'a pas changé.

Toutes les règles générales du guide restent applicables.

---

# 2. Les configurations candidates sont des plans de secours

Le moteur de composition ne produit pas une configuration accompagnée de quatre curiosités. Il produit cinq architectures validées, chacune cohérente au niveau système (`16-Compatibilites-et-interactions.md`) et positionnée sur le front de Pareto (`17-Notation-et-classement.md`, `18-Algorithme-global.md`).

Le moteur d'acquisition doit exploiter cette richesse plutôt que de s'attacher exclusivement à la configuration la mieux classée au moment initial.

## 2.1 Exemple — bascule entre configurations

```text
RTX 5080 chère
RTX 5090 exceptionnellement remisée
   ↓
la configuration C1 perd de l'intérêt
   ↓
la configuration C3 peut devenir meilleure
```

```text
RTX 5070 Ti en forte promotion
   ↓
la configuration C2 devient extrêmement attractive
```

## 2.2 Conséquence

À chaque checkpoint de recalcul complet (section 4.3), le moteur recalcule les cinq configurations candidates avec les prix, stocks et risques observés à cet instant, exactement comme le ferait le moteur de composition avec des données de marché mises à jour. L'utilisateur n'est jamais prisonnier de la configuration initialement la mieux classée.

---

# 3. Recomposition automatique

Le moteur peut aller plus loin que le simple choix entre les cinq configurations existantes : il peut produire une configuration temporaire, composée des meilleurs choix compatibles disponibles à l'instant `t`, en piochant parmi les cinq configurations candidates.

## 3.1 Exemple

* C1 possède le meilleur CPU et la meilleure RAM.
* C4 possède une alimentation exceptionnellement remisée.
* C2 possède une carte mère devenue imbattable.

Le moteur peut produire une configuration recomposée, par exemple nommée `C1-BF-03`, combinant ces éléments, sous réserve que toutes les vérifications de compatibilité et d'interactions définies en `16-Compatibilites-et-interactions.md` restent satisfaites.

## 3.2 Condition de validité

Une configuration recomposée n'est retenue que si elle :

* respecte toutes les vérifications de compatibilité et d'interactions ;
* respecte le budget maximal (`04-Budget-et-allocation.md`) ;
* obtient un score global au moins équivalent à celui des cinq configurations candidates initiales, dans les conditions de marché actuelles.

Une configuration recomposée qui ne satisfait pas ces trois conditions est rejetée sans être proposée.

## 3.3 Conséquence conceptuelle

Les cinq configurations candidates constituent des points de départ, pas des carcans. Elles délimitent l'espace des combinaisons jugées cohérentes par le moteur de composition ; le moteur d'acquisition explore cet espace en fonction de l'état réel du marché, sans jamais en sortir.

---

# 4. Trois niveaux de checkpoint

Recalculer l'intégralité du moteur (composition et acquisition) à chaque heure serait à la fois coûteux et inutile lorsque rien de significatif n'a changé. Le moteur d'acquisition distingue trois niveaux de recalcul.

## 4.1 Scan

Très rapide. Exécuté à haute fréquence.

Vérifie :

* prix ;
* stock ;
* nouvelles promotions.

Ne déclenche aucun recalcul de configuration. Sert uniquement à détecter si un changement significatif justifie un recalcul incrémental.

## 4.2 Recalcul incrémental

Déclenché lorsqu'une variable surveillée change de façon significative (nouvelle zone de prix atteinte, changement de niveau de `R_dispo`, disparition d'une référence, franchissement d'un seuil de budget).

Recalcule uniquement :

* le composant concerné ;
* ses alternatives directes ;
* l'état du budget ;
* le score des configurations qui incluent ce composant ;
* les dépendances directement affectées.

## 4.3 Recalcul complet

Exécuté aux moments stratégiques (ouverture d'un évènement commercial, fréquence minimale garantie, ou accumulation de changements incrémentaux significatifs).

Recalcule :

* toutes les références surveillées ;
* les cinq configurations candidates ;
* les éventuelles configurations recomposées ;
* le front de Pareto (`17-Notation-et-classement.md`) ;
* le classement de priorité d'achat (`25-Dependances-et-priorite-achat.md`) ;
* la décision d'achat pour chaque composant encore non sécurisé.

## 4.4 Règle d'arbitrage

```text
Scan
  ↓ (changement significatif détecté)
Recalcul incrémental
  ↓ (accumulation de changements, ou échéance stratégique)
Recalcul complet
```

Le moteur doit éviter de refaire inutilement l'ensemble du calcul à chaque scan. Un scan qui ne détecte aucun changement significatif ne déclenche rien de plus.

---

# 5. Traçabilité

Le rapport d'acquisition conserve :

* l'horodatage et le niveau (scan, incrémental, complet) de chaque recalcul ;
* le motif ayant déclenché chaque recalcul incrémental ou complet ;
* toute configuration recomposée produite, avec sa composition et son score ;
* l'évolution du classement des cinq configurations candidates au fil des recalculs complets.

---

# 6. Principe final

Les cinq configurations produites par le moteur de composition ne sont pas un résultat figé au moment de la conception. Elles constituent un espace de solutions valides que le moteur d'acquisition continue d'exploiter, de comparer et, si nécessaire, de recomposer tant que le marché évolue. La fréquence de recalcul doit être proportionnée à l'ampleur du changement détecté, jamais uniforme dans le temps.
