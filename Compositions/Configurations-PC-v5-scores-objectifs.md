# Rapport v5 — 5 configurations immersives (central ultra-large + latéraux cohérents)

**Nouvel axe :** expérience immersive. Poste 3 écrans avec **central ultra-large (21:9)** et **deux latéraux intégrés au design** — pas trois ultra-larges alignés, mais des latéraux qui appartiennent visuellement au même ensemble (règle « pas deux pizzas à côté d'un gâteau »).

> v5 conserve tout l'acquis (v1–v4 : composition, scoring mission, acquisition) et applique une **transition arrière S8 → S1** : le format du central change la résolution cible, donc le dimensionnement GPU et le budget. Prix = niveau C, modèles = PROVISOIRE.

---

## 1. Sous-système d'affichage immersif

### 1.1 Le central — deux formats retenus

| Format | Résolution | PPI | Rafraîch. | Charge GPU vs 4K | Usage | Estim. € |
|---|---|---|---|---|---|---|
| **34" QD-OLED courbé** | 3440×1440 (UWQHD) | ~110 | 165–240 Hz | **plus légère** (~4,95 M px) | immersion + jeu + créa, sweet spot | ~1000 |
| **39" 5K2K WOLED** (LG GX9) | 5120×2160 | ~143 | 165 Hz (dual 330) | **plus lourde** (~11 M px) | canvas créa + immersion premium | ~1800 |

À proscrire : 45" en 3440×1440 (netteté dégradée), 38" en 3840×1600 (rafraîchissement bas).

### 1.2 La règle de cohérence des latéraux (le cœur de la demande)

Un latéral « hors sujet » casse l'ensemble. Un **indice de cohérence visuelle** valide chaque trio sur cinq critères :

1. **Marque / série commune** — même langage de design (cadre, pied, finition, RGB). Latéraux issus de la même gamme que le central.
2. **Cohérence de dalle** — éviter d'accoler une dalle bas de gamme à un OLED. *Astuce fonctionnelle :* central **OLED** (immersion/jeu/média) + latéraux **IPS haut de gamme de la même marque** — cohérent visuellement **et** immunisé contre le marquage (burn-in) sur le contenu statique (code, doc, terminaux) qu'on affiche des heures. Le meilleur des deux mondes.
3. **Cohérence dimensionnelle** — un 27" 16:9 (~336 mm de haut) aligne presque ses bords avec un 34" 21:9 (~365 mm). Pour un 39" (~420 mm), préférer des latéraux 27" surélevés/centrés ou des 32".
4. **Courbure / angle** — central courbé (800R) + latéraux angulés ~30–40° vers l'intérieur = cockpit enveloppant.
5. **Support unifié** — bras triple ou pieds assortis pour un ensemble net et intégré.

### 1.3 Trios cohérents candidats (PROVISOIRE)

| Trio | Central | Latéraux (même famille) | Estim. € |
|---|---|---|---|
| **Valeur-cohérent** | 34" QD-OLED (ex. Alienware AW3425DW / MSI 341CQR / ASUS PG34WCDN) | 2× 27" QHD **IPS** même marque (anti-burn-in) | ~1450 |
| **Premium-OLED** | 34" QD-OLED | 2× 27" QHD **OLED** même série | ~1950 |
| **Créa 5K2K** | 39" 5K2K WOLED (LG UltraGear GX9) | 2× 27" QHD LG UltraGear | ~2350 |

*Haut-parleurs inclus (intégrés ou kit 2.0). Sorties : central OLED haute fréquence en **DisplayPort 2.1**, latéraux en DP/HDMI 2.1 — le GPU (3× DP 2.1 + HDMI 2.1) suffit. VESA 100×100 sur les trois → bras triple.*

### 1.4 Effet immersion + création
Le 21:9 courbé élargit le champ de vision (immersion jeu) **et** offre une timeline très large pour Premiere, un grand canvas Blender/Photoshop. Le 5K2K ajoute une densité « créa » supérieure. Nouveau sous-axe **Immersion/Expérience** intégré à l'ergonomie du scoring.

---

## 2. Transition arrière S8 → S1 (résolution ↔ GPU)

| Choix central | Conséquence GPU | Configs renforcées |
|---|---|---|
| 34" UWQHD (3440×1440) | plus léger que 4K → 5070 Ti/5080 très confortables, 120–165 fps natif atteignable | **C1, C2** |
| 39" 5K2K (5120×2160) | plus lourd que 4K → 5080 mini (avec DLSS), 5090 pour du natif haute fréquence | C3, C5 |

**Interaction budgétaire clé :** le trio immersif premium (1450–2350 €) entre en concurrence directe avec le GPU. Comme l'UWQHD rend le GPU « valeur » suffisant, **économiser sur le GPU finance l'immersion** — synergie qui favorise nettement les profils équilibrés/valeur.

---

## 3. Les 5 configurations immersives

Tour identique à la v3/v4 ; seule la ligne écrans change (+ effets GPU/budget). Réserve recalculée.

### C1-I Équilibrée immersive
5080 · 64 Go · Trio **Valeur-cohérent** (34" QD-OLED + 2× 27" IPS assortis)
- Tour ~3820 + écrans 1450 + périph 275 = **~5545 €** · **Réserve ~455 €**
- UWQHD 34" : le 5080 sort 100–165 fps natif, immersion pleine. Latéraux IPS anti-burn-in pour le dev.

### C2-I Value durable immersive ★ sweet spot immersion
5070 Ti · 64 Go · Trio **Premium-OLED** (34" QD-OLED + 2× 27" QHD OLED même série)
- Tour ~3370 + écrans 1950 + périph 275 = **~5595 €** · **Réserve ~405 €**
- L'économie GPU (5070 Ti, parfaitement à l'aise en UWQHD) **finance le trio OLED intégral**. Immersion maximale, cohérence parfaite, budget maîtrisé. *Variante réserve : Trio Valeur-cohérent → ~5095 €, réserve ~905 €.*

### C3-I Création-canvas immersive
5080 · 32 Go · Trio **Créa 5K2K** (39" 5K2K WOLED + 2× 27" QHD assortis)
- Tour ~3340 + écrans 2350 + périph 200 = **~5890 €** · **Réserve ~110 €**
- **Pivot imposé par l'immersion :** le 5K2K (canvas créa idéal) + un 5090 dépasse 6000 € → on retient le **5080** (qui pilote le 5K2K avec DLSS) plutôt que le 5090. La création gagne le canvas ; la VRAM 16 Go reste le maillon faible (upgrade GPU prévu).

### C4-I Silence immersive
5080 (UV) · 64 Go · Trio **Valeur-cohérent** · alim Platinum semi-passive · boîtier insonorisé · NH-D15 G2
- Tour ~3900 + écrans 1450 + périph 275 = **~5625 €** · **Réserve ~375 €**
- Cockpit immersif **et** cible < 25 dBA. Latéraux IPS = zéro burn-in en usage bureautique prolongé.

### C5-I Perf max immersive (plafond)
5090 · **32 Go** (imposé) · Trio **Valeur-cohérent** · gamme éco ailleurs
- Tour (5090, 32 Go) ~4500 + écrans 1450 + périph éco 200 = **~6150 €** → **ajustements requis** (stockage 2 To, périph éco) pour rentrer ≈ 6000 € · **Réserve ~0**
- **Constat :** 5090 + 64 Go + trio immersif ne rentre pas dans 6000 €. L'immersion **force le 32 Go** et une réserve nulle. L'axe immersion aggrave la fragilité déjà connue de C5.

---

## 4. Effet de l'axe immersion sur le classement

| Config | Immersion | Cohérence visuelle | Réserve | Lecture |
|---|---|---|---|---|
| C1-I | ★★★★ | ★★★★ | 455 | solide |
| **C2-I** | **★★★★★** | **★★★★★** | 405 | **immersion max à budget maîtrisé** |
| C3-I | ★★★★★ (canvas) | ★★★★ | 110 | spécialisé créa, réserve mince |
| C4-I | ★★★★ | ★★★★ | 375 | immersion + silence |
| C5-I | ★★★★ | ★★★★ | ~0 | plafond fragile, 32 Go imposé |

**Résultat cohérent avec les vagues précédentes :** l'immersion **renforce C2/C1** (l'UWQHD rend le GPU valeur suffisant, ce qui finance des écrans premium cohérents) et **contraint davantage C3/C5** (5K2K/5090 poussent le budget hors limite). Le sweet spot immersion pour *ta* mission et *ton* budget est **C2-I** : 5070 Ti pleinement à l'aise en 34" UWQHD, ce qui libère de quoi offrir un trio OLED parfaitement cohérent.

---

## 5. Lecture acquisition du trio (rappel moteur `21`–`29`)

- **Substituabilité :** l'exigence de cohérence de série **abaisse légèrement** `S` des latéraux (on veut la même famille) → surveiller la **disponibilité conjointe** central + latéraux. Pas de risque de rupture, mais le Black Friday est la **fenêtre de remise** idéale pour les écrans.
- **Priorité :** écrans = criticité structurelle nulle → sécurisés **après** GPU/CPU/RAM, mais le central OLED (modèle précis, valeur élevée) mérite d'être pris **dès une zone verte** au BF plutôt qu'attendu.
- **Cohérence d'abord :** ne pas « dépareiller » sous prétexte d'une promo isolée sur un latéral d'une autre marque — la cohérence visuelle prime sur une petite économie (sinon : deux pizzas et un gâteau).

---

## 6. Synthèse & prochaine étape

La vague immersive ne bouleverse pas le classement : elle le **confirme**. Le central ultra-large courbé + latéraux de même famille (idéalement OLED central / IPS latéraux pour le confort et l'anti-burn-in) crée le cockpit voulu, et parce que l'UWQHD est plus léger que la 4K, **le chemin valeur (C2) devient aussi le chemin immersion**.

Recommandation immersive : **C2-I** (immersion maximale, cohérence parfaite, budget tenu), ou **C4-I** si le silence reste prioritaire, ou **C3-I** si le canvas 5K2K créa prime.

Pour la suite (quand tu voudras reprendre) : figer **une config-cible immersive**, puis lancer la **phase de scan** pour instancier les zones de prix réelles du trio choisi et des composants structurants, avant la boucle d'achat du Black Friday.