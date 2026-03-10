# Guide des résultats

## Objectif

Cette page explique comment lire les résultats du benchmark.

Le dépôt contient plusieurs niveaux de résultats :

- intermédiaires
- synthèses
- analyse des erreurs
- vérification
- exemples patients

## 1. Résultats intermédiaires

Dans `results/intermediates/`, on trouve :

- `df_gold.csv`
- `df_notes.csv`
- `df_recon.csv`

Ils permettent de suivre la chaîne principale :

- source structurée
- note générée
- reconstruction

## 2. Résultats de métriques

Dans `results/summaries/metrics/`, on trouve :

- `df_scores.csv`
- `df_scores_overall_summary.csv`
- `df_scores_summary_by_note_style.csv`

### Rôle de chaque fichier

#### `df_scores.csv`

Résultats détaillés patient par patient.

Ce fichier contient notamment les scores calculés selon les deux lectures principales :

- **note vs recon**
- **source vs recon**

#### `df_scores_overall_summary.csv`

Vue globale du benchmark.

#### `df_scores_summary_by_note_style.csv`

Vue par style de note.

## 3. Analyse des erreurs

Dans `results/summaries/errors/`, on trouve :

- `df_error_analysis.csv`
- `df_error_types_by_note_style_conditions.csv`
- `df_error_types_by_note_style_medication_requests.csv`
- `df_hard_cases_by_note_style.csv`

Ces fichiers permettent de comprendre :

- quels types d’erreurs dominent
- quels styles sont les plus difficiles
- quels patients représentent des cas complexes

## 4. Vérification

Dans `results/summaries/verification/`, on trouve :

- `df_verification.csv`
- `df_verification_by_note_style.csv`

Ces fichiers contiennent la couche de vérification LLM.

## 5. Résultats secondaires

Dans `results/other_results/`, on trouve des fichiers utiles pour une lecture plus détaillée, mais non indispensables à la compréhension principale.

## 6. Comment lire les résultats dans le bon ordre

Je conseille l’ordre suivant :

1. `df_scores_overall_summary.csv`
2. `df_scores_summary_by_note_style.csv`
3. `df_error_analysis.csv`
4. `df_verification.csv`
5. `df_hard_cases_by_note_style.csv`
6. puis les exemples patients

## Résultats visuels

### Comparaison des scores par style de note

| Style de note | Note vs recon cond exact F1 | Note vs recon méd exact F1 | Source vs recon cond exact F1 | Source vs recon méd exact F1 | Taux consistent |
|---|---:|---:|---:|---:|---:|
| Health check summary | 0.533 | 0.829 | 0.458 | 0.785 | 0.900 |
| Medical history note | 0.650 | 0.882 | 0.546 | 0.850 | 0.900 |
| Short consultation note | 0.381 | 0.776 | 0.288 | 0.665 | 0.900 |
| Telegraphic note | 0.536 | 0.722 | 0.460 | 0.525 | 0.900 |

![Comparaison des F1 exacts par style de note](../assets/figures/style_exact_f1.png)

*Figure : comparaison des performances exactes par style de note.*

### Vérification par style de note

| Verdict | Nombre |
|---|---:|
| consistent | 36 |
| unknown | 4 |

![Vérification par style de note](../assets/figures/verification_by_style.png)

*Figure : résultats de la chaîne de vérification selon le style de note.*

## 7. Messages principaux du benchmark

Les conclusions principales sont :

- les medication requests sont mieux reconstruites que les conditions
- les conditions ont souvent de bons résultats sémantiques mais des résultats exacts plus faibles
- certains styles de note sont plus robustes que d’autres
- une partie des pertes d’information apparaît avant la reconstruction finale

## Voir aussi

- [Rapport benchmark](benchmark_report.md)
- [Exemples patients](../results/examples/)
