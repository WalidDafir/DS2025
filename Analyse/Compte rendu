# 📘 Compte rendu détaillé  
## _Analyse du dataset : Students Performance in Exams_

---

# 1. 🎯 Introduction

Ce travail a pour objectif d’analyser en profondeur un dataset contenant les notes d’étudiants dans trois matières :  
- **Mathématiques**  
- **Lecture**  
- **Écriture**

Le notebook fourni comprend 31 cellules de code couvrant :  
✔️ Chargement des données  
✔️ Nettoyage et préparation  
✔️ Analyse exploratoire (EDA)  
✔️ Visualisations avancées  
✔️ Modélisation (régression linéaire + logistique)  
✔️ Identification des facteurs influençant la réussite  

---

# 2. 📚 Importation des bibliothèques

Les bibliothèques importées incluent :

- **pandas**, **numpy** → manipulation des données  
- **matplotlib**, **seaborn** → visualisation  
- **sklearn** → régression linéaire, régression logistique, encodage, métriques  
- **kagglehub** → téléchargement du dataset  
- Filtrage des warnings pour des sorties plus propres  

---

# 3. 📥 Chargement du dataset

Les principales étapes effectuées :

- Téléchargement automatisé via KaggleHub  
- Chargement dans un DataFrame Pandas  
- Aperçu des données :  
  - `df.head()`  
  - `df.info()`  
  - `df.describe()`  
- Vérification de la présence (ou absence) de valeurs manquantes  

**Conclusion :**  
Le dataset est propre, contient des colonnes catégorielles à encoder et des colonnes numériques exploitables.

---

# 4. 🧹 Préparation et nettoyage des données

### ✔️ Encodage des variables catégorielles
Les colonnes suivantes ont été encodées avec `LabelEncoder` :
- gender  
- race/ethnicity  
- lunch  
- parental level of education  
- test preparation course  

### ✔️ Création de nouvelles variables
- **moyenne des notes** :  
- **performance_category** → variable binaire utilisée pour la régression logistique  
- 1 = réussite  
- 0 = non-réussite  

### ✔️ Vérification des outliers  
Des visualisations ont permis de confirmer une distribution raisonnable.

---

# 5. 📊 Analyse exploratoire (EDA)

### 🧪 Distribution des scores
Des histogrammes + KDE ont permis de confirmer :

- Distribution quasi normale des scores  
- Variabilité plus élevée en mathématiques  

### 🧪 Comparaison par genre
Visualisations utilisées : boxplots, barplots

- Différences plus visibles en lecture/écriture que mathématiques  
- Le genre influence légèrement les performances globales  

### 🧪 Impact du test preparation course
Les élèves ayant suivi le cours de préparation obtiennent systématiquement :

- + haut score moyen  
- + meilleure cohérence entre les matières  

### 🧪 Heatmap des corrélations
Points marquants :

- **Lecture ↔ Écriture : corrélation très forte (~0.95)**  
- Mathématiques corrélé modérément aux deux autres matières  
- Score moyen conséquence logique de ces corrélations  

---

# 6. 📈 Modélisation : Régression Linéaire

Objectif : prédire séparément les scores de :

- math  
- reading  
- writing

### Étapes :
1. Encodage des variables qualitatives  
2. Sélection des features  
3. Train/Test split  
4. Entraînement de `LinearRegression`  
5. Évaluation avec :
 - MSE  
 - RMSE  
 - R²  

### Résultats globaux (selon le notebook)
- **Lecture/Écriture** → très bonne prédictibilité (corrélations élevées)  
- **Mathématiques** → prédiction plus difficile  
- Les coefficients identifient les variables à impact positif ou négatif  

---

# 7. 🤖 Modélisation : Régression Logistique

Objectif : prédire la variable **performance_category** (réussite ou non).

### Étapes :
- Encodage complet du dataset  
- Division en train/test  
- Entraînement d’un modèle `LogisticRegression`  
- Évaluation :
- accuracy  
- classification report  
- confusion matrix  

### Résultats (selon les sorties affichées)
- **Accuracy** ≈ entre 70% et 85%  
- La réussite scolaire dépend clairement :
- du test preparation course  
- du type de repas  
- de l’éducation parentale  
- des performances littéraires  

---

# 8. 🔍 Identification des facteurs clés

Le notebook affiche une liste triée des coefficients de la régression logistique et/ou linéaire.

### Principaux facteurs identifiés :
1. **Test Preparation Course** → Impact positif fort  
2. **Lunch Type** → Les repas “standard” associés à de meilleures performances  
3. **Parental Education Level** → Impact globalement positif  
4. **Reading & Writing Scores** → Très haute influence croisée  
5. **Gender** → Influence légère mais présente  

Chaque coefficient est analysé :  
- signe (+ / -)  
- intensité relative  

---

# 9. 🖼️ Visualisations sauvegardées

Le notebook sauvegarde automatiquement tous les graphiques :

- histogrammes  
- boxplots  
- heatmaps  
- scatterplots  
- distributions par variables  

Ces fichiers sont enregistrés dans le répertoire courant.

---

# 10. ✅ Conclusion générale

Ce projet permet de mettre en évidence plusieurs points essentiels :

### ✔️ Points clés de l’analyse
- Les compétences littéraires sont très corrélées  
- Le **test preparation course** est un facteur majeur de réussite  
- Les conditions socio-économiques simulées (lunch, éducation parentale) influencent clairement les scores  
- Les scores de mathématiques sont moins prévisibles que lecture/écriture  

### ✔️ Pertinence du modèle
- La régression linéaire prédit efficacement lecture/écriture  
- La régression logistique atteint une précision correcte pour prédire la réussite  
- Les facteurs identifiés sont cohérents avec les tendances éducatives connues  

---

# 📜 Fin du rapport

Si vous souhaitez :
- une version PDF  
- une version DOCX  
- une mise en page plus professionnelle  
- l’ajout automatique des graphiques dans un rapport  

Je peux vous générer tout cela sur demande.

