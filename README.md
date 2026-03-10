# Projet BUPA

## Présentation

Ce projet étudie un pipeline de reconstruction structurée de données médicales à partir de notes cliniques générées depuis des bundles FHIR synthétiques.

L’idée générale est la suivante :

1. partir d’un dossier patient structuré au format FHIR
2. filtrer l’information utile
3. construire une source structurée de référence
4. générer une note clinique non structurée
5. reconstruire une structure à partir de cette note
6. évaluer la qualité de la reconstruction
7. analyser les erreurs et les cas difficiles

Le projet se concentre principalement sur deux types d’information :

- les **conditions**
- les **medication requests**

## Quick start

Si vous découvrez le projet, l’ordre de lecture conseillé est :

1. [Vue d’ensemble du projet](docs/project_overview.md)
2. [Pipeline détaillée](docs/pipeline_explained.md)
3. [Guide des résultats](docs/results_guide.md)
4. [Synthèse globale des scores](results/summaries/metrics/df_scores_overall_summary.csv)
5. [Exemples patients](results/examples/)

## Navigation rapide

### Comprendre le projet

- [Vue d’ensemble du projet](docs/project_overview.md)
- [Pipeline détaillée](docs/pipeline_explained.md)
- [Guide du notebook](docs/notebook_guide.md)
- [Guide des résultats](docs/results_guide.md)
- [Carte du dépôt](docs/repository_map.md)

### Analyse et synthèse

- [Rapport benchmark](docs/benchmark_report.md)

### Fichiers importants

- [Notebook final](notebooks/BUPA_benchmark_final.ipynb)
- [Résultats intermédiaires](results/intermediates/)
- [Résultats finaux](results/summaries/)
- [Autres résultats](results/other_results/)
- [Exemples patients](results/examples/)

## Structure générale du dépôt

```text
projet_bupa/
├── README.md
├── .gitignore
├── notebooks/
├── docs/
├── results/
└── assets/
```

## Pipeline résumée

La logique générale du projet est la suivante :

**FHIR filtered -> gold source -> note générée -> reconstruction -> scoring -> vérification -> analyse des erreurs**

Pour une explication détaillée, voir :

- [Pipeline détaillée](docs/pipeline_explained.md)

## Contenu du dépôt

### `notebooks/`

Contient le notebook final du benchmark.

### `docs/`

Contient la documentation du projet écrite directement en Markdown pour permettre une lecture fluide sur GitHub.

### `results/intermediates/`

Contient les résultats intermédiaires principaux :

- source structurée
- notes générées
- reconstruction

### `results/summaries/`

Contient les résultats finaux :

- métriques
- analyse des erreurs
- vérification

### `results/other_results/`

Contient des résultats secondaires utiles pour une lecture plus détaillée.

### `results/examples/`

Contient quelques patients exemples permettant de suivre la pipeline complète de bout en bout.

## Résultats principaux

Le benchmark final a été réalisé sur **40 patients** répartis entre plusieurs styles de notes.

Les grandes conclusions sont les suivantes :

- le pipeline fonctionne globalement bien
- les **medication requests** sont mieux reconstruites que les **conditions**
- les **conditions** ont de bons scores sémantiques mais des scores exacts plus faibles
- une partie importante de la perte d’information semble apparaître entre la source structurée et la note générée
- certains styles de notes sont plus robustes que d’autres

### Aperçu visuel des résultats

| Indicateur | Valeur |
|---|---:|
| Note vs recon conditions exact F1 | 0.525 |
| Note vs recon conditions sémantique F1 | 0.833 |
| Note vs recon medication requests exact F1 | 0.802 |
| Note vs recon medication requests sémantique F1 | 0.905 |
| Source vs recon conditions exact F1 | 0.440 |
| Source vs recon conditions sémantique F1 | 0.390 |
| Source vs recon medication requests exact F1 | 0.703 |
| Source vs recon medication requests sémantique F1 | 0.730 |
| Vérification taux consistent | 0.900 |
| Vérification confiance moyenne | 0.890 |

![Vue globale des F1 exacts et sémantiques](assets/figures/overall_f1.png)

*Figure : vue globale des performances exactes et sémantiques du benchmark.*

Pour la lecture détaillée :

- [Guide des résultats](docs/results_guide.md)
- [Rapport benchmark](docs/benchmark_report.md)

## Comment relancer le projet

Le projet est centré sur un notebook final.

### Étapes générales

1. ouvrir le notebook dans l’environnement adapté
2. installer les dépendances nécessaires
3. vérifier la configuration
4. exécuter les cellules dans l’ordre
5. récupérer les exports produits à la fin

Pour plus de détails :

- [Guide du notebook](docs/notebook_guide.md)

## Note d’environnement

Ce notebook a été principalement développé et exécuté dans Google Colab avec support GPU.

Certaines étapes dépendent :

- d’un runtime avec GPU
- d’un accès à Hugging Face
- d’utilitaires spécifiques à Colab pour la gestion des secrets et le téléchargement de fichiers

## Limites du projet

- les données utilisées sont synthétiques
- le benchmark final repose sur un échantillon limité de patients
- les résultats dépendent du modèle utilisé
- les métriques exactes sur les conditions restent exigeantes et pénalisent certaines reformulations

## Ordre de lecture conseillé

Si vous découvrez le projet, l’ordre conseillé est :

1. [Vue d’ensemble du projet](docs/project_overview.md)
2. [Pipeline détaillée](docs/pipeline_explained.md)
3. [Guide des résultats](docs/results_guide.md)
4. [Rapport benchmark](docs/benchmark_report.md)
5. [Exemples patients](results/examples/)
