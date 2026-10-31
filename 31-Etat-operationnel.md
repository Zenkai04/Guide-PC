# État opérationnel — Projet PC Black Friday 2026

Dernière mise à jour : 31 octobre 2026  
Statut : agents Web et CLI bootstrap validés ; benchmark CLI à lancer

---

# 1. Phase actuelle

```text
PHASE :
VALIDATION DES AGENTS

ÉTAT :
ChatGPT Web V2      VALIDÉ
Claude Web V2.1     VALIDÉ
Claude Code V1.1    VALIDÉ
Codex V1.1          VALIDÉ
```

Les agents CLI ont réussi leur test de bootstrap depuis le dépôt.

Prochaine étape :

```text
BENCHMARK CLAUDE CODE ↔ CODEX
```

---

# 2. Mission

Choisir, composer puis acheter un setup PC complet pour le Black Friday 2026.

Budget de référence :

```text
≈ 6 000 € maximum
```

Le budget couvre l'ensemble du setup prévu, notamment la tour et le trio d'écrans.

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

---

# 3. État réel de la configuration

```text
ARCHITECTURE RÉELLE :
NON GELÉE

BOM RÉELLE :
NON GELÉE

RECHERCHE MARCHÉ :
NON OUVERTE
```

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

Ces mesures sont exploratoires.

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
LANCER LE PREMIER BENCHMARK CLAUDE CODE ↔ CODEX
```

Objectif :

tester la boucle CLI :

```text
Claude Code — MODE NORMAL
→ Codex — audit contradictoire
→ Claude Code — correction si nécessaire
→ consensus architectural
→ Claude Code — MODE BOM
→ Codex — audit BOM
→ corrections éventuelles
→ BOM GELÉE
```

Pour ce premier benchmark, arrêter le test au gel de la BOM.

Ne pas ouvrir encore la recherche marché réelle.

---

# 15. État synthétique

```text
Guide-PC              ACTIF
Manuel opérationnel   V2

ChatGPT Web            V2 VALIDÉ
Claude Web             V2.1 VALIDÉ

Claude Code            V1.1 VALIDÉ
Codex                  V1.1 VALIDÉ

Architecture réelle    NON GELÉE
BOM réelle             NON GELÉE
Marché                  NON OUVERT

Prochaine action        BENCHMARK CLI
```
