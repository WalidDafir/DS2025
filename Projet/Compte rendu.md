# 📊 Compte Rendu de l’Analyse de la Base de Données  
### À partir du notebook : *Consommation_Electrique_avec_Pandas_*

---

## 1. 🎯 Objectif de l’étude

L’objectif de ce projet est d’analyser la consommation électrique d’un foyer en utilisant le dataset **household_power_consumption**.  
Les tâches principales incluent :

- Chargement et nettoyage des données  
- Analyse exploratoire (EDA)  
- Visualisation des tendances énergétiques  
- Construction d’un modèle de régression linéaire pour prédire `Global_active_power`  

---

## 2. 🧼 Préparation et Nettoyage des Données

### 🔹 Fusion et Parsing des Dates
Les colonnes `Date` et `Time` ont été combinées pour former une colonne `DateTime`, ensuite convertie au format `datetime`.

### 🔹 Conversion des Types Numériques
Les colonnes suivantes, initialement de type texte, ont été converties en `float` :

- Global_active_power  
- Global_reactive_power  
- Voltage  
- Global_intensity  
- Sub_metering_1  
- Sub_metering_2  
- Sub_metering_3  

Les valeurs `"?"` ont été remplacées par `NaN`, puis supprimées avec les lignes incomplètes.

### 🔹 Données nettoyées et triées
Les lignes invalides ont été retirées, et les données ont été triées chronologiquement.

---

## 3. 📈 Analyse Exploratoire (EDA)

### 🔹 Statistiques descriptives
Les statistiques montrent :

- des valeurs généralement faibles pour la puissance active,  
- des pics ponctuels identifiables,  
- une forte variabilité dans certaines sous-mesures d’énergie.

### 🔹 Évolution de la consommation dans le temps
La courbe de `Global_active_power` démontre :

- des cycles journaliers,  
- des pics visibles à certaines heures,  
- une tendance générale relativement stable.

### 🔹 Distribution de la puissance active
L’histogramme accompagné du KDE montre une distribution asymétrique, indiquant :

- une majorité de consommations faibles,  
- des valeurs extrêmes occasionnelles.

### 🔹 Matrice de corrélation
Principaux enseignements :

- Forte corrélation entre `Global_active_power` et `Global_intensity`  
- Relations significatives entre certaines variables de sous-comptage (`Sub_metering_*`)  
- Corrélations plus faibles avec le `Voltage`

---

## 4. 🤖 Modélisation : Régression Linéaire

### 🔹 Variables explicatives utilisées

- Global_reactive_power  
- Voltage  
- Global_intensity  
- Sub_metering_1  
- Sub_metering_2  
- Sub_metering_3  

La variable cible est : **Global_active_power**.

### 🔹 Découpage des données
Les données sont divisées en :

- 80% pour l'entraînement  
- 20% pour le test

### 🔹 Entraînement et prédiction
Un modèle de régression linéaire a été entraîné avec scikit-learn.

### 🔹 Performance du modèle
Les métriques calculées :

- **MAE** : erreur moyenne  
- **MSE** : erreur quadratique  
- **RMSE** : racine de l’erreur quadratique  
- **R²** : proportion de variance expliquée  

Le modèle montre une capacité raisonnable à prédire la puissance active, mais reste limité par sa nature linéaire.

### 🔹 Visualisation des résultats
Le nuage de points *Valeurs réelles vs Valeurs prédites* montre :

- une corrélation visible,  
- mais une dispersion montrant que le modèle ne capture pas toute la complexité des données.

---

## 5. 📝 Conclusions

- Le dataset nécessite un nettoyage important dû aux valeurs manquantes et aux formats initiaux.  
- L’analyse exploratoire révèle des tendances temporelles et des corrélations utiles.  
- Le modèle de régression linéaire fournit une première estimation mais :

  - manque de précision,  
  - pourrait être amélioré avec des modèles non linéaires (Random Forest, XGBoost, LSTM, etc.).

---

## 6. 🚀 Recommandations

- Ajouter des variables temporelles : heure, jour, mois, saisonnalité.  
- Tester des modèles plus avancés pour améliorer la précision.  
- Réaliser une analyse détaillée des pics de consommation.  
- Construire un tableau de bord interactif pour le suivi énergétique (Plotly, Dash, Streamlit).

---

