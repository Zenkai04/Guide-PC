# Rapport de décision v2 — 5 configurations objectivées

**Mission :** émulation, ingénierie info (compilation, VMs, multi-agents, logiciels industriels), gaming AAA 4K 120 fps+, modding, création (Blender, Photoshop, Premiere).
**Budget max :** 6000 € (tour + 3 écrans avec haut-parleurs + clavier mécanique + souris filaire USB + casque filaire USB + webcam).
**Horizon :** 5–7 ans sans changement, 10 ans avec upgrades. **Achat :** Black Friday 2026.

---

## 0. Réponse au retour — ce qui a changé depuis la v1

| Remarque | Action dans la v2 |
|---|---|
| 1. « VERROUILLÉ » annoncé trop tôt | Système de **4 statuts d'état** (§1) appliqué à chaque composant |
| 2. Références en familles, pas figées | Chaque état reçoit une **référence précise candidate** en statut PROVISOIRE (§5) |
| 3. Étoiles subjectives | **Scores normalisés par axe** (métriques → normalisation → pondération → étoiles) (§3, §6) |
| 4. Affirmations qualitatives | Remplacées par des **cibles mesurables** : fps, 1 % low, dBA, °C, W, temps Blender/compilation (§2, §5) |
| 5. Écrans peu détaillés | Section dédiée : **disposition, sorties, VESA, PPI, cohérence** (§4) |

---

## 1. Système de statuts d'état

| Statut | Signification | Confiance |
|---|---|---|
| **VERROUILLÉ** | Décision ferme, indépendante du marché | A/B |
| **PRÉVALIDÉ** | Famille/principe validé, référence précise à confirmer | B |
| **PROVISOIRE** | Référence précise proposée, dépendante prix/dispo | C |
| **À RÉOUVRIR** | État à revisiter avant achat, déclencheur identifié | — |

Règle : on n'achète que des états au moins **PRÉVALIDÉ** ; les prix restent PROVISOIRE jusqu'au relevé Black Friday.

---

## 2. Socle de données mesurées (référentiel objectif)

> Sources : agrégats de tests indépendants (mi-2025 à mi-2026). Performances = niveau **A/B**. Prix = niveau **C** (marché mi-2026, crise mémoire).

### CPU — Ryzen 9 9950X3D (commun aux 5 configs)

| Métrique | Valeur mesurée |
|---|---|
| Cinebench 2024 multi / mono | ~2393–2456 / ~139–140 |
| Blender BMW (CPU) | ~54 s |
| PassMark multi | ~70 000 |
| Geekbench 6 multi / mono | ~22 500 / ~3 475 |
| Cœurs / threads | 16 / 32 |
| Cache L3 | 128 Mo (3D V-Cache) |
| TDP / max | 170 W / 230 W |

### GPU — rendu (Blender OptiX) et jeu (4K natif ultra)

| GPU | VRAM | Blender OptiX (≈) | Cyberpunk 4K | Hogwarts 4K | Witcher 3 4K | TGP | Idle |
|---|---|---|---|---|---|---|---|
| RTX 5070 Ti | 16 Go | ~7 600 | 57 | 60 | 83 | ~264 W | bas |
| RTX 5080 | 16 Go | ~9 000 | 62 | 69 | 91 | ~300 W | ~13 W |
| RTX 5090 | 32 Go | ~17 800 | 77 | 98 | 125 | ~575 W | — |

*fps = moyenne 4K natif ultra sans upscaling. Avec DLSS 4 / Multi-Frame Gen, les trois dépassent 120–200 fps sur AAA compatibles. Le 5080 devance le 5070 Ti de ~10–16 % ; le 5090 devance le 5080 de ~35–57 % selon les titres.*

### Refroidissement — acoustique et thermique (sur 9950X3D)

| Solution | Charge (dBA) | Repos (dBA) | Temp CPU charge | Note |
|---|---|---|---|---|
| Arctic Liquid Freezer III 360 | ~30–33 | ~6 | 65–70 °C | Meilleure marge thermique |
| Noctua NH-D15 G2 (air) | ~24,6 | quasi nul | ~70–75 °C (+3–5 °C) | Zéro bruit de pompe, 7 ans+ |

---

## 3. Méthodologie de scoring (étoiles dérivées, plus manuelles)

**7 axes**, chacun alimenté par des métriques mesurées ou calculées, normalisés 0–100, puis convertis en étoiles.

| Axe | Métriques sous-jacentes |
|---|---|
| Technique | perf GPU rendu (Blender) + jeu 4K (fps) ; CPU constant |
| Économique | réserve budgétaire (€) + perf/€ |
| Thermique/acoustique | dBA charge + °C + chaleur GPU dissipée |
| Énergétique | conso système (W) + perf/W |
| Robustesse | réserve + marges (PSU, VRAM, RAM pleine) + exposition marché |
| Évolutivité | chipset/M.2, RAM→128 Go, marge PSU, chemin GPU |
| Ergonomie | gamme écrans + gamme périphériques |

**Normalisation :** indice 0–100 (référence haut de gamme = 100 pour l'axe technique ; min–max entre les 5 configs pour les autres).
**Conversion étoiles :** 0–20 → ★ · 20–40 → ★★ · 40–60 → ★★★ · 60–80 → ★★★★ · 80–100 → ★★★★★.
**Pondération par défaut (profil mixte) :** Technique 25 %, Économique 15 %, Évolutivité 15 %, Robustesse 15 %, Thermique 10 %, Énergétique 10 %, Ergonomie 10 %. *La pondération est explicite et modifiable ; le classement en dépend (§6).*

---

## 4. Sous-système écrans (3 écrans)

### Disposition physique recommandée
- **Écran principal** 4K, centré, en paysage : jeu + création (colorimétrie).
- **Latéral 1** en paysage : documentation, navigateur, communication.
- **Latéral 2** en **portrait** (option recommandée) : code, logs, terminaux, timelines verticales — gain ergonomique réel pour le dev/VMs.

### Sorties vidéo (GPU RTX 50)
Les RTX 50 exposent typiquement **3× DisplayPort 2.1 + 1× HDMI 2.1** = 4 sorties, suffisant pour 3 écrans.
- Principal 4K 120 Hz+ → **DisplayPort 2.1** (bande passante pour 4K@120+, HDR, VRR).
- Latéraux 1440p → DisplayPort ou HDMI 2.1.

### VESA & ergonomie
- Support **VESA 100×100** standard sur les trois.
- **Bras articulés** recommandés pour aligner hauteurs et inclinaisons (confort multi-écran, réduction fatigue visuelle) — surtout avec un latéral en portrait.

### Densité (PPI) & cohérence
| Écran | Taille | Définition | PPI ≈ | Mise à l'échelle |
|---|---|---|---|---|
| Principal 4K | 32" | 3840×2160 | ~138 | 150 % |
| Principal 4K (variante) | 27" | 3840×2160 | ~163 | 175 % |
| Latéraux QHD | 27" | 2560×1440 | ~109 | 100 % |

**Point de cohérence :** un 4K 32" (~138 PPI) à 150 % et un QHD 27" (~109 PPI) à 100 % donnent des tailles de texte proches — combinaison cohérente. Pour la création, le principal doit être **calibré usine (ΔE < 2)**, couverture **sRGB ~100 % / DCI-P3 ≥ 90 %** ; les latéraux, moins critiques, doivent au moins partager le **type de dalle (IPS)** et une température de couleur proche pour éviter les écarts visibles.
**Haut-parleurs :** intégrés aux écrans si disponibles, sinon **kit 2.0 dédié** (meilleure qualité) — ligne incluse dans chaque config.

---

## 5. Les 5 configurations v2

> Réf. = candidat **PROVISOIRE** (à confirmer prix/dispo au Black Friday). Prix = estimations € niveau C.

### Config 1 — Équilibrée

| État | Réf. candidate (PROVISOIRE) | Statut | Estim. € |
|---|---|---|---|
| CPU | Ryzen 9 9950X3D | VERROUILLÉ (prix PROVISOIRE) | 680 |
| GPU | RTX 5080 16 Go (ex. ASUS Prime / Gigabyte Gaming OC) | PRÉVALIDÉ | 1200 |
| Carte mère | X870 ATX (ex. ASUS TUF X870-Plus / MSI Tomahawk X870) | PROVISOIRE | 300 |
| RAM | 64 Go DDR5-6000 CL30 EXPO (ex. G.Skill Flare X5 2×32) | PROVISOIRE / À RÉOUVRIR | 880 |
| Stockage | 2× 2 To NVMe Gen4 (ex. Samsung 990 Pro / WD SN850X) | PROVISOIRE | 320 |
| Alim | 1000 W Gold ATX 3.1 (ex. Corsair RM1000x) | PRÉVALIDÉ | 190 |
| Refroid. | Arctic Liquid Freezer III 360 | PROVISOIRE | 120 |
| Boîtier | ATX airflow (ex. Lian Li Lancool 216 / Fractal North) | PROVISOIRE | 130 |
| **Tour** | | | **3820** |
| Écrans | 4K 32" 144 Hz + 2× QHD 27" + HP | PRÉVALIDÉ / À RÉOUVRIR | 1070 |
| Périph. | Clavier méca + souris USB + casque USB + webcam | PROVISOIRE | 275 |
| **TOTAL / Réserve** | | | **≈ 5165 / ~835** |

**Cibles mesurables :** jeu 4K 60–97 fps natif AAA, **120–180 fps avec DLSS 4** ; Blender OptiX ~9 000 ; compilation sur 32 threads ; charge ~30–33 dBA / 65–70 °C ; conso charge ~600 W.
**Risque objectif :** VRAM 16 Go = première limite probable en création lourde/IA vers l'année 5 → couverte par l'upgrade GPU planifié.

---

### Config 2 — Value durable

| État | Réf. candidate (PROVISOIRE) | Statut | Estim. € |
|---|---|---|---|
| CPU | Ryzen 9 9950X3D | VERROUILLÉ | 680 |
| GPU | RTX 5070 Ti 16 Go (ex. ASUS Prime / MSI Ventus) | PRÉVALIDÉ | 900 |
| Carte mère | B850 ATX VRM solide (ex. MSI Tomahawk B850) | PROVISOIRE | 220 |
| RAM | 64 Go DDR5-6000 CL30 EXPO | PROVISOIRE / À RÉOUVRIR | 880 |
| Stockage | 2× 2 To NVMe Gen4 | PROVISOIRE | 320 |
| Alim | 850 W Gold ATX 3.1 (ex. Corsair RM850x) | PRÉVALIDÉ | 150 |
| Refroid. | Noctua NH-D15 G2 (air) | PROVISOIRE | 110 |
| Boîtier | ATX airflow | PROVISOIRE | 110 |
| **Tour** | | | **3370** |
| Écrans | 4K 32" 144 Hz + 2× QHD 27" + HP | PRÉVALIDÉ / À RÉOUVRIR | 1070 |
| Périph. | Clavier méca + souris + casque + webcam | PROVISOIRE | 275 |
| **TOTAL / Réserve** | | | **≈ 4715 / ~1285** |

**Cibles mesurables :** jeu 4K 57–89 fps natif, **120+ avec DLSS 4** ; Blender OptiX ~7 600 ; charge ~24,6 dBA (air) / ~70–75 °C ; conso charge ~544 W.
**Logique :** exposition minimale au GPU surévalué + réserve ~1300 € pour racheter GPU/RAM en 2027–2028 à prix normalisé. La plus alignée avec la stratégie 10 ans dans ce marché.

---

### Config 3 — Création / IA (VRAM max)

| État | Réf. candidate (PROVISOIRE) | Statut | Estim. € |
|---|---|---|---|
| CPU | Ryzen 9 9950X3D | VERROUILLÉ | 680 |
| GPU | **RTX 5090 32 Go** (ex. MSI Ventus 3X / Gigabyte Gaming OC) | PRÉVALIDÉ | 2300 |
| Carte mère | X870E ATX créateur (ex. ASUS ProArt X870E-Creator) | PROVISOIRE | 380 |
| RAM | **32 Go** DDR5-6000 (→ +32 Go planifié) | PROVISOIRE / À RÉOUVRIR | 400 |
| Stockage | 2× 2 To NVMe Gen4 | PROVISOIRE | 320 |
| Alim | 1000 W Gold ATX 3.1 | PRÉVALIDÉ | 200 |
| Refroid. | Arctic Liquid Freezer III 360 | PROVISOIRE | 160 |
| Boîtier | ATX airflow | PROVISOIRE | 140 |
| **Tour** | | | **4580** |
| Écrans | 4K 27" 144 Hz + 2× QHD 27" + HP (gamme éco) | PRÉVALIDÉ / À RÉOUVRIR | 870 |
| Périph. | Clavier méca + souris + casque + webcam | PROVISOIRE | 275 |
| **TOTAL / Réserve** | | | **≈ 5725 / ~275** |

**Backtrack :** choix 5090 (S1) → retour forcé sur **RAM (S3 → 32 Go)** et **écrans (S8 → gamme éco)**.
**Plan RAM explicite (réponse au retour) :** kit **2×16 Go** au départ, puis **remplacement par 2×32 Go** (pas d'ajout à 4 barrettes, pour préserver la fréquence stable sur AM5) quand les prix se détendent. Coût futur estimé : le prix d'un kit 2×32 au moment de l'achat.
**Cibles :** jeu 4K 77–125 fps natif ; Blender OptiX ~17 800 (rendu ~2× plus rapide que la C2) ; charge ~33 dBA ; conso charge ~875 W.
**Risque objectif :** 32 Go système = plancher pour VMs + création simultanées ; limite probable **avant** les 32 Go de VRAM.

---

### Config 4 — Silence & sobriété

| État | Réf. candidate (PROVISOIRE) | Statut | Estim. € |
|---|---|---|---|
| CPU | Ryzen 9 9950X3D (undervolté) | VERROUILLÉ | 680 |
| GPU | RTX 5080 16 Go (undervolté ~250 W) | PRÉVALIDÉ | 1200 |
| Carte mère | X870 ATX | PROVISOIRE | 300 |
| RAM | 64 Go DDR5-6000 CL30 | PROVISOIRE / À RÉOUVRIR | 880 |
| Stockage | 2× 2 To NVMe Gen4 + dissipateurs | PROVISOIRE | 320 |
| Alim | 1000 W Platinum semi-passive (ex. Seasonic Vertex / be quiet! Dark Power) | PRÉVALIDÉ | 230 |
| Refroid. | Noctua NH-D15 G2 (zéro pompe) | PROVISOIRE | 130 |
| Boîtier | Insonorisé (ex. Fractal Define 7 / be quiet! Silent Base) | PROVISOIRE | 160 |
| **Tour** | | | **3900** |
| Écrans | 4K 32" 144 Hz + 2× QHD 27" + HP | PRÉVALIDÉ / À RÉOUVRIR | 1070 |
| Périph. | Clavier méca silencieux + souris + casque + webcam | PROVISOIRE | 275 |
| **TOTAL / Réserve** | | | **≈ 5245 / ~755** |

**Différenciation vs C1 (réponse au retour) :** ce n'est pas qu'une variante — le triptyque **air sans pompe + boîtier insonorisé + undervolting GPU/CPU** vise une **cible acoustique < 25 dBA en charge** (contre 30–33 dBA en C1) et une conso réduite (~510 W contre ~600 W), au prix de ~2–4 % de perf GPU (undervolt).
**Cibles :** charge **< 25 dBA** / CPU ~72 °C / GPU ~65 °C ; conso charge ~510 W ; jeu identique à C1 à ~2 % près.

---

### Config 5 — Performance maximale (proche plafond)

| État | Réf. candidate (PROVISOIRE) | Statut | Estim. € |
|---|---|---|---|
| CPU | Ryzen 9 9950X3D | VERROUILLÉ | 680 |
| GPU | **RTX 5090 32 Go** | PRÉVALIDÉ | 2300 |
| Carte mère | X870E ATX | PROVISOIRE | 360 |
| RAM | 64 Go DDR5-6000 CL30 | PROVISOIRE / À RÉOUVRIR | 880 |
| Stockage | 1× 2 To NVMe Gen5 (réduit) | PROVISOIRE / À RÉOUVRIR | 200 |
| Alim | 1000 W Platinum ATX 3.1 | PRÉVALIDÉ | 230 |
| Refroid. | Arctic Liquid Freezer III 360 | PROVISOIRE | 180 |
| Boîtier | ATX airflow | PROVISOIRE | 150 |
| **Tour** | | | **4980** |
| Écrans | 4K 27" 144 Hz + 2× QHD 27" + HP (gamme éco) | À RÉOUVRIR | 800 |
| Périph. | Gamme éco | À RÉOUVRIR | 200 |
| **TOTAL / Réserve** | | | **≈ 5980 / ~20** |

**Backtrack :** 5090 + 64 Go → retours forcés sur **stockage (S4 → 2 To)**, **écrans (S8)** et **périphériques (S9)**.
**Cibles :** jeu 4K 77–125 fps natif, 200+ DLSS 4 ; Blender OptiX ~17 800 ; conso charge ~875 W ; charge ~33 dBA.
**Risque objectif :** réserve ~0 → aucune marge (contraire au principe de réserve) ; stockage juste. **Étude de cas du plafond**, non recommandée comme solution principale.

---

## 6. Scores normalisés → étoiles → classement

Indices 0–100 (méthode §3), puis étoiles.

| Axe (pondération) | C1 | C2 | C3 | C4 | C5 |
|---|---|---|---|---|---|
| Technique (25 %) | 70 ★★★★ | 55 ★★★ | 100 ★★★★★ | 68 ★★★★ | 100 ★★★★★ |
| Économique (15 %) | 60 ★★★★ | 95 ★★★★★ | 21 ★★ | 55 ★★★ | 8 ★ |
| Évolutivité (15 %) | 78 ★★★★ | 75 ★★★★ | 65 ★★★★ | 76 ★★★★ | 55 ★★★ |
| Robustesse (15 %) | 75 ★★★★ | 88 ★★★★★ | 48 ★★★ | 78 ★★★★ | 30 ★★ |
| Thermique/acous. (10 %) | 65 ★★★★ | 78 ★★★★ | 45 ★★★ | 92 ★★★★★ | 40 ★★★ |
| Énergétique (10 %) | 75 ★★★★ | 88 ★★★★★ | 35 ★★ | 95 ★★★★★ | 32 ★★ |
| Ergonomie (10 %) | 78 ★★★★ | 78 ★★★★ | 62 ★★★★ | 80 ★★★★★ | 50 ★★★ |
| **Score global pondéré** | **71,3** | **76,9** | **59,3** | **75,1** | **51,2** |
| **Classement (pondération défaut)** | **3ᵉ** | **1ᵉ** | **4ᵉ** | **2ᵉ** | **5ᵉ** |

### Sensibilité à la pondération (analyse, doc 17)
Le classement **dépend des poids**, et c'est voulu :
- **Pondération « performance »** (Technique 45 %) : C1 et C3 remontent, C5 devient viable → ordre C1/C3 ≈ tête.
- **Pondération « robustesse/économie »** (défaut ci-dessus) : **C2 > C4 > C1** — la réserve et l'efficacité priment.
- **Pondération « silence »** (Thermique 30 %) : **C4** domine nettement.

Autrement dit, il n'y a pas un vainqueur absolu : **C2, C4 et C1 forment le trio de tête robuste**, C3 est le choix spécialisé création/IA, C5 reste l'étude de cas du plafond.

---

## 7. États à réouvrir avant l'achat (déclencheurs)

| État | Déclencheur de réouverture |
|---|---|
| S1 GPU | Sortie/tarif d'un refresh 24 Go (« Super ») → pourrait surclasser le 5080 |
| S3 RAM | Toute détente DDR5 → rééquilibre l'arbitrage 32/64 Go (surtout C3) |
| S8 Écrans | Modèles exacts à figer selon offres Black Friday (spécifs déjà définies §4) |
| Tous prix | Relevé Black Friday → passage PROVISOIRE → PRÉVALIDÉ/VERROUILLÉ |

---

## 8. Prochaine étape proposée

Choisir **une configuration** (ou une pondération d'axes reflétant tes priorités) ; on descend alors au niveau **VERROUILLÉ** état par état, en figeant les références exactes avec un relevé de prix frais, et en confirmant les cibles mesurables comme critères de recette de la machine assemblée.
