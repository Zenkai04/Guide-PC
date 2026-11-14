# État opérationnel — Projet PC Black Friday 2026

Dernière mise à jour : 14 novembre 2026 (test à blanc d'acquisition n°4, §3.2 ; reprise du 14/11, §3.3)  
Statut : simulations Claude Code ↔ Codex clôturées ; préparation opérationnelle avant acquisition Black Friday

---

# 1. Phase actuelle

```text
PHASE :
PRÉPARATION OPÉRATIONNELLE
→ ACQUISITION BLACK FRIDAY (27 novembre 2026)

ÉTAT :
ChatGPT Web V2      VALIDÉ
Claude Web V2.1     VALIDÉ
Claude Code V1.1    VALIDÉ
Codex V1.1          VALIDÉ
```

Benchmark CLI #1 (31 octobre 2026) :

- durée : ≈ 17 min pour la première boucle, suivie d'analyses complémentaires ;
- Claude Code et Codex : bootstrap et contrôle contradictoire validés ;
- constat : contrôle de qualité, mais coût excessif en itérations et en interventions humaines ;
- aucune architecture réelle ni BOM approuvée.

Simulations pragmatiques Claude Code ↔ Codex (31 octobre 2026) :

- résultats plus concrets et satisfaisants, nette réduction des itérations inutiles ;
- deux configurations comparables produites, puis une BOM candidate complète auditée (voir §3) ;
- aucune BOM finale gelée, aucun achat autorisé.

Règles applicables : manuel `30-Manuel-operationnel-outils.md` §31 (stratégie pragmatique), §32 (procédure du jour J), §33 (correction exceptionnelle, contrôle obligatoire).

---

# 2. Mission

Choisir, composer puis acheter un setup PC complet pour le Black Friday 2026.

Budget de référence :

```text
6 000 € maximum pour le setup complet
```

Le budget couvre l'ensemble du setup prévu : tour, trio d'écrans, périphériques, supports et câbles.

Marge exceptionnelle (décision utilisateur, 10 novembre 2026) :

- 500 € supplémentaires au plus, **qui ne constituent pas un budget normal de 6 500 €** ;
- jamais consommés automatiquement ; réservés à une opportunité exceptionnellement rentable ;
- attente indicative : rapport bénéfices/coût supérieur d'environ 20 % ou davantage à la meilleure solution ≤ 6 000 €, gains étayés, sans score global arbitraire ;
- toute exception est soumise explicitement à l'utilisateur, jamais validée par un agent ;
- produire d'abord la meilleure solution ≤ 6 000 € ; ne pas fabriquer de variante à 6 500 € sans opportunité réelle.

Qualité de l'investissement : une BOM conforme et sous le plafond ne suffit pas à justifier l'achat. Distinguer bonne affaire, prix normal, composant surévalué et configuration acceptable mais peu attractive. `ATTENDRE / NO-GO COMMERCIAL` reste possible même avec une BOM complète sous budget.

RAM : 64 Go est une préférence pertinente (polyvalence, durée de vie), non un minimum éliminatoire démontré. Un choix 32 Go est un compromis à expliciter et à faire accepter par l'utilisateur.

Affichage :

```text
39" 5K2K          OBJECTIF PRIORITAIRE
UWQHD             COMPROMIS ÉVENTUEL
```

IA locale : besoin à très long terme, hors dimensionnement 2026.

Principe :

```text
BUDGET = CONTRAINTE MAXIMALE
BUDGET ≠ OBJECTIF DE DÉPENSE
```

Usages principaux :

- jeux AAA haute résolution / haut rafraîchissement ;
- Blender ;
- Premiere ;
- Photoshop ;
- développement logiciel ;
- virtualisation ;
- systèmes multi-agents ;
- logiciels industriels ;
- émulation PS2 / PS3 / Switch.

Horizon :

```text
5–7 ans sans changement majeur
≈ 10 ans avec upgrades ciblés
```

## 2.1 Exigences utilisateur établies

Affichage :

- 39" 5K2K prioritaire ; 34" UWQHD compromis éventuel ;
- trio d'écrans visuellement cohérent.

Jeu AAA solo :

- 60 fps moyens réellement rendus ; DLSS autorisé ; Frame Generation exclue du calcul ;
- 90 fps souhaitables ; 120 fps en bonus ;
- ray tracing partiel fortement souhaitable ; RT Ultra / Path Tracing facultatif.

Jeu compétitif (CoD) :

- 120 fps ou davantage et faible latence prioritaires.

Autres usages :

- virtualisation : trois scénarios **alternatifs**, jamais exécutés simultanément entre eux ni avec un jeu lourd et Blender :
  1. Windows Server + 3 à 5 clients légers simultanés (administration, connexions, opérations simples) — scénario dimensionnant ;
  2. une VM isolée de test de logiciels, à un autre moment ;
  3. expérimentations Linux ou autres systèmes, séparées ;
- dimensionnement indicatif du scénario 1 (ESTIMATION utilisateur) : Server 6 Go + 5 clients × 2 Go + hôte 8 Go = 24 Go ; avec des clients à 4 Go (minimum Windows 11), 34 Go ;
- RAM : **64 Go = objectif privilégié** (polyvalence, longévité) ; **32 Go = compromis économique acceptable uniquement après confirmation explicite de l'utilisateur avant l'achat** ; critère pratique : 32 Go conformes avec clients Linux légers ou ≤ 4 clients Windows 11, non conformes avec 5 clients Windows 11 ;
- compilations et exports Premiere occasionnels, potentiellement lourds ;
- Blender : progression débutant → intermédiaire, notamment modding de jeux vidéo ;
- macOS : apprentissage de l'écosystème Apple, sans obligation de le faire tourner sur la tour ;
- IA locale avancée : très long terme, hors dimensionnement 2026.

## 2.2 Données utilisateur confirmées

- licence Windows 11 Pro déjà disponible et support d'installation USB préparé → licence : 0 € ;
- montage physique réalisé par l'utilisateur → prestation : 0 € ;
- ne pas recommander un PC prémonté pour éviter l'assemblage ;
- conserver les vérifications de compatibilité Windows 11 ;
- budgéter uniquement les accessoires indispensables réellement manquants.

Aucune clé de licence ni information personnelle n'est consignée dans le dépôt.

## 2.3 Préférences secondaires

RGB : **FACULTATIF**, purement esthétique, non éliminatoire, sans avantage fonctionnel présumé.

- à performances, prix, fiabilité, acoustique et compatibilité comparables, une version RGB peut être préférée ;
- RGB discret, configurable et désactivable préférable ;
- pas de budget RGB réservé ; pas de surcoût significatif ; pas de sacrifice de performance, silence ou qualité ; pas de RGB imposé sur tous les composants.

## 2.4 Stratégie Black Friday

- fenêtre principale d'acquisition : 27 novembre 2026 ;
- les prix d'octobre sont provisoires ; les promotions réelles sont inconnues ;
- aucune remise n'est présumée ;
- les configurations étudiées restent des bases techniques et alternatives, non définitives ;
- ne pas figer une architecture sur les seuls prix d'octobre ;
- plafond de 6 000 € maintenu pour le setup complet ;
- distinguer objectif initial et compromis nécessaires pour tenir le budget ;
- `NO-GO` reste une issue rationnelle si les offres réelles sont insuffisantes.

---

# 3. État réel de la configuration

```text
ARCHITECTURE RÉELLE :
NON GELÉE

BOM RÉELLE :
NON GELÉE

RECHERCHE MARCHÉ :
NON OUVERTE (prix indicatifs autorisés ; session d'acquisition à ouvrir explicitement)
```

## 3.1 Résultats des simulations (31 octobre 2026) — PROVISOIRES

Bases techniques à reprendre le jour J. Tous les choix de composants restent provisoires ; aucun ne constitue une décision d'achat.

**Configuration A ajustée — préférence provisoire** (BOM candidate auditée par Codex : `BOM À CORRIGER` ; lignes bloquantes corrigées par Claude Code, correction non ré-auditée ; gel non prononcé) :

| Poste | Référence provisoire |
|---|---|
| CPU | AMD Ryzen 7 9800X3D (100-100001084WOF) |
| Ventirad | Thermalright Phantom Spirit 120 SE (154 mm) |
| Carte mère | MSI MAG B850 TOMAHAWK MAX WIFI |
| RAM | Corsair CMK64GX5M2B6000Z30 (2 × 32 Go DDR5-6000 CL30, EXPO ; QVL et stabilité à vérifier) |
| GPU | ASUS PRIME-RTX5070TI-O16G (RTX 5070 Ti 16 Go) |
| SSD | Samsung 990 PRO 2 To (MZ-V9P2T0BW), slot M2_1 |
| Alimentation | Corsair RM850e (2025) CP-9020296-EU |
| Boîtier | Fractal Design North TG Dark (FD-C-NOR1C-02) + ARCTIC P12 PWM (ACFAN00119A) en extraction |
| Écran central | Alienware AW3926QW (39" 5K2K WOLED RVB, 165 Hz, DP 2.1 UHBR20, garantie 3 ans incluant le marquage) |
| Écrans latéraux | 2 × Dell UltraSharp U2724D (27" QHD IPS Black 120 Hz), câbles DP fournis |
| Câble central | Club 3D CAC-1091 (DP80, 1,2 m) ou CAC-1092 (1,6 m) |
| Périphériques (PROPOSITION) | Logitech G515 LIGHTSPEED TKL FR (920-012546), Logitech G502 X filaire (référence à confirmer), HyperX Cloud III (727A8AA), Logitech C920 (960-001055, disponibilité à vérifier) |
| Licence / montage | 0 € (voir §2.2) |

Total estimé lors de la simulation (prix d'octobre, hors licence et montage) : ≈ 5 624 €, réserve ≈ 376 €. Hypothèses hautes : dépassement possible. Valeurs indicatives, à remplacer par les prix réels.

**Configuration B — alternative / secours** : même socle, RTX 5080 16 Go + écran central 34" UWQHD OLED 240 Hz + 2 latéraux 27" QHD IPS. Conservée comme solution si l'objectif 5K2K ne tient pas le budget ou si la priorité compétitive/fps l'impose.

Constats de simulation à réutiliser :

- RTX 5090 hors budget aux prix d'octobre 2026 ;
- RAM, SSD et GPU en forte hausse en octobre 2026 ; prix du Black Friday inconnus ;
- performances 5K2K non mesurées de façon appariée pour les GPU retenus ;
- largeur et profondeur du bureau non documentées (trio ≈ 2,1–2,2 m à plat).

Les configurations C1 à C5, leurs variantes, les convergences observées pendant les simulations et les BOM de test ne constituent pas automatiquement des décisions d'achat réelles.

Une ancienne convergence de simulation vers C2 reste un résultat de test tant qu'elle n'est pas explicitement approuvée dans le workflow réel.

## 3.2 Test à blanc d'acquisition n°4 (10 novembre 2026) — SIMULATION

Session d'acquisition ouverte **en simulation uniquement** ; aucun achat, aucun gel réel. Production Claude Code (SIM4-V1), audit Codex, correction ciblée (SIM4-V2), contrôle Codex des corrections sans nouvelle boucle.

**Résultat :** `SIM4-V2 — BOM INCOMPLÈTE — NE PAS GELER` ; verdict `ATTENDRE — NO-GO SIMULÉ AU 10/11`. Aucune recomposition nécessaire ; aucune exception au-delà de 6 000 € démontrée.

Corrections locales de la configuration A retenues en simulation (toutes `PROPOSITION`, non approuvées) :

| Poste | SIM4-V2 | Prix observé 10/11 |
|---|---|---|
| CPU | Ryzen 7 9800X3D **tray** (SAV via revendeur) | 449,95 € LDLC |
| Ventirad | Thermalright Phantom Spirit 120 **non-SE** (157 mm) | 64,95 € LDLC |
| Carte mère | MSI MAG B850 TOMAHAWK WIFI (non-MAX) | 299,95 € LDLC |
| RAM | G.Skill F5-6000J3636F16GX2-RM5NRK, **2 × 16 Go** DDR5-6000 CL36 EXPO — compromis 32 Go **non validé** | 695,95 € LDLC |
| GPU | MSI RTX 5070 Ti 16G VENTUS 3X OC — **offre non sécurisée** | 1 402,95 € Amazon (via comparateur, non vérifié) ; 1 649,95 € LDLC (sous 7 j) |
| SSD | Samsung 990 EVO Plus 2 To (TLC, HMB, compromis de gamme vs 990 PRO) | 399,95 € LDLC |
| Alim / boîtier | RM850e (2025) / North TG Dark (+ ARCTIC P12 facultatif) | 134,95 € / 139,95 € LDLC |
| Écrans | AW3926QW + 2 × U2724D | 1 249 € Dell / 2 × 352,99 € PcComponentes |
| Câble central | **Supprimé** : HDMI 2.1 FRL fourni par Dell (5K2K 165 Hz avec DSC) ; latéraux en DP | 0 € |
| Périphériques | G515 TKL Lightspeed, G502 X filaire, Cloud III, C920s | 349,80 € LDLC |

Budget (hors livraison) : sous-total sans GPU 4 499,38 € ; avec GPU Amazon 5 902,33 € ; avec Gainward RTX 5070 Ti Phoenix-S LDLC 1 619,95 € (moins chère vérifiée en stock) 6 119,33 € — **hors budget** ; variante 64 Go 6 486,37 € — exception non démontrée.

Seuil de faisabilité GPU (avec 32 Go) : **prix GPU livraison comprise ≤ 1 500,62 € − F**, F = frais de livraison des autres achats. Condition de faisabilité, pas critère de bonne affaire.

Constats de marché (relevés datés, non prédictifs) :

- minimum LDLC en stock de la catégorie RTX 5070 Ti : 1 349,95 € (13/09), 1 479,95 € (04/11), 1 619,95 € (10/11) — suivi de catégorie, pas de la même référence ; hausses partenaires annoncées ;
- 9800X3D tray LDLC : 499,95 € (01/11) → 449,95 € (10/11) ;
- kits 64 Go DDR5-6000 ≈ 1 280–1 300 € ; AW3926QW stable à 1 249 €.

Points ouverts reportés au jour J :

- offre GPU livrée sous le seuil, chez un vendeur acceptable (une Gainward ou autre substitution exige ses propres contrôles de dépendances) ;
- frais réels au panier (LDLC calculés au panier ; Dell, Amazon inconnus) ;
- choix 32 / 64 Go : décrire le plus gros scénario de virtualisation (nombre de VM, RAM par VM, charge hôte simultanée) ;
- dégagement RAM/ventirad (≈ 41 mm pour 42 mm, non officiel) : relever le ventilateur, hauteur installée ≤ 170 mm à confirmer ;
- performances 5K2K et CoD non mesurées : incertitude documentée (§31.4), ni validation ni échec.

Enseignements de méthode :

- qualifier une offre par des relevés appariés (même référence, même marchand, dates différentes) ; un prix conseillé ou un indice de catégorie DRAM/NAND ne qualifie pas une offre précise ;
- un prix vu sur comparateur n'est pas une offre sécurisée (vendeur, stock, prix livré à vérifier) ;
- tableau budgétaire reproductible ligne par ligne, frais traités comme variable explicite tant qu'ils ne sont pas relevés.

## 3.3 Reprise du test à blanc n°4 (14 novembre 2026) — SIMULATION

Production Claude Code (SIM4-V3), audit Codex, correction ciblée (SIM4-V3.1) sans nouvelle boucle. Aucun achat, aucun gel, aucun fichier de composition produit.

**Résultat :** architecture A **techniquement crédible**, **correction locale** (pas de recomposition) ; `BOM À CORRIGER — NON GELABLE` (choix 32 / 64 Go non confirmé, vendeur des latéraux non validé, total livré non établi) ; verdict `ATTENDRE — NO-GO COMMERCIAL SIMULÉ AU 14/11`. Aucune extension au-delà de 6 000 € justifiée.

Socle SIM4-V2 inchangé, sauf GPU : MSI RTX 5070 Ti 16G VENTUS 3X OC chez GrosBill.

Prix observés le 14/11 — **observations historiques datées, non objectifs ni seuils d'achat** :

| Référence | Prix observé 14/11 | Vendeur / état |
|---|---|---|
| MSI RTX 5070 Ti VENTUS 3X OC | 1 449,99 € (barré 1 589,99 €) | GrosBill, en stock web, promo sans date de fin |
| Minimum RTX 5070 Ti LDLC (Gainward Phoenix-S) | 1 679,95 € | LDLC, en stock (1 619,95 € le 10/11) |
| RTX 5080 la moins chère (Gainward Python III) | 2 199,95 € | LDLC |
| Ryzen 7 9800X3D tray | 449,95 € | LDLC, en stock |
| B850 TOMAHAWK WIFI / Phantom Spirit 120 / RM850e / North TG Dark | 299,95 / 64,95 / 134,95 / 139,95 € | LDLC, en stock |
| G.Skill 2 × 16 Go RM5NRK | 695,95 € | LDLC, en stock (identique au 10/11) |
| Kits 2 × 32 Go DDR5-6000 neufs | 1 299,95 € (Aegis 5, 7–15 j) ; 1 399,95 € (RM5NRW, en stock) | LDLC |
| Samsung 990 EVO Plus 2 To / 990 PRO 2 To | 399,95 / 549,95 € | LDLC |
| AW3926QW | 1 249 € (fiche) ; 1 149 € (autre page Dell, non établi comme commandable) | Dell FR |
| U2724D | 351,04 € (marketplace « You Get », non validé) ; 408,16 € | PcComponentes ; Dell FR |
| Périphériques (G515 TKL, G502 X, Cloud III, C920s) | 349,80 € | LDLC (Cloud III : délai > 15 j) |

Budget (hors frais non relevés) : 5 936,52 € ; frais admissibles ≤ 63,48 €. Latéraux Dell directs : 6 050,76 € (+ frais) avec central à 1 249 € ; sous 6 000 € seulement si le central à 1 149 € est confirmé. 64 Go : ≥ 6 440 € avant frais dans tous les cas observés, hors budget.

Qualification économique : faisabilité conditionnelle, **bonne affaire non démontrée**. Aucun historique apparié pour la Ventus ; les qualifications « surprix », « prix normal » ou « meilleure offre » ont été retirées faute de relevés appariés. Un GPU à ≈ 1 450 € est un repère de faisabilité, pas un déclencheur d'achat.

Compatibilités confirmées par l'audit : Ventus 303 mm (North 355 mm) ; 750 W recommandés, 12V-2x6 natif RM850e ; RAM 41 mm, ventirad 157 mm (limite 170 mm) ; câbles HDMI 2.1 FRL (AW3926QW) et DP (U2724D) fournis ; têtes d'affichage NVIDIA 2 (DSC) + 1 + 1 = 4 — déduction technique sans essai physique.

**Performances non validées :** AAA à 60 fps réellement rendus en 5K2K et CoD ≥ 120 fps avec la RTX 5070 Ti restent **non mesurés** ; la capacité 5K2K 165 Hz de la liaison ne prouve pas les performances de rendu (§31.4 : ni validation, ni échec).

Conditions de GO (au-delà du plafond) : choix RAM confirmé par l'utilisateur, vendeurs validés, disponibilité simultanée de toutes les lignes, total livré réel ≤ 6 000 €, intérêt économique étayé.

---

# 4. Workflow validé

```text
BESOIN / CONTRAINTES
        ↓
COMPOSITION
        ↓
CONTRÔLE CONTRADICTOIRE
        ↓
CONSENSUS ARCHITECTURAL
        ↓
BOM CANDIDATE
        ↓
AUDIT BOM
        ↓
CORRECTIONS ÉVENTUELLES
        ↓
BOM GELÉE
        ↓
RECHERCHE MARCHÉ
        ↓
VALIDATION DES DEALS
        ↓
ÉVENTUELLES RECOMPOSITIONS
        ↓
PRIX FINAUX AU PANIER
        ↓
GO / NO-GO
        ↓
ACHAT
```

Règle majeure :

> Aucune recherche commerciale systématique ne commence avant le gel de la BOM.

Exception : session d'acquisition explicitement ouverte par le pilotage (manuel §32). Les offres réelles des références utiles sont alors relevées avant la BOM candidate, puis audit Codex, gel, validation panier et GO / NO-GO. Fonctionnement nominal des contrôles : composition complète → audit principal → validation ou correction ciblée (manuel §33).

---

# 5. Répartition des rôles

## ChatGPT Web V2

```text
RÔLE :
pilotage Web
contrôle contradictoire
audit BOM
coordination marché
validation finale
```

## Claude Web V2.1

```text
RÔLE :
composition
recomposition
BOM
correction BOM
urgence
```

## Claude Code V1.1

```text
RÔLE :
moteur CLI de composition et recomposition
compatibilité et dimensionnement
production et correction de BOM
urgence technique
```

Claude Code ne gèle pas sa propre BOM et ne prononce pas le GO / NO-GO final.

Pendant une session d'acquisition ouverte, Claude Code peut consulter directement les prix et disponibilités réels des références utiles (manuel §32). Cela ne vaut jamais autorisation d'achat.

## Codex V1.1

```text
RÔLE :
contrôle contradictoire CLI
audit d'architecture
audit BOM
détection correction locale / recomposition
autorisation du gel de BOM
```

Codex n'est pas le moteur principal de composition.

Le chat ChatGPT principal reste le centre de pilotage global du projet.

---

# 6. Règles BOM

Une BOM candidate doit être réellement exploitable.

Les formulations génériques comme :

```text
RTX 5080
64 Go DDR5
SSD 2 To
1000 W Gold
```

sont insuffisantes au stade BOM.

Chaque ligne doit au minimum indiquer :

- catégorie ;
- fabricant ;
- modèle exact ;
- référence/SKU si vérifiée ;
- quantité ;
- caractéristiques critiques ;
- alternatives ;
- dépendances ;
- prix cible si déjà défini ;
- prix maximal si déjà défini ;
- `STATUT DU CHOIX`.

Valeurs possibles :

```text
APPROUVÉ
DÉRIVÉ DE L'ARCHITECTURE
PROPOSITION CLAUDE
À DÉTERMINER
```

Une référence incertaine doit être signalée.

Ne jamais inventer un SKU, un prix ou une préférence utilisateur.

---

# 7. Séparation BOM / marché

Avant le gel de la BOM, les recherches externes restent techniques :

- documentation constructeur ;
- référence/SKU ;
- compatibilité ;
- dimensions ;
- connectique ;
- VESA ;
- poids ;
- caractéristiques électriques.

Ne pas consulter volontairement pour décider la BOM :

- Dealabs ;
- promotions Amazon ;
- comparateurs ;
- Google Shopping ;
- Mino ;
- Shoptimate.

Exception :

```text
VARIABLE VÉRIFIÉE
```

explicitement transmise dans le workflow.

Les `PRIX INDICATIF` (relevés exploratoires datés et sourcés, transmis par le pilotage ou effectués sur autorisation explicite de la tâche) sont autorisés avant le gel pour vérifier la faisabilité économique, selon le §31.3 du manuel. Ils ne valent ni prix au panier ni décision d'achat ; la recherche systématique de promotions reste interdite avant le gel.

Pendant une session d'acquisition explicitement ouverte, les restrictions ci-dessus sont levées pour les références utiles selon le §32 du manuel.

---

# 8. Priorités du système

Priorités principales :

- performances utiles ;
- robustesse ;
- silence ;
- fiabilité ;
- durée de vie ;
- cohérence globale ;
- cohérence visuelle du trio d'écrans ;
- coût justifié ;
- évolutivité.

L'esthétique décorative pure est secondaire.

La cohérence visuelle du sous-système d'affichage reste une vraie contrainte UX.

---

# 9. Stratégie d'achat

Stratégie nominale :

```text
ONE-SHOT
```

Objectif :

acheter autant que possible l'ensemble du système dans une même fenêtre après validation complète.

Exceptions possibles :

- opportunité extraordinaire ;
- promotion future officiellement confirmée ;
- impossibilité rationnelle de sécuriser tout simultanément.

Toute exception structurelle doit être réévaluée.

---

# 10. Chronométrage connu

Première simulation Web de consensus architectural :

```text
≈ 9 min 40 s
```

Première production de BOM Claude Web :

```text
≈ 5 à 10 min
```

Benchmark CLI #1, première boucle Claude Code ↔ Codex :

```text
≈ 17 min, suivies d'analyses complémentaires
```

Ces mesures sont exploratoires.

Le temps humain d'orchestration est désormais mesuré en plus du temps des agents.

KPI préparation :

```text
temps début architecture
→ BOM gelée exploitable
```

KPI acquisition :

```text
temps détection deal
→ décision exécutable
```

---

# 11. Source de vérité

Ordre pratique :

```text
1. décisions explicitement approuvées
2. 31-Etat-operationnel.md pour l'état courant
3. corpus Guide-PC
4. 30-Manuel-operationnel-outils.md pour le protocole
5. documentation constructeur
6. données de marché vérifiées
7. tests techniques fiables
8. comparateurs / communauté
9. estimations / rumeurs
```

Une ancienne proposition ne devient jamais une décision simplement parce qu'elle est récente.

---

# 12. Bootstrap des agents CLI

Au début d'une nouvelle session CLI, avant la première réponse substantielle :

```text
1. 31-Etat-operationnel.md
2. map.md
3. 30-Manuel-operationnel-outils.md
4. documents du corpus pertinents pour la tâche
```

`CLAUDE.md` est réservé aux instructions Claude Code.

`AGENTS.md` est réservé aux instructions Codex.

Chaque agent doit ignorer le fichier d'instructions de l'autre comme source normative de rôle.

---

# 13. Mémoire et Task Observer

Pour l'usage normal, Task Observer ou d'autres mécanismes de mémoire peuvent être utiles.

Pour un benchmark à froid destiné à mesurer la qualité du dépôt et des instructions :

```text
SOURCE ATTENDUE :
dépôt uniquement
```

Un état provenant d'une autre session ou d'un autre agent ne doit pas servir à combler un manque documentaire pendant le benchmark.

---

# 14. Prochaine action

```text
PRÉPARATION OPÉRATIONNELLE
→ SESSION D'ACQUISITION BLACK FRIDAY (27 novembre 2026, ouverture explicite par le pilotage)
```

Préparation :

- partir des configurations A (préférence provisoire) et B (alternative) du §3.1 ;
- configurations de secours actualisables les 24, 25 et 26 novembre (manuel §19–20) ;
- lever avant la session, si possible, les incertitudes non commerciales : dimensions du bureau, variantes de références à confirmer ;
- reprendre les points ouverts du test à blanc n°4 (§3.2–3.3), notamment la confirmation 32 / 64 Go (OS et nombre des clients légers), le prix commandable de l'AW3926QW, le vendeur des latéraux et le seuil GPU.

Jour J : procédure du manuel §32, contrôles selon §33.

Ne pas ouvrir la recherche marché systématique avant l'ouverture explicite de la session d'acquisition.

---

# 15. État synthétique

```text
Guide-PC              ACTIF
Manuel opérationnel   V2.2

ChatGPT Web            V2 VALIDÉ
Claude Web             V2.1 VALIDÉ

Claude Code            V1.1 VALIDÉ
Codex                  V1.1 VALIDÉ

Simulations CLI         CLÔTURÉES
Config A (5K2K)         PRÉFÉRENCE PROVISOIRE
Config B (UWQHD)        ALTERNATIVE / SECOURS
Test à blanc n°4        SIM4-V2 INCOMPLÈTE — NO-GO SIMULÉ (10/11)
Reprise 14/11           SIM4-V3.1 CRÉDIBLE, À CORRIGER — NO-GO COMMERCIAL SIMULÉ
RAM                     64 Go PRIVILÉGIÉS ; 32 Go SUR CONFIRMATION UTILISATEUR
Budget                  6 000 € + marge exceptionnelle 500 € (sur accord explicite)

Architecture réelle    NON GELÉE
BOM réelle             NON GELÉE
Marché                  NON OUVERT (prix indicatifs autorisés)
Achat                   NON AUTORISÉ

Licence Windows         EXISTANTE (0 €)
Montage                 UTILISATEUR (0 €)

Prochaine action        PRÉPARATION → ACQUISITION BF 27/11
```
