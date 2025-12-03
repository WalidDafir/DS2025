# Compte rendu détaillé du travail de nettoyage du jeu de données OpenFoodFacts

## 1. Objectif général
Le travail vise à produire un dataset propre pour une analyse fiable. Le traitement couvre la lecture du fichier brut, l’étude des valeurs manquantes, la suppression des incohérences, la gestion des doublons, le contrôle des valeurs nutritionnelles et l’export du fichier final.

## 2. Chargement et exploration initiale
- Importation de NumPy, Pandas, Matplotlib, Seaborn et OS.
- Lecture du fichier en utilisant `read_csv` avec le séparateur tabulation.
- Inspection de quelques lignes pour confirmer le format.
- Vérification de la dimension du dataset. Le fichier contient un grand nombre de lignes et un nombre important de variables.

## 3. Analyse des valeurs manquantes
### 3.1. Calcul des taux de nullité
- Une fonction dédiée calcule le pourcentage de null pour chaque variable.
- Les variables avec plus de 50 de valeurs null sont isolées pour examen.
- Les variables avec 100 de valeurs null sont retirées car elles ne contiennent aucune information exploitable.

### 3.2. Impact du nettoyage
- La suppression de ces colonnes réduit la complexité du dataset.
- Le dataset devient plus léger et plus cohérent pour les analyses suivantes.

## 4. Gestion des doublons
- Recherche de doublons sur la variable code.
- Suppression des entrées répétées pour éviter les biais dans les analyses.

## 5. Nettoyage des données nutritionnelles
### 5.1. Contrôles sur les valeurs pour 100 g
Les colonnes suivantes sont contrôlées.
- protéines_100g
- fat_100g
- carbohydrates_100g
- sugars_100g  
Un produit ne doit pas dépasser 100 g pour 100 g. Les lignes qui contiennent des valeurs supérieures à 100 sont supprimées.

### 5.2. Contrôles logiques entre nutriments
- Les acides gras saturés doivent être inférieurs aux acides gras totaux.
- Le sodium doit être inférieur au sel total.
- Les lignes non conformes sont supprimées car elles indiquent une erreur d’imputation.

### 5.3. Énergie maximale
- L’énergie doit rester inférieure à 3700 kJ pour 100 g.
- Elle doit rester inférieure à 900 kcal pour 100 g.
- Les produits dépassant ces limites sont retirés.

## 6. Gestion des valeurs extrêmes
### 6.1. Variables ciblées
- additives_n
- serving_quantity

### 6.2. Méthode appliquée
- Calcul de la médiane pour chaque variable.
- Calcul de l’écart type pour détecter les valeurs éloignées.
- Visualisation de la dispersion pour confirmer les anomalies.
- Suppression des valeurs extrêmes situées en dehors des plages raisonnables.

## 7. Travail sur les variables Nutriscore
### 7.1. Calcul du Nutriscore
- Création de deux nouvelles colonnes pour le score et la lettre calculée.
- Extraction d’un échantillon pour vérifier la cohérence.

### 7.2. Test de précision
- Comparaison entre le Nutriscore calculé et celui présent dans les données originales.
- Le taux de précision est inférieur à 50.
- Les variables calculées sont supprimées car elles ne sont pas fiables pour une analyse sérieuse.

## 8. Structure finale et export
- Inspection du dataset final avec `info` pour vérifier les types et les colonnes restantes.
- Réindexation sur la variable code.
- Export au format CSV propre sous le nom cleaned_openfoodfacts.csv.

## 9. Résultat
Le dataset est maintenant réduit, cohérent, sans doublons, sans incohérences nutritionnelles et sans valeurs extrêmes inutiles. Il est prêt pour une analyse exploratoire et pour la production de visualisations fiables.
