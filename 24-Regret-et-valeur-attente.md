---

title: "Regret et valeur de l'attente"
description: "Arbitrage entre le gain potentiel d'attendre et le risque de rupture, formalisé par le regret attendu et la valeur de l'attente."
version: "1.0"
--------------

# Regret et valeur de l'attente

## 1. Objet

Ce document définit le mécanisme central de la décision d'achat temporelle : l'arbitrage entre attendre une meilleure offre et acheter maintenant.

Il combine les données de prix (`22-Temporalite-des-prix.md`) et de disponibilité (`23-Disponibilite-et-substituabilite.md`) pour produire une décision robuste, qui ne recherche ni le prix minimum absolu, ni l'achat immédiat systématique.

Toutes les règles générales du guide restent applicables.

---

# 2. Gain potentiel d'attente

## 2.1 Définition

```text
G_attente(c, t) = économie raisonnablement espérable si l'on attend
                 = prix actuel − meilleur prix raisonnablement espéré
```

Le meilleur prix raisonnablement espéré n'est pas le minimum absolu théorique. Il est estimé à partir de l'historique de la référence, de sa volatilité et de la proximité d'évènements commerciaux connus.

## 2.2 Exemple

Prix actuel : 1 199 €.

Meilleur prix raisonnablement espéré : 1 149 €.

`G_attente` ≈ 50 €.

---

# 3. Les deux regrets

Il existe deux formes de regret, symétriques et opposées.

## 3.1 Regret d'achat trop précoce

L'utilisateur achète à 1 199 €. Le lendemain, le prix descend à 1 099 €.

Regret : 100 €.

## 3.2 Regret d'attente

L'utilisateur refuse 1 199 €. Le produit disparaît. Il doit finalement acheter à 1 399 €.

Regret : 200 €.

## 3.3 Objectif du moteur

Le moteur ne cherche pas à minimiser le prix payé. Il cherche à minimiser le **regret attendu** de la décision, c'est-à-dire l'espérance du regret compte tenu de l'incertitude sur l'évolution du prix et de la disponibilité.

Cette formulation correspond beaucoup plus fidèlement au problème réel que la recherche du prix minimum : elle intègre explicitement le risque de ne jamais revoir l'offre.

---

# 4. Valeur de l'attente

## 4.1 Définition

Le moteur compare la valeur d'attendre à la valeur d'acheter maintenant :

```text
Valeur_attente = gain potentiel d'attente
                − risque de rupture (probabilité de perte × C_sub)
                − coût de substitution pondéré par le risque
                − risque de hausse (probabilité que le prix remonte avant tout achat)
```

Les termes de risque (probabilité de perte, risque de hausse) sont dérivés du niveau de `R_dispo` défini en `23-Disponibilite-et-substituabilite.md` : un niveau qualitatif (faible / moyen / élevé / critique) est converti en une pondération croissante appliquée aux coûts potentiels.

## 4.2 Règle de décision

```text
Si Valeur_attente < 0  →  ACHETER
Si Valeur_attente ≥ 0  →  ATTENDRE (sous réserve de la priorité d'achat, voir 25-Dependances-et-priorite-achat.md)
```

Lorsque la valeur de l'attente devient négative, le moteur recommande l'achat même si le prix actuel n'est pas le minimum théorique. C'est un changement fondamental par rapport à une logique de recherche du prix plancher.

## 4.3 Exemple

Attendre peut rapporter 50 € (`G_attente`).

Attendre peut coûter 200 € si l'offre disparaît (`C_sub` d'une alternative nettement moins bonne), avec un risque de disponibilité jugé élevé.

Dans cette situation, `Valeur_attente` est négative : acheter devient rationnel, même si le marché pourrait théoriquement descendre encore.

---

# 5. Loi des rendements décroissants — règle anti-perfectionnisme

Une fois qu'une offre entre suffisamment profondément dans la zone verte (`22-Temporalite-des-prix.md`), le bénéfice marginal d'attendre encore devient faible, tandis que le risque de rupture ne diminue pas.

> Plus une offre approche du prix optimal, moins il est rationnel de risquer sa disparition pour chercher les derniers pourcents d'économie.

## 5.1 Scénario à éviter

```text
1 400 € → attendre
1 300 € → attendre
1 220 € → attendre
1 180 € → attendre
rupture
achat finalement réalisé à 1 350 €
```

Ce scénario illustre un regret d'attente cumulatif : chaque refus successif, pris isolément, semblait rationnel, mais la somme des refus a fini par coûter plus cher que n'importe lequel des prix refusés.

## 5.2 Application

Le moteur doit recalculer `Valeur_attente` à chaque scan, et non se contenter de comparer le prix actuel au prix cible initial. Une offre déjà en zone verte profonde, avec un risque de disponibilité non négligeable, doit voir sa `Valeur_attente` décroître mécaniquement au fil des refus successifs, jusqu'à devenir négative.

---

# 6. Interaction avec la substituabilité

Le regret d'attente n'a de sens que rapporté au coût de substitution défini en `23-Disponibilite-et-substituabilite.md`.

* Substituabilité élevée → `C_sub` faible → le regret d'attente maximal est plafonné bas → l'attente reste peu risquée même en cas de rupture.
* Substituabilité faible → `C_sub` élevé → le regret d'attente peut devenir très supérieur au gain potentiel d'attente → l'achat devient rapidement préférable dès que le risque de disponibilité n'est plus faible.

---

# 7. Limites et incertitude

`G_attente` et `Valeur_attente` reposent sur des estimations, pas sur des certitudes. Conformément aux niveaux de confiance définis en `00-Objet-et-perimetre.md` (section 8) :

* un « meilleur prix raisonnablement espéré » fondé sur un historique long et stable est de niveau B ou C ;
* un « meilleur prix raisonnablement espéré » fondé sur une rumeur de promotion à venir est de niveau D, et ne doit peser que faiblement dans la décision.

Une décision d'achat ne doit jamais reposer uniquement sur une hypothèse de niveau D.

---

# 8. Traçabilité

Pour chaque décision d'achat ou d'attente, le rapport doit conserver :

* `G_attente` et la méthode d'estimation du meilleur prix raisonnablement espéré ;
* le regret estimé dans les deux scénarios (achat précoce / attente ayant échoué) ;
* `Valeur_attente` et le détail de ses quatre termes ;
* la décision retenue et son motif explicite.

---

# 9. Principe final

Le moteur ne recherche pas le prix minimum. Il recherche la décision qui minimise le regret attendu, en tenant compte à la fois de ce que l'attente peut rapporter et de ce qu'elle peut coûter si la solution devient inaccessible. Une décision d'achat n'est rationnelle que si elle reste défendable dans les deux scénarios : celui où le prix aurait continué de baisser, et celui où l'offre aurait disparu.
