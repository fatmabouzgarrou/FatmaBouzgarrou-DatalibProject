# Exemples d'utilisation de DataLib

Ce fichier présente quelques exemples d'utilisation courante de **DataLib** pour charger, traiter, analyser et visualiser des données.

## 1. Chargement et traitement des données

### Charger un fichier CSV

DataLib permet de charger facilement un fichier CSV dans un DataFrame pour une analyse plus approfondie.

```python
import DataLib

# Charger un fichier CSV
data = DataLib.load_csv("path_to_file.csv")
```

### Normaliser les colonnes numériques

DataLib offre une fonctionnalité de normalisation pour rendre les données comparables, en ramenant les valeurs à une échelle commune (comme entre 0 et 1).

```python
# Normaliser les données
normalized_data = DataLib.normalize(data)
```

### Gérer les valeurs manquantes

Les valeurs manquantes peuvent être remplies ou supprimées à l'aide des méthodes intégrées de DataLib. Voici comment remplir les valeurs manquantes avec la moyenne des colonnes.

```python
# Remplir les valeurs manquantes avec la moyenne
clean_data = DataLib.fill_missing_values(normalized_data, method='mean')
```

## 2. Statistiques descriptives

### Calculer la moyenne, la médiane et l'écart-type

Vous pouvez facilement obtenir des statistiques descriptives comme la moyenne, la médiane et l'écart-type pour mieux comprendre vos données.

```python
# Calcul des statistiques descriptives
mean = DataLib.mean(data)
median = DataLib.median(data)
std_dev = DataLib.std(data)
```

### Analyser les corrélations entre les colonnes

Pour examiner les relations entre les variables, DataLib vous permet de calculer une matrice de corrélation.

```python
# Calcul de la matrice de corrélation
correlation_matrix = DataLib.correlation(data)
```

## 3. Visualisation des données

### Créer un histogramme pour une colonne spécifique

DataLib inclut une fonctionnalité de visualisation pour créer des histogrammes et mieux comprendre la distribution des données.

```python
# Créer un histogramme pour la colonne 'age'
DataLib.plot_histogram(data, column='age')
```

### Créer une matrice de corrélation

La fonction `plot_correlation_matrix()` génère une matrice de corrélation visuelle pour examiner les relations entre toutes les colonnes.

```python
# Créer une matrice de corrélation visuelle
DataLib.plot_correlation_matrix(data)
```

## 4. Sauvegarde des données traitées

### Sauvegarder les données traitées en CSV

Après avoir traité et nettoyé vos données, vous pouvez facilement les sauvegarder en fichier CSV.

```python
# Sauvegarder les données traitées en CSV
DataLib.save_to_csv(clean_data, "processed_data.csv")
```

### Sauvegarder les données traitées en Excel

DataLib prend également en charge l'exportation des données traitées au format Excel.

```python
# Sauvegarder les données traitées en Excel
DataLib.save_to_excel(clean_data, "processed_data.xlsx")
```
