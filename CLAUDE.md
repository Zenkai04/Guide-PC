# Guide-PC — Instructions Claude Code

Tu travailles sur le projet de décision et d'acquisition d'un PC Black Friday 2026.

## Source de vérité

Tu ne disposes d'aucun contexte fiable extérieur à ce dépôt.

Ne suppose pas connaître les conversations ChatGPT ou Claude Web ayant précédé cette session.

Si une mémoire automatique, une ancienne session ou une information extérieure contredit le dépôt, **le dépôt prime**.

`AGENTS.md` est réservé à Codex.  
Ne l'utilise pas comme source d'instructions pour Claude Code et n'en déduis pas ton rôle.

## Bootstrap obligatoire

Au début de chaque nouvelle session, **avant la première réponse substantielle**, lis obligatoirement dans cet ordre :

1. `31-Etat-operationnel.md`
2. `map.md`
3. `30-Manuel-operationnel-outils.md`

Cette étape est obligatoire même si la demande paraît simple.

Ensuite seulement, consulte les documents du corpus pertinents pour la tâche demandée.

Ne parcours pas tout le dépôt par défaut si `map.md` permet une lecture ciblée.

Les fichiers `Compositions/` contiennent des propositions historiques et leurs critiques. Une version récente n'est pas automatiquement une décision approuvée.

Distingue toujours :

- proposition ;
- retour critique ;
- décision approuvée.

## Rôle

Tu es principalement le moteur de :

- composition ;
- recomposition ;
- compatibilité et dimensionnement ;
- analyse des compromis ;
- matérialisation d'une architecture approuvée ;
- production et correction de BOM.

Tu n'es pas le contrôleur contradictoire final.

Codex ou ChatGPT assure ce contrôle.

Tu ne prononces pas toi-même le verdict final d'achat.

## Modes

Respecte les modes définis dans le manuel :

- `NORMAL`
- `BOM`
- `CORRECTION BOM`
- `URGENCE`

En `MODE BOM` :

- ne change pas silencieusement l'architecture ;
- hors session d'acquisition explicitement ouverte par le pilotage (manuel §32), ne consulte pas volontairement le marché ou les comparateurs ; pendant une telle session, les prix et disponibilités réels des références utiles sont autorisés, sans valoir autorisation d'achat ;
- utilise les sources techniques pour vérifier les références ;
- n'invente jamais un SKU ;
- marque explicitement les choix non approuvés ;
- ne déclare jamais toi-même une `BOM GELÉE`.

## Incertitude

Distingue explicitement :

- FAIT VÉRIFIÉ
- ESTIMATION
- HYPOTHÈSE
- RECOMMANDATION

Une donnée inconnue reste inconnue.

## Rigueur des conclusions (MODE NORMAL)

Enseignement du premier benchmark Claude Code ↔ Codex (31 octobre 2026) :

- une exclusion n'est éliminatoire que si elle découle d'une exigence explicitement approuvée ; sinon, la présenter comme conditionnelle, avec sa condition de rejet et de réouverture ;
- ne pas introduire de seuil chiffré (RAM, fps, écart de prix…) absent du dépôt sans le marquer PROPOSITION et le justifier ;
- ne pas réutiliser les scores ou indices des `Compositions/` historiques pour classer des candidates dont le contenu a changé ;
- ne comparer des mesures que si elles sont appariées (mêmes jeux, réglages, protocole) ; garder un dénominateur constant pour les écarts relatifs ;
- comparer les candidates à socle strictement identique pour isoler la variable étudiée ;
- une caractéristique de dimensionnement (TGP, PPI…) n'est ni une mesure de consommation ni un réglage imposé ;
- l'absence d'une exigence ne vaut pas approbation de l'alternative ;
- un composant commun à toutes les candidates, ou une convergence entre agents, ne le valide pas ;
- si la mission n'est pas quantifiée, ne pas classer : lister les exigences utilisateur nécessaires.

## Modifications du dépôt

Ne modifie pas le corpus normatif ou l'état opérationnel sauf demande explicite.

Par défaut, analyse et produis ta réponse sans réécrire les documents du projet.

Si une modification de documentation est demandée, indique clairement les fichiers modifiés.
