# Examples

Ce dossier contient quelques exemples patients permettant de suivre la pipeline complète de bout en bout :

**filtered -> gold -> note -> reconstruction -> score -> vérification -> taxonomie**

## Objectif

Ces exemples servent à illustrer concrètement le fonctionnement du projet sur des cas individuels.

Ils permettent de relier :

- les résultats globaux du benchmark,
- la logique du pipeline,
- et des cas patients réels issus de l'expérience.

## Contenu attendu par patient

Chaque sous-dossier patient peut contenir :

- `01_filtered.json`
- `02_gold.json`
- `03_note.txt`
- `04_reconstruction.json`
- `05_score.json`
- `06_verification.json`
- `07_taxonomy.json`
- `README.md`

## Utilité

Ce sous-dossier est particulièrement utile pour :

- comprendre le projet sans lire uniquement des tables agrégées,
- montrer des cas concrets dans une soutenance,
- illustrer visuellement la chaîne complète de traitement.
