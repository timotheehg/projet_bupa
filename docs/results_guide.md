# Guide des résultats

## Objectif

Cette page explique comment lire les résultats du benchmark.

Le projet produit plusieurs niveaux de résultats :

- tables intermédiaires
- tables de synthèse
- analyse des erreurs
- vérification
- cas difficiles
- index de lecture

## 1. Résultats intermédiaires

Ces fichiers permettent de suivre la chaîne principale :

- `df_gold.csv`
- `df_notes.csv`
- `df_recon.csv`

Ils correspondent respectivement à :

- la source structurée de référence
- la note générée
- la reconstruction structurée

## 2. Tables longues

Ces fichiers détaillent les éléments médicaux ligne par ligne :

- `df_gold_conditions_long.csv`
- `df_gold_medreq_long.csv`
- `df_recon_conditions_long.csv`
- `df_recon_medreq_long.csv`

Ils sont utiles pour :

- inspecter les items individuellement
- comprendre les écarts de matching
- vérifier les différences entre gold et reconstruction

## 3. Résultats de scoring

Les fichiers de scoring principaux sont :

- `df_scores.csv`
- `df_scores_overall_summary.csv`
- `df_scores_summary_by_note_style.csv`

### `df_scores.csv`

Résultats détaillés patient par patient.

Ce fichier contient les scores calculés selon les deux lectures principales :

- **note vs recon**
- **source vs recon**

### `df_scores_overall_summary.csv`

Vue globale du benchmark.

### `df_scores_summary_by_note_style.csv`

Vue agrégée par style de note.

## 4. Analyse des erreurs

Les fichiers principaux sont :

- `df_error_analysis.csv`
- `df_error_types_by_note_style_conditions.csv`
- `df_error_types_by_note_style_medication_requests.csv`
- `df_hard_cases_by_note_style.csv`

Ils permettent de comprendre :

- quels types d’erreurs dominent
- quels styles de notes sont les plus difficiles
- quels patients représentent des cas complexes

## 5. Vérification

Le fichier principal est :

- `df_verification.csv`

Il contient la couche de vérification automatique de cohérence.

## 6. Fichiers de revue

Les fichiers complémentaires sont :

- `df_export_review.csv`
- `df_index.csv`

Ils servent à :

- faciliter la navigation dans les exports
- contrôler rapidement le contenu généré
- vérifier que les fichiers finaux sont bien présents

## 7. Ordre de lecture conseillé

Je conseille l’ordre suivant :

1. `df_scores_overall_summary.csv`
2. `df_scores_summary_by_note_style.csv`
3. `df_error_analysis.csv`
4. `df_verification.csv`
5. `df_hard_cases_by_note_style.csv`
6. `df_scores.csv`
7. puis les tables intermédiaires et longues

## 8. Messages principaux du benchmark

Les conclusions principales sont les suivantes :

- les medication requests sont mieux reconstruites que les conditions
- les conditions ont souvent de bons résultats sémantiques mais des résultats exacts plus faibles
- certains styles de note sont plus robustes que d’autres
- une partie des pertes d’information apparaît avant la reconstruction finale

## Voir aussi

- [Pipeline détaillée](pipeline_explained.md)
- [Rapport benchmark](benchmark_report.md)
