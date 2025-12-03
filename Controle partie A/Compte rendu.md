# Compte rendu du travail de nettoyage des données OpenFoodFacts

## Objectif
Préparer un jeu de données propre et exploitable pour une analyse exploratoire. Le travail traite les valeurs manquantes, les incohérences, les doublons et les anomalies numériques.

## Chargement des données
- Importation des librairies NumPy, Pandas, Matplotlib, Seaborn, OS.
- Lecture du fichier CSV OpenFoodFacts avec `read_csv`, séparateur tabulation.
- Affichage d’un échantillon pour vérifier la structure.
- Le dataset contient plusieurs milliers de lignes et plusieurs centaines de variables.

## Analyse des valeurs manquantes
- Calcul du taux de valeurs manquantes par variable.
- Identification des colonnes dont le taux dépasse 50.
- Suppression des colonnes avec 100 de valeurs nulles.
- Filtrage des colonnes très peu renseignées afin de réduire le bruit.

## Gestion des doublons
- Suppression des lignes duplicatives basées sur la colonne code.

## Nettoyage des variables quantitatives
### Contrôle des valeurs sur 100 g
- Vérification des colonnes protéines, lipides, glucides, sucres.
- Suppression des lignes où une valeur dépasse 100 g pour 100 g de produit.

### Contrôles nutritionnels logiques
- Les acides gras saturés ne doivent pas dépasser les acides gras totaux.
- Le sodium doit rester inférieur au sel total.
- Suppression des lignes non conformes.

### Contrôle de la densité énergétique
- L’énergie ne doit pas dépasser 3700 kJ ou 900 kcal pour 100 g.
- Élimination des produits dépassant ces seuils.

## Traitement des valeurs extrêmes
- Calcul de la médiane et de l’écart type sur les variables additives_n et serving_quantity.
- Visualisation pour repérer les dispersions.
- Nettoyage des valeurs aberrantes situées loin des métriques calculées.

## Préparation des variables Nutriscore
- Création de variables calculées pour le score global et la lettre Nutriscore.
- Extraction d’un échantillon pour vérification.
- Comparaison des Nutriscores calculés avec ceux du dataset.
- Le taux de précision obtenu est inférieur à 50, ce qui montre que la reconstruction du Nutriscore n’est pas fiable avec les seules variables présentes.
- Suppression des colonnes de Nutriscore calculé.

## Finalisation du nettoyage
- Vérification de la structure finale du dataset propre.
- Export du fichier nettoyé sous le nom cleaned_openfoodfacts.csv.
- Le dataset nettoyé est prêt pour une analyse exploratoire.


