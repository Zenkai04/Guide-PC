---

title: "Budget immobilisé et risque de configuration incomplète"
description: "Suivi du budget engagé pendant la campagne d'achat et évaluation du risque de ne pas parvenir à compléter une configuration viable."
version: "1.0"
--------------

# Budget immobilisé et risque de configuration incomplète

## 1. Objet

Ce document définit deux mécanismes de contrôle nécessaires dès qu'une configuration de plusieurs milliers d'euros est achetée progressivement, sur plusieurs jours ou semaines, plutôt qu'en une seule opération :

* le suivi du budget immobilisé, qui empêche la stratégie d'achat de devenir financièrement absurde ;
* le risque de configuration incomplète, qui empêche d'optimiser des économies partielles sur une configuration qui ne pourra pas être terminée dans les conditions prévues.

Toutes les règles générales du guide restent applicables, en particulier les principes définis en `04-Budget-et-allocation.md`.

---

# 2. Budget immobilisé

## 2.1 Pourquoi ce suivi est nécessaire

Le mécanisme décrit en `26-Etats-commerciaux-et-cycle-achat.md` (commandé ne signifie pas verrouillé) peut conduire à immobiliser temporairement plus d'argent que le budget ne semble le suggérer : par exemple lorsqu'un composant est acheté une seconde fois en attendant le remboursement du premier achat.

Sans suivi explicite, cette immobilisation temporaire peut empêcher de saisir une autre opportunité, y compris sur un composant plus prioritaire.

## 2.2 Grandeurs suivies

Le moteur suit en continu :

* budget total disponible ;
* budget dépensé (achats sécurisés, sans possibilité de remboursement) ;
* budget engagé (commandes passées mais encore susceptibles d'annulation ou de remboursement) ;
* remboursements en attente ;
* budget encore réellement disponible.

```text
budget disponible = budget total
                   − budget dépensé
                   − budget engagé
                   + remboursements en attente confirmés
```

## 2.3 Effet sur la décision d'achat

Une décision d'achat (`ACHAT RECOMMANDÉ` ou `ACHAT URGENT`, `26-Etats-commerciaux-et-cycle-achat.md`) ne peut être exécutée que si le budget encore réellement disponible le permet. Un composant prioritaire mais dont l'achat immobiliserait un budget nécessaire à un composant encore plus prioritaire ne doit pas être acheté en premier.

## 2.4 Exemple

L'achat temporaire de deux GPU (l'un en attente de retour) peut immobiliser plus de 2 000 €. Si cette immobilisation empêche de saisir une promotion exceptionnelle sur un autre composant structurant, le moteur doit refuser ou différer l'immobilisation, sauf si le gain attendu du remplacement du GPU dépasse largement le coût d'opportunité constaté sur les autres composants.

---

# 3. Risque de configuration incomplète

## 3.1 Définition

```text
R_incomplet = risque de ne pas parvenir à compléter une configuration viable
```

Ce risque global est celui qui motive l'ensemble du moteur d'acquisition : il ne sert à rien d'optimiser le prix de chaque composant individuellement si le résultat final est une configuration qui ne peut pas être terminée dans les conditions prévues.

## 3.2 Exemple

CPU, RAM, SSD et écrans achetés à d'excellents prix : 400 € économisés au total. Mais aucun GPU acceptable n'est resté disponible.

Le résultat n'est pas une configuration économisée. C'est un ordinateur qui ne peut pas être terminé dans les conditions prévues.

## 3.3 Facteurs d'évaluation

`R_incomplet` augmente avec :

* le nombre de composants structurants (criticité structurelle élevée, `25-Dependances-et-priorite-achat.md`) encore non sécurisés ;
* le niveau de risque de disponibilité (`R_dispo`, `23-Disponibilite-et-substituabilite.md`) de ces composants encore non sécurisés ;
* la faible substituabilité de ces mêmes composants ;
* la proximité de la date limite de la campagne d'achat, lorsqu'elle existe.

## 3.4 Vérification progressive

Plus le nombre de composants déjà achetés augmente, plus il devient nécessaire de vérifier que les composants structurants restants demeurent accessibles. Un achat de composants secondaires ne doit jamais faire perdre de vue l'état d'accès aux composants structurants encore en attente.

Cette vérification est réalisée à chaque recalcul incrémental et à chaque recalcul complet (`28-Configurations-secours-et-checkpoints.md`).

## 3.5 Effet sur la priorité d'achat

Lorsque `R_incomplet` devient significatif pour un composant structurant encore non sécurisé, sa priorité d'achat (`25-Dependances-et-priorite-achat.md`) doit être augmentée, même si son prix actuel n'est pas optimal. Terminer la configuration devient alors plus important que continuer à optimiser son coût.

---

# 4. Arbitrage entre économie et complétude

Le moteur doit être capable de refuser une économie apparente lorsqu'elle augmente `R_incomplet` de manière disproportionnée.

## 4.1 Exemple

Une configuration complète à 6 250 €, dont tous les composants sont satisfaisants, est potentiellement une meilleure décision qu'une tentative d'atteindre 6 050 € qui échoue à sécuriser deux composants critiques et se termine finalement à 6 500 € par manque d'alternative.

Cet arbitrage découle directement de la fonction objectif du moteur d'acquisition définie en `21-Moteur-dacquisition.md`.

---

# 5. Traçabilité

Le rapport d'acquisition conserve à tout moment :

* l'état complet du budget (total, dépensé, engagé, remboursements en attente, disponible) ;
* la valeur de `R_incomplet` et son évolution au fil de la campagne ;
* les composants structurants encore non sécurisés et leur risque de disponibilité respectif ;
* toute décision d'achat motivée principalement par `R_incomplet` plutôt que par le prix.

---

# 6. Principe final

Une campagne d'achat n'est pas réussie parce qu'elle a minimisé chaque prix pris isolément. Elle est réussie lorsqu'elle produit une configuration complète et viable, avec un budget resté sous contrôle à chaque étape. Le suivi du budget immobilisé empêche la stratégie de sécurisation de devenir financièrement incohérente ; le risque de configuration incomplète empêche l'optimisation locale de compromettre l'objectif global.
