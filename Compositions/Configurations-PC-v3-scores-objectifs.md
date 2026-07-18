# Rapport de décision v3 — 5 configurations « irréprochables »

**Mission :** émulation, ingénierie info (compilation, VMs, multi-agents, logiciels industriels), gaming AAA 4K 120 fps+, modding, création (Blender, Photoshop, Premiere).
**Budget max :** 6000 € (tour + 3 écrans avec haut-parleurs + clavier mécanique + souris USB + casque USB + webcam).
**Horizon :** 5–7 ans sans changement, 10 ans avec upgrades. **Achat :** Black Friday 2026.

---

## 0. Réponse au retour V2 — ce qui a changé

| Remarque V2 | Action V3 |
|---|---|
| 1. Pondérations fixes | **Pondérations dérivées automatiquement de la mission** (§1) |
| 2. Technique = métriques hétérogènes | **4 sous-axes techniques** : CPU-multi, CPU-cache, GPU-jeu, GPU-créa (§1–2) |
| 3. Pas de confiance par axe | **Niveau de confiance A/B/C/D par axe** (§2) |
| 4. Pas d'indices transversaux | **5 indices** : cohérence, modularité, saturation, remplaçabilité, réutilisation (§4) |
| 5. Risques qualitatifs | **AMDEC quantifiée** : IPR = Probabilité × Gravité × Détectabilité (§5) |
| 6. Scores composant par composant | **Scores par chaîne de ressources** (§6) |

---

## 1. Dérivation des pondérations depuis la mission

### 1.1 Vecteur de mission (déclaration utilisateur interprétée — confiance B, modifiable)

| Mission | Poids |
|---|---|
| Ingénierie (compilation, VMs, multi-agents, logiciels indus.) | 30 % |
| Gaming AAA 4K 120+ | 25 % |
| Création (Blender, Photoshop, Premiere) | 25 % |
| Émulation | 15 % |
| Modding | 5 % |

### 1.2 Matrice mission → demande technique

Chaque mission répartit son poids sur les 4 sous-axes de performance.

| Mission (poids) | CPU-multi | CPU-cache | GPU-jeu | GPU-créa |
|---|---|---|---|---|
| Ingénierie 30 % | 0,75 | 0,15 | 0,00 | 0,10 |
| Gaming 25 % | 0,15 | 0,20 | 0,65 | 0,00 |
| Création 25 % | 0,30 | 0,00 | 0,00 | 0,70 |
| Émulation 15 % | 0,25 | 0,65 | 0,10 | 0,00 |
| Modding 5 % | 0,30 | 0,10 | 0,40 | 0,20 |
| **Poids technique résultant** | **39,0 %** | **19,75 %** | **19,75 %** | **21,5 %** |

**Lecture :** la mission fait ressortir le **CPU multi-thread** comme premier facteur de performance — ce qui valide a posteriori le choix d'un 16 cœurs, et confirme que le CPU (identique partout) n'est pas le point de différenciation entre configs.

### 1.3 Pondérations globales (bloc perf 55 % + bloc pérennité 45 %)

| Axe | Poids global | Origine |
|---|---|---|
| CPU-multi | 21,45 % | mission |
| GPU-créa | 11,83 % | mission |
| CPU-cache | 10,86 % | mission |
| GPU-jeu | 10,86 % | mission |
| Robustesse | 10,00 % | priorité longévité |
| Évolutivité | 10,00 % | priorité longévité |
| Économique | 8,00 % | contrainte budget |
| Thermique/acoustique | 7,00 % | préférence « pose et oublie » |
| Énergétique | 5,00 % | secondaire |
| Ergonomie | 5,00 % | 3 écrans + périph |

---

## 2. Axes, confiance et scores unitaires

Indices 0–100 (perf : référence haut de gamme = 100 ; autres : min–max entre configs). **CPU-multi et CPU-cache sont identiques dans les 5 configs** (même 9950X3D) → ils ne différencient pas, mais pèsent dans le global.

| Axe | Conf. | C1 | C2 | C3 | C4 | C5 |
|---|---|---|---|---|---|---|
| CPU-multi | **A** | 85 | 85 | 85 | 85 | 85 |
| CPU-cache | **A** | 92 | 92 | 92 | 92 | 92 |
| GPU-jeu (4K) | **A** | 72 | 62 | 100 | 70 | 100 |
| GPU-créa (Blender+VRAM) | **A/B** | 50 | 45 | 100 | 48 | 100 |
| Robustesse | **C** | 78 | 90 | 48 | 80 | 30 |
| Évolutivité | **B** | 80 | 76 | 66 | 78 | 55 |
| Économique | **C** | 64 | 98 | 24 | 61 | 12 |
| Thermique/acous. | **B** | 65 | 80 | 45 | 93 | 42 |
| Énergétique | **B** | 75 | 90 | 32 | 97 | 30 |
| Ergonomie | **C** | 80 | 80 | 62 | 82 | 48 |

*Confiance moyenne pondérée ≈ B. Les axes les plus fiables (A) sont les axes techniques ; les moins fiables (C) sont l'économique, la robustesse et l'ergonomie — tous dépendants du marché ou de références non figées.*

---

## 3. Socle mesuré (rappel compact)

- **CPU 9950X3D :** Cinebench 2024 ~2456 multi / ~139 mono ; Blender BMW ~54 s ; PassMark ~70 000.
- **GPU (Blender OptiX / 4K natif AAA / TGP) :** 5070 Ti ~7 600 / 57–89 fps / 264 W · 5080 ~9 000 / 62–97 fps / 300 W · 5090 ~17 800 / 77–125 fps / 575 W. DLSS 4 porte les trois à 120–200+ fps.
- **Refroidissement (9950X3D) :** Arctic LF III 360 ~30–33 dBA / 65–70 °C · Noctua NH-D15 G2 ~24,6 dBA / +3–5 °C.
- **Marché :** DDR5 64 Go ≈ 850–900 € (crise, jusqu'à fin 2027) ; socket AM5 supporté jusqu'en 2029.

---

## 4. Composants et indices transversaux

### 4.1 Vue composants (réf. PROVISOIRE, prix niveau C)

| État | C1 Équilibrée | C2 Value | C3 Créa/IA | C4 Silence | C5 Perf max |
|---|---|---|---|---|---|
| CPU | 9950X3D | 9950X3D | 9950X3D | 9950X3D (UV) | 9950X3D |
| GPU | RTX 5080 | RTX 5070 Ti | RTX 5090 | RTX 5080 (UV) | RTX 5090 |
| Carte mère | X870 | B850 | X870E (ProArt) | X870 | X870E |
| RAM | 64 Go 6000 | 64 Go 6000 | 32 Go (→64) | 64 Go 6000 | 64 Go 6000 |
| Stockage | 4 To Gen4 | 4 To Gen4 | 4 To Gen4 | 4 To Gen4 | 2 To Gen5 |
| Alim | 1000 W Gold | 850 W Gold | 1000 W Gold | 1000 W Platinum | 1000 W Platinum |
| Refroid. | LF III 360 | NH-D15 G2 | LF III 360 | NH-D15 G2 | LF III 360 |
| Boîtier | Airflow | Airflow | Airflow | Insonorisé | Airflow |
| Écrans | A (4K32+2×QHD) | A | B (éco) | A | B (éco) |
| Périph. | Standard | Standard | Standard | Silencieux | Éco |
| **Total ≈ €** | **5165** | **4715** | **5725** | **5245** | **5980** |
| **Réserve ≈ €** | **835** | **1285** | **275** | **755** | **20** |

### 4.2 Indices transversaux (0–100)

| Indice | Définition | C1 | C2 | C3 | C4 | C5 |
|---|---|---|---|---|---|---|
| Cohérence système | absence de goulot / équilibre | 88 | 90 | 62 | 88 | 74 |
| Modularité | M.2 libres, lignes, extension | 80 | 68 | 92 | 80 | 85 |
| Saturation (↑ = + de marge) | éloignement des limites (RAM/VRAM/PSU/stockage) | 78 | 76 | 55 | 82 | 58 |
| Remplaçabilité | standard ATX + longévité AM5 | 85 | 85 | 82 | 85 | 82 |
| Réutilisation | survie vers la config suivante | 82 | 84 | 74 | 86 | 70 |

**Signaux :** C3 abaisse la **cohérence** et la **saturation** (5090 associé à 32 Go de RAM) ; C5 abaisse la **saturation** (stockage 2 To) et la **réutilisation** (écrans/périph éco).

---

## 5. AMDEC — risques quantifiés

Échelle 1–10. **IPR = Probabilité × Gravité × Détectabilité** (détectabilité élevée = difficile à anticiper). Seuils : < 100 acceptable · 100–200 à surveiller · > 200 action requise.

| Config | Risque principal | P | G | D | **IPR** | Statut |
|---|---|---|---|---|---|---|
| C1 | Saturation VRAM 16 Go (créa/IA an 5+) | 5 | 5 | 4 | **100** | à surveiller |
| C1 | Prix RAM au BF > estimation | 6 | 4 | 2 | 48 | acceptable |
| C2 | 5070 Ti insuffisant 4K natif AAA futurs | 6 | 4 | 3 | 72 | acceptable (upgrade prévu) |
| C2 | B850 limite extension M.2/lignes | 3 | 4 | 3 | 36 | acceptable |
| C3 | **RAM 32 Go saturée** (VMs + créa simultanés) | 7 | 7 | 3 | **147** | à surveiller |
| C3 | Upgrade RAM futur coûteux (2027–28) | 8 | 5 | 2 | 80 | acceptable |
| C4 | Marge thermique air sous charge extrême | 4 | 4 | 3 | 48 | acceptable |
| C4 | Undervolt instable si mal réglé | 3 | 5 | 4 | 60 | acceptable |
| C5 | **Stockage 2 To saturé tôt** | 8 | 5 | 3 | **120** | action (ajout SSD anticipé) |
| C5 | Réserve ~0 → tout imprévu = dépassement | 7 | 7 | 2 | 98 | limite |

**Lecture :** aucun risque > 200. Les deux points chauds (IPR ≈ 120–147) sont la **RAM de C3** et le **stockage de C5** — cohérent avec les compromis assumés de ces deux profils.

---

## 6. Scores par chaîne de ressources

Trois chaînes évaluées ; on identifie le **maillon limitant** et un score d'équilibre 0–100.

| Chaîne | C1 | C2 | C3 | C4 | C5 |
|---|---|---|---|---|---|
| **Jeu** (CPU→PCIe5→GPU→VRAM→écran 4K) | 82 · *GPU* | 74 · *GPU* | 92 · *équilibré* | 80 · *GPU* | 92 · *équilibré* |
| **Dev/Données** (SSD→RAM→CPU) | 90 · *équilibré* | 90 · *équilibré* | 66 · *RAM* | 90 · *équilibré* | 74 · *stockage* |
| **Création** (SSD→RAM→GPU/VRAM→écran calibré) | 76 · *VRAM* | 72 · *VRAM* | 68 · *RAM système* | 76 · *VRAM* | 72 · *stockage* |

**Lecture :** C1/C2/C4 ont un maillon faible en **VRAM** (16 Go) sur la chaîne création — couvert par l'upgrade GPU planifié. C3 est paradoxal : GPU surpuissant mais **RAM système** limitante sur les chaînes dev et création. C5 est limité par le **stockage** hors chaîne jeu.

---

## 7. Score global pondéré (pondérations mission) → classement

| | C1 | C2 | C3 | C4 | C5 |
|---|---|---|---|---|---|
| **Score global** | 75,2 | **78,8** | 72,1 | 77,6 | 67,2 |
| **Rang** | 3ᵉ | **1ᵉ** | 4ᵉ | 2ᵉ | 5ᵉ |
| Étoiles | ★★★★ | ★★★★ | ★★★★ | ★★★★ | ★★★★ |

*Les cinq restent en bande « très bon » (le CPU commun tire tout le monde vers le haut) ; la différenciation se lit dans le rang et les profils d'axes.*

### 7.1 Sensibilité aux pondérations

| Scénario de pondération | Tête de classement |
|---|---|
| **Mission (défaut ci-dessus)** | C2 > C4 > C1 |
| Priorité **création/IA** (GPU-créa 30 %) | C3 remonte 1ᵉ ou 2ᵉ |
| Priorité **jeu** (GPU-jeu 30 %) | C3/C5 remontent, C1 devant C2 |
| Priorité **silence** (thermique 25 %) | C4 domine nettement |
| Priorité **budget/robustesse** | C2 se détache |

Le trio **C2 / C4 / C1** est robuste à la plupart des pondérations raisonnables. C3 n'est premier que si la création/IA écrase le reste. C5 ne devient jamais premier — c'est l'étude de cas du plafond.

---

## 8. Verdict par configuration

- **C1 Équilibrée** — le meilleur compromis « sans angle mort » ; maillon faible VRAM anticipé. Recommandation généraliste.
- **C2 Value durable** — 1ᵉ en pondération mission ; exposition marché minimale + réserve max ; la plus intelligente dans le contexte 2026–2027.
- **C3 Création/IA** — GPU maximal, mais cohérence/RAM la pénalisent pour *cette* mission mixte ; excellente uniquement si la création/IA devient dominante.
- **C4 Silence** — identité propre (cible < 25 dBA, ~510 W) ; 2ᵉ au global ; le choix si le confort acoustique compte vraiment.
- **C5 Perf max** — démonstration du plafond ; IPR stockage + réserve nulle la rendent la moins robuste. Non recommandée comme solution principale.

---

## 9. États à réouvrir avant achat

| État | Déclencheur |
|---|---|
| S1 GPU | Refresh « Super » 24 Go (surclasserait le 5080) |
| S3 RAM | Détente DDR5 (rééquilibre 32/64 Go, surtout C3) |
| S8 Écrans | Modèles exacts à figer selon offres BF (spécifs déjà arrêtées) |
| Prix (tous) | Relevé BF → PROVISOIRE devient PRÉVALIDÉ/VERROUILLÉ |

---

## 10. Prochaine étape

Choisir **une configuration** (ou ajuster le vecteur de mission §1.1 si mes poids ne reflètent pas tes priorités réelles). On descend ensuite au **verrouillage** : références exactes figées, relevé de prix frais, et validation des cibles mesurables comme **critères de recette** de la machine assemblée.
