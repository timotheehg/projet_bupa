# Projet BUPA

## Présentation

Ce projet étudie un pipeline de reconstruction structurée de données médicales à partir de notes cliniques générées depuis des bundles FHIR synthétiques.

L'idée générale est la suivante :

1. partir d'un dossier patient structuré au format FHIR
2. filtrer l'information utile
3. construire une source structurée de référence
4. générer une note clinique non structurée
5. reconstruire une structure à partir de cette note
6. évaluer la qualité de la reconstruction
7. analyser les erreurs et les cas difficiles

Le projet se concentre principalement sur deux types d'information :

- les **conditions**
- les **medication requests**

## Navigation rapide

### Comprendre le projet
- [Vue d’ensemble du projet](docs/project_overview.md)
- [Pipeline détaillée](docs/pipeline_explained.md)
- [Guide du notebook](docs/notebook_guide.md)
- [Guide des résultats](docs/results_guide.md)
- [Carte du dépôt](docs/repository_map.md)

### Analyse et synthèse
- [Résumé de l’audit](docs/audit_summary.md)
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
└── results/
