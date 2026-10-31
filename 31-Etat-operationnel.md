# État opérationnel — Projet PC Black Friday 2026

Dernière mise à jour : 31 octobre 2026  
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

- virtualisation : scénarios alternatifs, non cumulés artificiellement ;
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
- lever avant la session, si possible, les incertitudes non commerciales : dimensions du bureau, variantes de références à confirmer.

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

Architecture réelle    NON GELÉE
BOM réelle             NON GELÉE
Marché                  NON OUVERT (prix indicatifs autorisés)
Achat                   NON AUTORISÉ

Licence Windows         EXISTANTE (0 €)
Montage                 UTILISATEUR (0 €)

Prochaine action        PRÉPARATION → ACQUISITION BF 27/11
```
