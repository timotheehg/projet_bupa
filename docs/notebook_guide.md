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
- taxonomie
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
Calcul des métriques officielles et secondaires.

### Vérification
Ajout d’une couche de relecture automatique.

### Taxonomie
Classification des erreurs.

### Exports
Création des fichiers CSV finaux.

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

- [Notebook final](../notebooks/BUPA_benchmark_final.ipynb)

## Voir aussi

- [Pipeline détaillée](pipeline_explained.md)
- [Guide des résultats](results_guide.md)
