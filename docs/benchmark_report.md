# Rapport benchmark

## Objectif

Cette page résume les principaux enseignements du benchmark final.

## Taille du benchmark

Le benchmark final a été réalisé sur 40 patients.

Plusieurs styles de notes ont été utilisés pour tester la robustesse du pipeline face à des formes variées de rédaction clinique.

## Résultats principaux

### 1. Le pipeline fonctionne globalement bien
Les résultats montrent que la chaîne produit des reconstructions exploitables et qu’elle peut être benchmarkée de manière structurée.

### 2. Les medication requests sont mieux reconstruites que les conditions
C’est le constat principal du benchmark.

### 3. Les conditions ont un écart important entre exact et sémantique
Cela signifie que le pipeline retrouve souvent le bon sens clinique, mais pas toujours le bon libellé exact ou la bonne forme canonique.

### 4. Certains styles de note sont plus robustes que d’autres
Les styles ne se valent pas tous. Certains facilitent davantage la reconstruction.

### 5. Une partie de la perte apparaît avant la reconstruction finale
Les erreurs ne viennent pas seulement de l’extracteur final. Une partie de la perte semble venir de la transmission source -> note.

## Lecture recommandée des résultats

Pour lire les résultats :
- commencer par les synthèses globales
- regarder ensuite les résultats par style de note
- lire ensuite la taxonomie des erreurs
- consulter enfin les exemples patients

## Fichiers les plus importants

- [Scores globaux](../results/summaries/metrics/df_scores_overall_summary.csv)
- [Scores par style](../results/summaries/metrics/df_scores_summary_by_note_style.csv)
- [Taxonomie des erreurs](../results/summaries/errors/df_error_taxonomy.csv)
- [Vérification](../results/summaries/verification/df_verification.csv)
- [Cas difficiles](../results/summaries/errors/df_hard_cases_by_note_style.csv)

## Conclusion

Le benchmark est globalement positif.

Le pipeline est particulièrement convaincant sur les medication requests.
Le principal axe d’amélioration concerne les conditions, en particulier leur fidélité exacte tout au long de la chaîne.
