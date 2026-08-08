# Rapport v4 — 5 configurations × moteur d'acquisition

**Mission :** émulation, ingénierie info (compilation, VMs, multi-agents, indus.), gaming AAA 4K 120+, modding, création (Blender, Photoshop, Premiere).
**Budget max :** 6000 €. **Achat :** campagne autour du Black Friday 2026. **Réutilisé :** licence Windows.

> Cette vague **n'annule pas** la v3 (moteur de composition). Elle applique par-dessus le **moteur d'acquisition** (`21`–`29`) : le *quoi* reste, on ajoute le *quand / comment sécuriser*. Prix et seuils = niveau **C/D**, à calibrer sur le marché observé.

---

## 0. Ce que la couche d'acquisition ajoute

| Mécanisme (doc) | Intégration v4 |
|---|---|
| Temporalité des prix — 4 zones (`22`) | Zones 🔴🟠🟢🟢🟢 par référence clé (§2, §4) |
| Disponibilité & substituabilité (`23`) | `R_dispo` **système** + `S` + `C_sub` par composant (§2) |
| Regret & valeur d'attente (`24`) | `Valeur_attente` → décision ATTENDRE/ACHETER (§2, §5) |
| Dépendances & priorité (`25`) | Criticité structurelle → **ordre de sécurisation** (§3) |
| États commerciaux & C_switch (`26`) | Cycle CANDIDATE→…→SÉCURISÉE, « commandé ≠ verrouillé » (§6) |
| Budget immobilisé & R_incomplet (`27`) | Profil `R_incomplet` par config + garde-fous (§4, §7) |
| Secours & recomposition (`28`) | 5 configs = plans de secours + recompositions (§6) |
| Boucle & garde-fous (`29`) | Anti-FOMO / anti-perfectionnisme + checkpoints (§5, §8) |

---

## 1. Rappel : les 5 identités techniques (issues v3)

| | C1 Équilibrée | C2 Value | C3 Créa/IA | C4 Silence | C5 Perf max |
|---|---|---|---|---|---|
| GPU | RTX 5080 | RTX 5070 Ti | RTX 5090 | RTX 5080 (UV) | RTX 5090 |
| RAM | 64 Go | 64 Go | 32 Go (→64) | 64 Go | 64 Go |
| Total ≈ € | 5165 | 4715 | 5725 | 5245 | 5980 |
| Rang mission (v3) | 3ᵉ | **1ᵉ** | 4ᵉ | 2ᵉ | 5ᵉ |

CPU commun : **Ryzen 9 9950X3D** · plateforme **AM5** (support 2029).

---

## 2. Profil d'acquisition par composant (table partagée)

Les composants se répètent entre configs ; leur profil d'acquisition est mutualisé ici. `R_dispo` est **système** (calculé sur l'ensemble des références validées pour la fonction, pas sur une seule).

| Composant | Criticité struct. | Substituab. `S` | `C_sub` | `R_dispo` (BF) | Zones de prix (réf. → 🔴/🟠/🟢/🟢🟢) | Décision défaut BF |
|---|---|---|---|---|---|---|
| **GPU 5090** | **Élevée** | **Faible** | Élevé | **Élevé** | >2400 / 2250–2400 / 2100–2250 / <2100 | 🟢🟢+risque → **ACHETER IMMÉDIATEMENT** |
| **GPU 5080** | Élevée | Moyenne | Moyen | Moyen | >1300 / 1200–1300 / 1100–1200 / <1100 | 🟢 → ACHETER ; sinon SURVEILLER |
| **GPU 5070 Ti** | Élevée | **Élevée** | Faible | Faible | >950 / 880–950 / 800–880 / <800 | 🟢 → ACHETER (sans urgence) |
| **CPU 9950X3D** | Élevée | Moyenne | Moyen | Faible | >720 / 660–720 / 610–660 / <610 | 🟠/🟢 → ACHETER (structural) |
| **RAM 64 Go 6000** | Moyenne | Élevée | Faible | **Moyen ↑** | >920 / 850–920 / 800–850 / <800 | marché **haussier** → ACHETER dès 🟠 |
| **Carte mère X870/B850** | Moyenne | Moyenne | Moyen | Faible | selon réf. | 🟢 → ACHETER après CPU |
| **Alimentation** | Moyenne | Élevée | Faible | Faible | selon réf. | ACHETER après GPU (dimensionnement) |
| **Stockage NVMe** | Faible | **Élevée** | ~0 | Faible | >180 / 160–180 / 130–160 / <130 | opportuniste, peut attendre |
| **Refroid. / Boîtier** | Faible | Élevée | Faible | Faible | selon réf. | opportuniste |
| **Écrans (×3)** | Nulle | Élevée | Faible | Faible | selon réf. | fenêtre BF = bon moment, pas d'urgence |
| **Périphériques** | Nulle | Élevée | ~0 | Faible | selon réf. | dernier, opportuniste |

**Deux lectures d'acquisition majeures :**
- **RAM — anti-perfectionnisme actif.** Le marché DDR5 est haussier (crise jusqu'à fin 2027). Le « meilleur prix raisonnablement espéré » est ≥ prix actuel → `G_attente ≈ 0 ou négatif` → **attendre ne rapporte rien et peut coûter**. On sécurise dès la zone 🟠, sans chercher un 🟢🟢 qui ne viendra probablement pas.
- **5090 — anti-FOMO ET faible substituabilité.** Peu de modèles, pénurie GDDR7 : `S` faible, `C_sub` élevé. Un vrai 🟢🟢 + stock qui se tend = **ACHETER IMMÉDIATEMENT**. Mais « plus que 2 en stock » seul ne suffit pas (règle anti-FOMO `29`).

*Les seuils ci-dessus sont illustratifs (niveau C/D). Ils doivent être calibrés sur l'historique réel de chaque référence pendant la phase de scan (`22` §7).*

---

## 3. Ordre de sécurisation (priorité d'achat dynamique)

`Priorité = criticité × rareté × C_sub × qualité de l'offre × dépendances ÷ substituabilité`.

Ordre par défaut (recalculé à chaque checkpoint) :

1. **GPU** — criticité maximale (contraint boîtier + alim), plus gros levier prix, fenêtre BF = moment des remises. *Priorité d'autant plus haute que le tier est peu substituable (5090 ≫ 5070 Ti).*
2. **CPU 9950X3D** + **carte mère** — structural (socket fixe la plateforme) ; à sécuriser tôt, sans surpayer.
3. **RAM** — marché haussier → sécuriser dès une offre 🟠 correcte (la substituabilité élevée évite l'urgence, mais la tendance prix pousse à ne pas traîner).
4. **Alimentation** — après le GPU (pour dimensionner juste).
5. **Refroidissement / boîtier** — opportuniste.
6. **Stockage** — très substituable, `R_dispo` faible → peut être sécurisé **en dernier** au meilleur prix, sans risque de rupture.
7. **Écrans** — fenêtre BF favorable, mais aucun risque de rupture ; à saisir quand 🟢.
8. **Périphériques** — dernier, opportuniste.

---

## 4. Les 5 configurations — lecture acquisition

Pour chaque config : le **risque de configuration incomplète** (`R_incomplet`), la séquence d'achat, et les scénarios de marché qui la favorisent.

### C1 Équilibrée
- **R_incomplet : MOYEN.** Le 5080 est moyennement substituable ; RAM 64 à sécuriser tôt (marché haussier).
- **Séquence :** 5080 (dès 🟢) → CPU+X870 → RAM (dès 🟠) → alim → reste opportuniste.
- **Favorisée si :** 5080 entre en zone verte au BF.

### C2 Value durable
- **R_incomplet : FAIBLE (le plus bas).** 5070 Ti très substituable, 850 W et B850 abondants → config la **plus facile à compléter** au budget prévu. Grosse réserve = coussin contre les imprévus d'achat.
- **Séquence :** 5070 Ti (sans urgence, attendre 🟢) → RAM (dès 🟠) → CPU+B850 → reste très souple.
- **Favorisée si :** 5070 Ti fortement remisé (sa thèse) — passe alors « extrêmement attractive » (`28` §2.1).

### C3 Création / IA
- **R_incomplet : ÉLEVÉ.** 5090 peu substituable + `R_dispo` élevé à bon prix ; de plus la RAM 32→64 crée une **seconde acquisition différée** en marché haussier (mauvais timing). Réserve mince → peu de marge d'immobilisation.
- **Séquence :** 5090 **prioritaire et agressive** (ACHETER IMMÉDIATEMENT si 🟢🟢) → CPU+X870E → RAM 32 → reste comprimé.
- **Favorisée si :** 5090 exceptionnellement remisé (`28` §2.1) — bascule alors depuis C1.

### C4 Silence
- **R_incomplet : MOYEN.** Comme C1 côté GPU ; alim Platinum et boîtier insonorisé un peu moins abondants mais substituables.
- **Séquence :** identique à C1, + surveiller les références silencieuses (NH-D15 G2, boîtier amorti) qui ne sont pas des goulots.
- **Favorisée si :** priorité acoustique confirmée par tes pondérations.

### C5 Perf max
- **R_incomplet : LE PLUS ÉLEVÉ.** 5090 peu substituable **et** réserve ≈ 0 : la moindre hausse ou rupture casse le budget. Risque de **budget immobilisé** si l'on tente le mécanisme « commandé ≠ verrouillé » sur un 5090 (>2000 € bloqués).
- **Séquence :** 5090 en tout premier, puis tout le reste en gamme éco sécurisé vite (aucune marge pour attendre).
- **Statut :** étude de cas du plafond — l'acquisition **aggrave** sa fragilité déjà notée en v3.

---

## 5. Décisions par défaut au Black Friday (synthèse)

| Composant | Si zone atteinte au BF | Action |
|---|---|---|
| GPU visé | 🟢🟢 + stock tendu + `S` faible | **ACHETER IMMÉDIATEMENT** |
| GPU visé | 🟢 | ACHETER |
| GPU visé | 🟠 | SURVEILLER PRIORITAIREMENT |
| CPU / carte mère | 🟠–🟢 | ACHETER (structural, ne pas surpayer) |
| RAM 64 Go | 🟠 ou mieux | **ACHETER** (marché haussier, anti-perfectionnisme) |
| Stockage / périph. | 🟢–🟢🟢 | ACHETER ; sinon ATTENDRE (aucun risque) |
| Écrans | 🟢 | ACHETER (fenêtre BF) |

Garde-fous : un simple « stock faible » ne déclenche jamais seul un achat (anti-FOMO) ; une offre déjà 🟢 profonde avec risque non nul ne se refuse pas indéfiniment pour grappiller (anti-perfectionnisme).

---

## 6. Plans de secours & recomposition

Les 5 configs sont des **plans de secours** interchangeables selon le marché, pas une config + 4 curiosités.

| Scénario de marché | Effet | Config activée |
|---|---|---|
| A — 5090 en 🟢🟢 exceptionnel | C1/C3 gagnent, l'écart de prix fond | bascule vers **C3** (ou C5 si budget) |
| B — 5070 Ti fortement bradé | meilleur rapport encore renforcé | **C2** devient dominante |
| C — DDR5 se détend | 64 Go redevient accessible | **C3** peut restaurer 64 Go |
| D — offres éparses | meilleurs prix répartis sur plusieurs configs | **recomposition** ci-dessous |

**Recomposition (`28` §3) — exemple `C-BF` :** piocher parmi les 5 le meilleur composant *disponible et bien prixé* à l'instant t (ex. GPU au tarif de C1 + carte mère au tarif de C2 + alim au tarif de C4), **à condition** que compatibilités (`16`), budget max (`04`) et score ≥ configs candidates soient respectés. Sinon la recomposition est rejetée sans être proposée.

---

## 7. Plan de checkpoints autour du Black Friday

| Niveau | Fréquence | Rôle |
|---|---|---|
| **Scan** | élevée (avant BF) | construire l'historique prix/stock par référence, poser les zones réelles |
| **Recalcul incrémental** | sur changement significatif | nouvelle zone atteinte, `R_dispo` qui monte, promo, seuil budget |
| **Recalcul complet** | ouverture BF, Cyber Monday, échéance campagne | recalcul des 5 configs + recompositions + priorités + décisions d'achat |

Séquence type : **scanner 2–4 semaines avant** pour calibrer les zones (sinon les seuils restent niveau D) → à l'ouverture du BF, **sécuriser d'abord le GPU et le CPU**, **la RAM dès une offre correcte**, puis les composants substituables au fil de leurs propres bonnes offres.

---

## 8. Garde-fous budget immobilisé & R_incomplet

- **Budget disponible = total − dépensé − engagé + remboursements confirmés.** Ne jamais immobiliser un budget nécessaire à un composant **plus prioritaire** (typiquement le GPU).
- **Ne pas optimiser au détriment de la complétude.** Une config complète à 6250 € tous composants satisfaisants > une tentative à 6050 € qui échoue à sécuriser le GPU et finit à 6500 €.
- **« Commandé ≠ verrouillé »** : on peut remplacer un achat par une meilleure offre **seulement si** `gain > C_switch + marge` (coût financier + logistique + risque + temps). Sur un 5090, l'immobilisation temporaire (>2000 €) rend ce mécanisme rarement rentable.

---

## 9. Synthèse — classement enrichi

| | C1 | C2 | C3 | C4 | C5 |
|---|---|---|---|---|---|
| Score mission (v3) | 75,2 | **78,8** | 72,1 | 77,6 | 67,2 |
| Robustesse d'acquisition (R_incomplet inversé) | 78 | **92** | 55 | 78 | 48 |
| **Lecture combinée** | solide | **la plus sûre** | risquée à l'achat | solide+silence | fragile |

**Conclusion.** La couche d'acquisition **renforce le verdict v3** au lieu de le contredire : **C2** est à la fois la mieux classée sur la mission et la plus facile à sécuriser réellement (GPU très substituable, `R_incomplet` faible, réserve-coussin). **C4** reste le second solide. **C3/C5** portent désormais un risque supplémentaire — non plus seulement budgétaire, mais **d'acquisition** (5090 peu substituable, réserve mince, achat différé de RAM en marché haussier).

**Prochaine étape :** figer **une config cible** (défaut recommandé : **C2**, ou **C4** si le silence prime) puis lancer la **phase de scan** pour calibrer les zones de prix réelles des références de cette config, avant d'entrer dans la boucle d'achat du Black Friday. Je peux préparer la **liste de références à surveiller** (avec zones à instancier) pour la config que tu choisis.