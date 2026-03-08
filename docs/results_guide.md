# Guide des résultats

## Objectif

Cette page explique comment lire les résultats du benchmark.

Le dépôt contient plusieurs niveaux de résultats :
- intermédiaires
- synthèses
- erreurs
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

#### `df_scores_overall_summary.csv`
Vue globale du benchmark.

#### `df_scores_summary_by_note_style.csv`
Vue par style de note.

## 3. Erreurs

Dans `results/summaries/errors/`, on trouve :

- `df_error_taxonomy.csv`
- `df_error_taxonomy_by_note_style_conditions.csv`
- `df_error_taxonomy_by_note_style_medication_requests.csv`
- `df_hard_cases_by_note_style.csv`

Ces fichiers permettent de comprendre :
- quels types d’erreurs dominent
- quels styles sont les plus difficiles
- quels patients représentent des cas complexes

## 4. Vérification

Dans `results/summaries/verification/`, on trouve :

- `df_verification.csv`

Ce fichier contient la couche de vérification LLM.

## 5. Résultats secondaires

Dans `results/other_results/`, on trouve des fichiers utiles pour une lecture plus détaillée, mais non indispensables à la compréhension principale.

## 6. Comment lire les résultats dans le bon ordre

Je conseille l’ordre suivant :

1. `df_scores_overall_summary.csv`
2. `df_scores_summary_by_note_style.csv`
3. `df_error_taxonomy.csv`
4. `df_verification.csv`
5. `df_hard_cases_by_note_style.csv`
6. puis les exemples patients

## 7. Messages principaux du benchmark

Les conclusions principales sont :
- les medication requests sont mieux reconstruites que les conditions
- les conditions ont souvent de bons résultats sémantiques mais des résultats exacts plus faibles
- certains styles de note sont plus robustes que d’autres
- une partie des pertes d’information apparaît avant la reconstruction finale

## Voir aussi

- [Rapport benchmark](benchmark_report.md)
- [Exemples patients](../results/examples/)
