# Guide du notebook

## Rôle du notebook

Le notebook final est le cœur du projet.

Il orchestre toute la pipeline :

- téléchargement et préparation des données
- filtrage
- construction du gold source
- génération des notes
- reconstruction
- scoring
- vérification
- analyse des erreurs
- exports finaux

## Philosophie du notebook

Le notebook n’est pas seulement un script.

Il sert aussi de support de lecture :

- les étapes sont séparées
- les noms sont explicites
- les sorties sont exportées en tables
- le benchmark est lisible

## Grandes sections

### Préparation

Initialisation de l’environnement, dépendances, paramètres globaux.

### Données

Téléchargement et chargement des bundles FHIR synthétiques.

### Préfiltrage

Réduction du bruit structurel avant les étapes LLM.

### Gold source

Construction de la source structurée utilisée pour générer les notes.

### Génération de notes

Production de notes cliniques de plusieurs styles.

### Reconstruction

Extraction structurée à partir du texte des notes.

### Scoring

Calcul des métriques selon deux lectures :

- **note vs recon**
- **source vs recon**

### Vérification

Ajout d’une couche de relecture automatique.

### Analyse des erreurs

Interprétation des écarts observés, des types d’erreurs et des cas difficiles.

### Exports

Création des fichiers CSV finaux.

## Fichiers exportés principaux

Le notebook produit notamment les fichiers suivants :

- `df_gold.csv`
- `df_notes.csv`
- `df_recon.csv`
- `df_gold_conditions_long.csv`
- `df_gold_medreq_long.csv`
- `df_recon_conditions_long.csv`
- `df_recon_medreq_long.csv`
- `df_scores.csv`
- `df_scores_overall_summary.csv`
- `df_scores_summary_by_note_style.csv`
- `df_error_analysis.csv`
- `df_error_types_by_note_style_conditions.csv`
- `df_error_types_by_note_style_medication_requests.csv`
- `df_hard_cases_by_note_style.csv`
- `df_verification.csv`
- `df_export_review.csv`
- `df_index.csv`

## Comment relancer le notebook

### Pré-requis

- environnement compatible
- dépendances installées
- accès au modèle utilisé
- session stable

### Règles importantes

- exécuter les cellules dans l’ordre
- ne pas modifier les paramètres au milieu d’un run final
- utiliser la cellule de reset des sorties si nécessaire avant benchmark

## Notebook du dépôt

- `BUPA_benchmark_final.ipynb`

## Voir aussi

- [Pipeline détaillée](pipeline_explained.md)
- [Guide des résultats](results_guide.md)
