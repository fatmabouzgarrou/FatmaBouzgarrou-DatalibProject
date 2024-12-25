# Utilisation de DataLib

Voici quelques exemples pour commencer à utiliser **DataLib** dans vos projets.

## 1. Chargement et traitement des données

**Charger un fichier CSV**

DataLib permet de charger facilement des fichiers CSV dans un DataFrame.

```python
import DataLib

# Charger un fichier CSV
data = DataLib.load_csv("path_to_file.csv")
```

**Normaliser les colonnes numériques**

La fonction `normalize()` permet de normaliser les colonnes numériques en les ramenant à une échelle commune (par exemple, entre 0 et 1).

```python
normalized_data = DataLib.normalize(data)
```

**Gérer les valeurs manquantes**

DataLib fournit une méthode `fill_missing_values()` pour gérer les valeurs manquantes. Vous pouvez remplir ces valeurs par une stratégie de votre choix (moyenne, médiane, suppression, etc.).

```python
# Remplir les valeurs manquantes par la moyenne
clean_data = DataLib.fill_missing_values(normalized_data, method='mean')
```

## 2. Statistiques descriptives

**Calculer la moyenne, la médiane et l'écart-type**

Les méthodes `mean()`, `median()`, et `std()` permettent de calculer les statistiques descriptives de base pour un jeu de données.

```python
mean = DataLib.mean(data)
median = DataLib.median(data)
std_dev = DataLib.std(data)
```

**Analyser les corrélations entre les colonnes**

La méthode `correlation()` génère une matrice de corrélation entre les différentes colonnes du dataset.

```python
correlation_matrix = DataLib.correlation(data)
```

## 3. Visualisation des données

**Créer un histogramme pour une colonne spécifique**

DataLib permet de générer des histogrammes pour visualiser la distribution des données d'une colonne.

```python
DataLib.plot_histogram(data, column='age')
```

**Créer une matrice de corrélation**

Vous pouvez également visualiser la matrice de corrélation entre toutes les colonnes avec la méthode `plot_correlation_matrix()`.

```python
DataLib.plot_correlation_matrix(data)
```

## 4. Sauvegarder et exporter les données traitées

DataLib vous permet de sauvegarder le DataFrame traité dans différents formats comme CSV ou Excel.

**Sauvegarder en CSV :**

```python
DataLib.save_to_csv(clean_data, "processed_data.csv")
```

**Sauvegarder en Excel :**

```python
DataLib.save_to_excel(clean_data, "processed_data.xlsx")
```