# Rapport de décision — Configuration PC

**Mission :** émulation (PS3/Switch/…), ingénierie informatique (compilation, VMs, systèmes multi-agents, logiciels industriels), gaming AAA 4K 120 fps+, modding, création (Blender, Photoshop, Premiere Pro).
**Budget maximal :** 6000 € (tour + 3 écrans avec haut-parleurs + clavier mécanique + souris filaire USB + casque filaire USB + webcam).
**Horizon :** 5–7 ans sans changer les composants, 10 ans avec upgrades.
**Fenêtre d'achat :** Black Friday 2026.

> **Note de confiance (échelle du guide).** Les faits d'architecture, de socket et les benchmarks sont de niveau **A/B**. **Tous les prix sont des estimations de niveau C** — marché de mi-2026, en euros, dans un contexte de pénurie mémoire. Ils doivent être revérifiés au moment de l'achat. La pénurie DDR5/GDDR7/NAND rend le marché volatil ; le Black Friday n'apportera probablement pas de forte baisse sur la RAM ni sur les GPU haut de gamme.

---

## 1. Contraintes exogènes du marché (mi-2026)

Ces éléments s'imposent à toutes les configurations et orientent la stratégie.

- **Crise mémoire.** DDR5 à ~4–5× le prix d'avant-pénurie. Kit 2×32 Go (64 Go) ≈ 850–900 € en Europe ; 2×16 Go (32 Go) ≈ 330–450 €. Répit non attendu avant fin 2027. Cause : bascule de la production vers la HBM pour l'IA.
- **SSD/NAND.** Hausse réelle mais plus modérée (+20–40 % sur 2026). Moins pénalisant que la RAM.
- **GPU.** Série RTX 50 (Blackwell) sous pression de prix via la GDDR7 ; le RTX 5090 dépasse souvent son tarif officiel en Europe.
- **Refresh « Super » (24 Go).** Statut incertain (repoussé fin 2026 / CES 2027, voire annulé selon les sources). À surveiller, mais **on ne peut pas planifier dessus** pour un achat Black Friday 2026.
- **Socket AM5.** Support constructeur confirmé **jusqu'en 2029** (Zen 6 « Olympic Ridge », voire Zen 7). C'est le socle de ta longévité : upgrade CPU à mi-vie possible **sans changer de carte mère**.

**Implication stratégique :** cette année, chaque euro non dépensé sur la RAM/GPU peut être réinvesti plus tard, à prix normalisé. La réserve budgétaire n'est pas un luxe, c'est un levier.

---

## 2. Déroulé de l'automate — états partagés

Rappel du contrat : on ne passe à l'état suivant qu'une fois l'état courant **verrouillé** (mission satisfaite, critères éliminatoires passés, confiance ≥ B, aucune bifurcation ouverte). Un retour arrière est autorisé si une contrainte aval l'impose.

### S0 — CPU — **VERROUILLÉ**

**AMD Ryzen 9 9950X3D** (16C/32T, AM5, 128 Mo L3 via 3D V-Cache). Confiance **B**.
Justification : productivité à parité avec le 9950X non-X3D (la pénalité de latence de l'ancienne génération a disparu) ; en 4K le jeu est limité par le GPU donc l'écart X3D y est marginal ; **le surcoût (~75 €) est justifié par l'émulation** (RPCS3/Switch, limitées par le CPU et très sensibles au cache) qui est explicitement dans la mission. Plateforme AM5 → chemin d'upgrade Zen 6/7 jusqu'en 2029.
*Ce composant est identique dans les 5 configurations.*

### S1 — GPU — bifurcation (point de divergence des configs)

Contrainte quasi-éliminatoire : **CUDA** (Blender OptiX, Premiere, IA locale). Trois candidats retenus :

| Modèle | VRAM | Points clés | Estim. € (C) |
|---|---|---|---|
| RTX 5070 Ti | 16 Go GDDR7 | Excellent rapport perf/prix, 4K avec DLSS 4, VRAM = plancher confortable | ~850–1000 |
| RTX 5080 | 16 Go GDDR7 | ~75–80 % du 5090 en jeu, 4K120 solide | ~1150–1300 |
| RTX 5090 | 32 Go GDDR7 | 4K120 natif, **VRAM énorme** pour Blender/Premiere/IA locale et longévité | ~2200–2500 |

**Analyse.** La VRAM est le facteur qui « périme » un GPU le plus vite pour la création et l'IA. 16 Go est suffisant pour le jeu 4K aujourd'hui et confortable en création à court terme ; 32 Go achète de la **durée de pertinence** pour tes usages Blender/Premiere/IA. Mais le 5090 consomme à lui seul ~40 % du budget dans ce marché, ce qui force des compromis ailleurs. Comme tu prévois de toute façon un upgrade GPU vers l'année 5, un GPU 16 Go + grosse réserve est une stratégie défendable ; un 5090 32 Go maintenant l'est aussi si tu veux repousser cet upgrade. **Il n'y a pas de réponse unique : c'est le curseur qui définit tes profils de config.**

### S2 — Carte mère

Chipset AM5. Choix selon la config :
- **B850** : suffisant, PCIe 5.0 sur le slot GPU et un M.2, bon VRM sur les bons modèles. Meilleur rapport valeur/longévité si l'on n'a pas besoin de connectique extrême. ~180–280 €.
- **X870 / X870E** : plus de lignes PCIe 5.0, plus de M.2, USB4, meilleur pour le stockage multiple et l'évolutivité. ~300–450 €.
Critère de longévité : **VRM robuste + BIOS Flashback + au moins 3 slots M.2** pour absorber tes bibliothèques (émulation, jeux, projets vidéo, VMs). 4 slots DIMM (capacité 128–256 Go) obligatoire pour l'évolutivité RAM.

### S3 — RAM — décision structurée par la crise

Cible mission : **64 Go** (VMs + Blender + Premiere + compilation simultanées). Mais 64 Go ≈ 880 € aujourd'hui.
- **Acheter 64 Go maintenant (2×32)** : couvre la mission, évite le mélange de modules ultérieur (risque doc 09) et n'expose pas à une hausse future. Recommandé si la mission l'exige vraiment dès le départ.
- **Acheter 32 Go maintenant (2×32 impossible → 2×16), ajouter plus tard** : libère ~480 € pour le GPU, mais l'ajout futur reste cher jusqu'en 2028 et sur AM5 passer à 4 barrettes peut réduire la fréquence stable. Compromis, pas idéal.
Spécification : **DDR5-6000 CL30, kit 2 barrettes** (dual-channel optimal sur AM5, EXPO).

### S4 — Stockage

Architecture recommandée : **NVMe Gen4 système (2 To)** + **NVMe Gen4 données (2 To)**, slots M.2 restants libres pour extension. TLC avec DRAM (éviter QLC/DRAM-less pour l'endurance vu tes écritures : VMs, montage, gros transferts). Dissipateur M.2 obligatoire pour éviter le throttling.

### S5 — Alimentation

Dimensionnée pour le GPU **et** un futur GPU plus gourmand (marge d'évolutivité). ATX 3.1 / connecteur 12V-2×6 natif. Cible :
- 850 W Gold pour un 5070 Ti / 5080.
- 1000 W Gold/Platinum pour un 5090 (pics transitoires Blackwell).
Qualité (condensateurs, protections, garantie 10 ans) prioritaire sur le wattage brut.

### S6 — Refroidissement

Le 9950X3D est exigeant thermiquement. Options : **gros air haut de gamme** (silencieux, sans risque de pompe) ou **AIO 360** (marge thermique supérieure, utile si undervolting léger conservé). Undervolting léger recommandé (gratuit, réduit chaleur/bruit, sert la longévité) — cohérent avec ton « pose et oublie ».

### S7 — Boîtier

Bon flux d'air, compatible GPU long + AIO 360, 3 slots M.2 accessibles, filtres anti-poussière (ton environnement). Évolutif (baies libres). Version à panneaux amortis pour le profil silencieux.

### S8 — Écrans (3, haut-parleurs inclus)

- **Principal** : 4K, 120–144 Hz, IPS de qualité (ou OLED selon budget) — jeu 4K120 **et** travail colorimétrique (Premiere/Photoshop). Poste à ne pas sacrifier.
- **2 secondaires** : 1440p, ~100 Hz, pour dev, VMs, doc, monitoring. Pas besoin de 4K ni haute fréquence.
- **Haut-parleurs** : soit intégrés aux écrans, soit petit kit 2.0 dédié (meilleure qualité). Ligne incluse.

### S9 — Périphériques (de zéro)

Clavier mécanique, souris filaire USB, casque filaire USB, webcam pour visio. Composants « très longue durée » (doc 05) : investir raisonnablement une fois, réutiliser sur plusieurs machines.

---

## 3. Les 5 configurations

> Prix = estimations € niveau C (mi-2026), à revérifier au Black Friday. Tour = boîte seule ; total = tour + écrans + périphériques.

### Config 1 — « Cible équilibrée » ★ recommandée

Le meilleur compromis pour ton profil mixte : puissance création/jeu, 64 Go réels, réserve confortable.

| État | Composant | Estim. € |
|---|---|---|
| CPU | Ryzen 9 9950X3D | 680 |
| GPU | RTX 5080 16 Go | 1200 |
| Carte mère | X870 (ATX, 3× M.2) | 300 |
| RAM | 64 Go DDR5-6000 CL30 | 880 |
| Stockage | 2×2 To NVMe Gen4 (4 To) | 320 |
| Alim | 1000 W Gold ATX 3.1 | 190 |
| Refroidissement | AIO 360 | 150 |
| Boîtier | Airflow ATX évolutif | 130 |
| **Tour** | | **3850** |
| Écrans | 4K 144 Hz + 2×1440p + HP | 1070 |
| Périphériques | Clavier méca + souris + casque + webcam | 275 |
| **TOTAL** | | **≈ 5195** |
| **Réserve** | | **≈ 805** |

**Pourquoi :** 16 Go de VRAM couvrent le 4K120 et la création à court/moyen terme ; 64 Go réels sans compromis ; réserve pour l'upgrade GPU vers l'année 5. **Horizon :** 5–7 ans confortables, 10 avec upgrade GPU (+éventuellement RAM 128 Go quand les prix baissent).
**Risque principal :** 16 Go de VRAM pourraient limiter les très gros projets Blender/IA vers la fin de vie → compensé par l'upgrade planifié.

---

### Config 2 — « Value durable / réserve maximale »

Minimise l'exposition aux composants les plus surévalués (GPU haut de gamme), maximise la réserve pour racheter à prix normalisé. **La plus alignée avec ta stratégie 10 ans dans ce marché.**

| État | Composant | Estim. € |
|---|---|---|
| CPU | Ryzen 9 9950X3D | 680 |
| GPU | RTX 5070 Ti 16 Go | 900 |
| Carte mère | B850 (ATX, VRM solide, 3× M.2) | 220 |
| RAM | 64 Go DDR5-6000 CL30 | 880 |
| Stockage | 2×2 To NVMe Gen4 (4 To) | 320 |
| Alim | 850 W Gold ATX 3.1 | 150 |
| Refroidissement | Gros air haut de gamme | 100 |
| Boîtier | Airflow ATX évolutif | 110 |
| **Tour** | | **3360** |
| Écrans | 4K 144 Hz + 2×1440p + HP | 1070 |
| Périphériques | Clavier méca + souris + casque + webcam | 275 |
| **TOTAL** | | **≈ 4705** |
| **Réserve** | | **≈ 1295** |

**Pourquoi :** le 5070 Ti gère le 4K avec DLSS 4 et la création CUDA aujourd'hui ; la grosse réserve (~1300 €) finance un upgrade GPU en 2027–2028 quand la gamme suivante / le refresh 24 Go sera disponible et les prix plus sains. Tu profites deux fois du marché : peu exposé maintenant, mieux servi plus tard.
**Horizon :** upgrade GPU anticipé (année 3–4 plutôt que 5), plateforme conservée 10 ans.
**Risque :** le 5070 Ti sera le premier à montrer ses limites en 4K natif sur les AAA futurs → assumé, c'est le principe.

---

### Config 3 — « Création & IA / VRAM maximale »

Priorité à la VRAM pour Blender, Premiere et IA locale, au prix d'un compromis RAM imposé par la crise.

| État | Composant | Estim. € |
|---|---|---|
| CPU | Ryzen 9 9950X3D | 680 |
| GPU | **RTX 5090 32 Go** | 2300 |
| Carte mère | X870E (ATX, 4× M.2, USB4) | 360 |
| RAM | **32 Go** DDR5-6000 (→ +32 Go plus tard) | 400 |
| Stockage | 2×2 To NVMe Gen4 (4 To) | 320 |
| Alim | 1000 W Gold ATX 3.1 | 200 |
| Refroidissement | AIO 360 | 160 |
| Boîtier | Airflow ATX évolutif | 140 |
| **Tour** | | **4560** |
| Écrans | 4K 144 Hz + 2×1440p + HP (gamme éco) | 870 |
| Périphériques | Clavier méca + souris + casque + webcam | 275 |
| **TOTAL** | | **≈ 5705** |
| **Réserve** | | **≈ 295** |

**Backtrack de l'automate :** le choix du 5090 en S1 a forcé un retour sur **S3 (RAM ramenée à 32 Go)** et **S8 (écrans en gamme éco)** pour tenir le budget. C'est l'automate qui fonctionne : un état aval contraint un état amont.
**Pourquoi :** 32 Go de VRAM = la meilleure durée de pertinence pour la création/IA, et repousse le besoin d'upgrade GPU. **Attention :** 32 Go de RAM système est le plancher pour tes VMs + création simultanées ; l'ajout de 32 Go plus tard restera cher jusqu'en 2028 et peut imposer une fréquence RAM réduite. À ne choisir que si la VRAM prime vraiment sur tout.
**Risque :** RAM système limitante à court terme ; réserve mince.

---

### Config 4 — « Silence & sobriété »

Pour le « pose et oublie » : machine puissante, discrète, efficace, avec undervolting léger. Sert directement la longévité (moins de chaleur = composants qui durent).

| État | Composant | Estim. € |
|---|---|---|
| CPU | Ryzen 9 9950X3D (undervolté) | 680 |
| GPU | RTX 5080 16 Go (undervolté) | 1200 |
| Carte mère | X870 (ATX) | 300 |
| RAM | 64 Go DDR5-6000 CL30 | 880 |
| Stockage | 2×2 To NVMe Gen4 + dissipateurs | 320 |
| Alim | 1000 W Platinum semi-passive | 230 |
| Refroidissement | Air premium silencieux OU AIO 360 silencieux | 160 |
| Boîtier | Panneaux insonorisés + ventilos silencieux | 160 |
| **Tour** | | **3930** |
| Écrans | 4K 144 Hz + 2×1440p + HP | 1070 |
| Périphériques | Clavier méca (switchs silencieux) + souris + casque + webcam | 275 |
| **TOTAL** | | **≈ 5275** |
| **Réserve** | | **≈ 725** |

**Pourquoi :** alim Platinum + undervolting + boîtier amorti = machine quasi inaudible sous charge, consommation maîtrisée, températures basses. Même base performante que la Config 1, orientée confort acoustique et durabilité.
**Horizon :** identique à la Config 1 ; l'undervolting prolonge la marge thermique.
**Risque :** léger surcoût alim/boîtier pour le silence → justifié si le bruit t'importe.

---

### Config 5 — « Performance maximale » (proche plafond)

Tout au maximum dans les 6000 €, au prix de compromis assumés sur le stockage et les écrans. Illustre la limite de l'enveloppe dans ce marché.

| État | Composant | Estim. € |
|---|---|---|
| CPU | Ryzen 9 9950X3D | 680 |
| GPU | **RTX 5090 32 Go** | 2300 |
| Carte mère | X870E (ATX, 4× M.2) | 360 |
| RAM | **64 Go** DDR5-6000 CL30 | 880 |
| Stockage | 1×2 To NVMe Gen5 (trimé) | 200 |
| Alim | 1000 W Platinum ATX 3.1 | 230 |
| Refroidissement | AIO 360 | 180 |
| Boîtier | Airflow ATX | 150 |
| **Tour** | | **4980** |
| Écrans | 4K 144 Hz + 2×1440p + HP (gamme éco) | 800 |
| Périphériques | Clavier méca + souris + casque + webcam (gamme éco) | 200 |
| **TOTAL** | | **≈ 5980** |
| **Réserve** | | **≈ 20** |

**Backtrack de l'automate :** 5090 **et** 64 Go ont saturé le budget → retour forcé sur **S4 (stockage réduit à 2 To)** et **S8/S9 (écrans et périphériques en gamme éco)**. C'est le prix de « tout maximiser » dans le marché 2026.
**Pourquoi :** GPU + RAM au sommet, aucun compromis sur les deux composants directeurs. **Mais** réserve quasi nulle (aucun coussin pour un imprévu ou un upgrade), stockage juste, périphériques d'entrée de gamme.
**Risque :** absence de réserve = fragilité (ton guide déconseille de consommer tout le budget). À réserver au cas où tu veux le maximum de puissance brute immédiate et acceptes de compléter le stockage/écrans plus tard.

---

## 4. Tableau comparatif

| Critère | C1 Équilibrée | C2 Value durable | C3 Créa/VRAM | C4 Silence | C5 Perf max |
|---|---|---|---|---|---|
| GPU | 5080 16 Go | 5070 Ti 16 Go | 5090 32 Go | 5080 16 Go | 5090 32 Go |
| RAM | 64 Go | 64 Go | 32 Go | 64 Go | 64 Go |
| Total ≈ € | 5195 | 4705 | 5705 | 5275 | 5980 |
| Réserve ≈ € | 805 | 1295 | 295 | 725 | 20 |
| Jeu 4K120 | ★★★★ | ★★★ | ★★★★★ | ★★★★ | ★★★★★ |
| Création/IA | ★★★★ | ★★★ | ★★★★★ | ★★★★ | ★★★★★ |
| Émulation | ★★★★★ | ★★★★★ | ★★★★★ | ★★★★★ | ★★★★★ |
| Silence | ★★★ | ★★★★ | ★★★ | ★★★★★ | ★★★ |
| Évolutivité | ★★★★ | ★★★★★ | ★★★ | ★★★★ | ★★★ |
| Robustesse budget | ★★★★ | ★★★★★ | ★★ | ★★★★ | ★ |

*(L'émulation est à 5★ partout : elle dépend du 9950X3D, commun à toutes les configs.)*

---

## 5. Analyse des risques

- **Prix (tous).** Estimations niveau C dans un marché volatil. Revérifier au Black Friday ; la RAM et les GPU haut de gamme risquent d'avoir des remises faibles.
- **RAM (C3).** 32 Go système peut brider VMs + création simultanées ; ajout futur cher.
- **Réserve (C5).** Quasi nulle → aucune marge d'erreur, contraire au principe de réserve du guide.
- **VRAM 16 Go (C1, C2, C4).** Limite possible en fin de vie sur Blender/IA → compensée par l'upgrade GPU planifié.
- **Refresh « Super » 24 Go.** Si lancé avant ton achat, il pourrait rebattre les cartes (24 Go au tarif du 5080). À vérifier juste avant le Black Friday — pourrait rouvrir l'état S1.
- **Timing.** Décaler l'achat ne résoudra pas la crise mémoire (élevée jusqu'à fin 2027). Le Black Friday reste pertinent pour le GPU/écrans/périphériques, moins pour la RAM.

---

## 6. Recommandation

Dans le contexte 2026, **la Config 1 (Équilibrée)** est le meilleur compromis global pour ta mission mixte, et **la Config 2 (Value durable)** est la plus intelligente au sens de ta stratégie 10 ans : peu exposée aux prix gonflés, grosse réserve pour racheter GPU/RAM quand le marché se normalisera.

Si la création/IA prime sur tout → Config 3. Si le silence est une vraie priorité → Config 4. Si tu veux la puissance brute maximale et acceptes ses compromis → Config 5.

**Transitions restant ouvertes à surveiller avant l'achat :**
1. **S1 (GPU)** — vérifier le lancement/prix du refresh « Super » 24 Go.
2. **S3 (RAM)** — surveiller la DDR5 ; toute détente change l'arbitrage 32/64 Go.
3. **S8 (écrans)** — les modèles exacts n'ont pas été figés (bandes de prix seulement) : à choisir selon les offres Black Friday.

*Les références précises de chaque composant (marques, modèles) restent à verrouiller au moment de l'achat, avec des données de prix fraîches.*
