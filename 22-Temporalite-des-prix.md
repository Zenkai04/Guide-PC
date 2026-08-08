---

title: "Temporalité des prix"
description: "Définition du prix comme variable temporelle et des quatre zones de décision utilisées pour qualifier une offre à un instant donné."
version: "1.0"
--------------

# Temporalité des prix

## 1. Objet

Ce document définit la manière dont le moteur d'acquisition représente le prix d'un composant.

Dans le moteur de composition, un composant est représenté essentiellement par ses caractéristiques et son prix, considéré comme une valeur unique.

Cette représentation est insuffisante pour décider **quand** acheter. Le moteur d'acquisition a besoin de savoir si un prix observé est bon, médiocre ou exceptionnel par rapport à l'historique de la référence.

Toutes les règles générales du guide restent applicables.

---

# 2. Le prix comme variable temporelle

Pour toute référence candidate `c`, le prix n'est plus une constante mais une fonction du temps :

```text
P(c, t) = prix du composant c au moment t
```

Cette fonction n'est jamais connue à l'avance. Elle est reconstruite progressivement à partir des observations successives réalisées lors des scans du marché (`29-Algorithme-acquisition-marche.md`).

---

# 3. Données conservées par référence

Pour chaque référence candidate, le moteur conserve :

* prix actuel ;
* prix de référence (prix habituel constaté hors promotion) ;
* meilleur prix observé (minimum historique connu) ;
* historique des prix ;
* variation récente (tendance à court terme) ;
* réduction réelle (écart entre prix actuel et prix de référence) ;
* date de l'observation.

Ces données transforment une affirmation peu exploitable :

> « Ce produit coûte 1 199 €. »

en une information directement utile à la décision :

> « Ce produit coûte 1 199 €, contre 1 399 € habituellement, et son minimum observé est 1 169 €. »

---

# 4. Fiabilité du prix de référence

Le prix de référence ne doit pas être déduit d'une seule source commerciale.

Le moteur doit privilégier :

* un prix de référence construit sur une période suffisamment longue ;
* plusieurs vendeurs lorsque cela est possible ;
* la distinction entre un prix barré affiché par un vendeur et un prix habituellement pratiqué sur le marché.

Un prix barré n'est pas une preuve de réduction réelle. Il doit être recoupé avec l'historique observé de la référence avant d'être utilisé dans une décision.

---

# 5. Quatre zones de prix

Un unique prix cible est trop simpliste pour piloter une décision d'achat. Chaque référence reçoit désormais quatre zones, définies à partir de son historique et de sa valeur normale de marché.

## Zone rouge — Attendre

Le prix n'est pas suffisamment intéressant. Aucune pression d'achat.

## Zone orange — Acceptable

Le prix est correct mais ne justifie pas encore nécessairement l'achat à lui seul.

## Zone verte — Bon achat

Le prix est suffisamment intéressant pour acheter si les autres conditions sont réunies (voir `23-Disponibilite-et-substituabilite.md` et `24-Regret-et-valeur-attente.md`).

## Zone vert foncé — Opportunité

Le prix est exceptionnel. L'achat doit généralement être déclenché immédiatement, sous réserve des garde-fous définis en `29-Algorithme-acquisition-marche.md`.

---

# 6. Exemple

| RTX 5080 candidate | Zone | Décision |
| ------------------: | :--: | -------- |
| > 1 350 € | 🔴 | Attendre |
| 1 250 – 1 350 € | 🟠 | Acceptable |
| 1 150 – 1 250 € | 🟢 | Bon achat |
| < 1 150 € | 🟢🟢 | Opportunité |

Les valeurs exactes de ces seuils sont propres à chaque référence. Elles doivent être établies à partir du marché réel observé, et non fixées arbitrairement.

---

# 7. Détermination des seuils

Les quatre seuils sont établis à partir :

* du prix de référence de la mission ;
* du minimum historique observé ;
* de la volatilité récente de la référence ;
* de la proximité d'un évènement commercial connu (Black Friday, soldes) ;
* du niveau de confiance attribué aux données disponibles (`00-Objet-et-perimetre.md`, section 8).

Les seuils doivent être documentés et traçables au même titre que toute autre donnée d'entrée du moteur. Un seuil fixé sans historique suffisant doit être signalé comme une estimation de niveau C ou D.

---

# 8. Réévaluation des seuils

Les seuils ne sont pas figés pour toute la durée de la campagne d'achat.

Ils sont recalculés :

* lorsqu'un nouveau minimum historique est observé ;
* lorsque le prix de référence évolue durablement ;
* lors de chaque recalcul complet (`28-Configurations-secours-et-checkpoints.md`).

Une opportunité observée aujourd'hui peut redevenir une zone orange demain si le marché révèle un prix encore plus bas — et inversement, un prix orange peut devenir une opportunité si le marché se durcit.

---

# 9. Limite de la zone de prix seule

La zone de prix ne constitue qu'une des entrées de la décision d'achat.

Elle ne doit jamais, à elle seule, déclencher un achat sans tenir compte :

* du risque de disponibilité (`23-Disponibilite-et-substituabilite.md`) ;
* du regret attendu (`24-Regret-et-valeur-attente.md`) ;
* de la priorité d'achat du composant (`25-Dependances-et-priorite-achat.md`) ;
* de l'état du budget immobilisé (`27-Budget-immobilise-et-risque-configuration.md`).

Une référence en zone rouge peut malgré tout devenir prioritaire si sa substituabilité est très faible et son risque de rupture élevé. Une référence en zone vert foncé peut ne pas justifier un achat immédiat si elle ne présente aucun risque de disponibilité et qu'elle reste régulièrement observée à ce niveau.

---

# 10. Principe final

Le prix n'est utile à la décision que rapporté à son histoire.

Un prix ne se juge pas dans l'absolu, mais par rapport à ce que la référence a coûté, à ce qu'elle coûte habituellement, et à ce qu'elle a coûté au plus bas. La zone de prix donne une lecture immédiate de cette position, mais elle ne constitue qu'un des éléments — jamais l'unique élément — de la décision d'achat.
