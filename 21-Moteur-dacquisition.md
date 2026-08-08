---

title: "Moteur d'acquisition"
description: "Positionnement, philosophie et principes du moteur d'exécution temporelle du marché, qui détermine quand acheter les composants retenus par le moteur de conception."
version: "1.0"
--------------

# Moteur d'acquisition

## 1. Objet

Ce document introduit un second moteur, qui s'ajoute au moteur de conception décrit dans les documents précédents.

Le moteur de conception répond à une première question :

> Quelle configuration constitue le meilleur choix ?

Le moteur d'acquisition répond à une seconde question, différente :

> Sachant ce que nous voulons acheter, quand faut-il effectivement déclencher l'achat ?

Ce moteur constitue la couche d'exécution temporelle du marché.

Il ne remplace ni ne modifie le moteur de conception. Il s'exécute après lui, en boucle, jusqu'à ce que tous les achats nécessaires soient sécurisés.

---

# 2. Ce qui ne change pas

Le cœur de l'algorithme défini dans les documents `00` à `20` reste intact.

On conserve intégralement la chaîne :

```text
Besoin → mission → contraintes → critères éliminatoires → candidats
→ compatibilités → dimensionnement → mesures → interactions
→ budget → notation → Pareto → configurations candidates
→ rapport de décision
```

C'est toujours ce moteur qui détermine **quoi** acheter.

Aucune règle définie dans les documents `01` à `20` n'est contredite ou remplacée par les documents `21` à `29`. En cas de conflit apparent, les règles générales (`03-Regles-generales.md`) priment.

---

# 3. Ce qui s'ajoute

Une fois les configurations candidates produites, un second moteur prend le relais et fonctionne en boucle jusqu'à ce que tous les achats soient sécurisés :

```text
Moteur de conception → configurations candidates → moteur d'exécution du marché → achats
```

Ce second moteur introduit :

* une dimension temporelle du prix (`22-Temporalite-des-prix.md`) ;
* un risque de disponibilité et une substituabilité (`23-Disponibilite-et-substituabilite.md`) ;
* un arbitrage entre gain d'attente et regret (`24-Regret-et-valeur-attente.md`) ;
* une priorité d'achat dynamique fondée sur les dépendances (`25-Dependances-et-priorite-achat.md`) ;
* un cycle de vie commercial des références, distinct du cycle de conception (`26-Etats-commerciaux-et-cycle-achat.md`) ;
* un suivi du budget immobilisé et du risque de configuration incomplète (`27-Budget-immobilise-et-risque-configuration.md`) ;
* une utilisation des cinq configurations candidates comme plans de secours et matière première d'une recomposition (`28-Configurations-secours-et-checkpoints.md`) ;
* une boucle d'exécution complète, avec ses garde-fous (`29-Algorithme-acquisition-marche.md`).

---

# 4. Trois moteurs successifs

Le guide comporte désormais trois moteurs.

## 4.1 Moteur d'ingénierie

> De quoi ai-je réellement besoin ?

Documents `01` à `03`.

---

## 4.2 Moteur de composition

> Quelle combinaison de composants répond le mieux à ce besoin ?

Documents `04` à `20`.

---

## 4.3 Moteur d'acquisition

> Quand et chez qui dois-je acheter chaque composant pour obtenir cette configuration avec un coût et un risque acceptables ?

Documents `21` à `29`.

---

Ce troisième moteur résout un conflit que les deux premiers ne traitent pas : acheter trop tôt produit un risque de regret ; acheter trop tard produit un risque de rupture. L'objectif du moteur d'acquisition est de trouver le point rationnel entre les deux, plutôt que d'essayer de deviner le point bas du marché.

---

# 5. Pourquoi un troisième moteur est nécessaire

Le moteur de composition traite les composants comme s'ils étaient disponibles à un prix fixe et à un instant donné.

Cette hypothèse est correcte pour concevoir une configuration. Elle devient fausse dès qu'il faut l'acheter réellement, en particulier lors de périodes de forte volatilité commerciale (Black Friday, soldes, ruptures saisonnières).

Sur un marché réel :

* le prix d'une référence varie dans le temps ;
* le stock d'une référence varie dans le temps ;
* la disparition d'une référence n'est pas toujours annoncée ;
* deux références équivalentes ne disparaissent pas nécessairement au même rythme ;
* un achat n'est pas toujours irréversible immédiatement après la commande.

Ignorer ces phénomènes conduit à deux erreurs symétriques :

* acheter trop tôt, et payer plus cher qu'il n'était nécessaire ;
* attendre trop longtemps, et perdre l'accès à une solution acceptable.

Le moteur d'acquisition existe pour arbitrer rationnellement entre ces deux erreurs.

---

# 6. Fonction objectif

## 6.1 Fonction objectif du moteur de composition

Avant l'extension, le moteur cherchait essentiellement à :

> Maximiser la qualité de la configuration sous contrainte budgétaire.

## 6.2 Fonction objectif du moteur d'acquisition

Le moteur d'acquisition cherche à :

> Maximiser la qualité finale de la configuration et l'économie obtenue, tout en minimisant le risque de rupture, le risque de configuration incomplète et le regret d'achat.

Le prix minimum absolu n'est donc plus l'objectif poursuivi.

Une configuration complète dont tous les composants sont satisfaisants est potentiellement une meilleure décision qu'une tentative d'atteindre le prix théorique le plus bas qui échoue parce que deux offres critiques ont été manquées.

---

# 7. Nouvelle définition d'une bonne affaire

Avant l'extension, une bonne affaire pouvait être assimilée au prix le plus bas observé.

Cette définition est insuffisante : elle ignore le risque de ne jamais revoir l'offre.

Le moteur d'acquisition retient la définition suivante.

> Une bonne affaire est un prix suffisamment inférieur à la valeur normale du produit pour que le gain potentiel d'attendre davantage ne justifie plus le risque de perdre l'opportunité.

Cette définition relie explicitement le prix, le temps et le risque. Elle est développée dans `24-Regret-et-valeur-attente.md`.

---

# 8. Principe final

Le moteur de conception détermine quoi acheter.

Le moteur d'acquisition détermine quand acheter, chez qui, et à quel moment il devient déraisonnable de continuer à attendre.

Un système de sélection de composants qui ne répond qu'à la première question reste incomplet pour tout achat réalisé dans des conditions de marché volatiles : il expose l'utilisateur soit à un regret d'achat trop précoce, soit à un risque de rupture. Le moteur d'acquisition existe pour rendre ce second arbitrage aussi explicite, traçable et reproductible que le premier.
