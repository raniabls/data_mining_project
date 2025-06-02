# 🧪 Clustering d’Alliages Métalliques

Ce projet vise à analyser et regrouper différents alliages métalliques en fonction de leur composition chimique et de leurs propriétés physiques à l’aide d’algorithmes de **machine learning non supervisés**.

## 📁 Structure du Projet

Le pipeline est divisé en plusieurs étapes :

### 1. Prétraitement des données
- Lecture des données à partir d’un fichier `.ods` contenant plusieurs feuilles.
- Fusion de plusieurs tableaux en un seul DataFrame cohérent.
- Nettoyage des données : suppression des doublons, gestion des valeurs manquantes.
- Extraction des composants chimiques à partir des formules textuelles complexes (ex: `{[(Fe60 Co40)75 B20 Si5]96 Nb4}98 Cr2`).
- Création d’un tableau structuré avec chaque élément chimique dans une colonne distincte.
- Validation des éléments chimiques extraits avec la table périodique.

### 2. Clustering des Alliages
Nous avons appliqué **KMeans** pour regrouper les alliages, en utilisant plusieurs combinaisons de variables :
- Composition uniquement
- Composition + Tg
- Composition + Tg + Tx
- Ensemble complet (composition + Tg + Tx + Tl + Dmax)

Pour chaque cas :
- Détermination du **nombre optimal de clusters** via la méthode du **coude**.
- Évaluation de la qualité du clustering avec le **score de silhouette**.
- Réduction de dimension avec **PCA** pour visualisation 2D des clusters.

### 3. Résultats

| Sous-ensemble              | Nombre optimal de clusters (k) | Score de silhouette |
|----------------------------|-------------------------------:|---------------------:|
| Composition uniquement     | 4                              | 0.389                |
| Composition + Tg           | 2                              | 0.679                |
| Composition + Tg + Tx      | 2                              | 0.721                |
| Ensemble complet           | 2                              | 0.723                |

🔍 Le meilleur clustering est obtenu avec l’**ensemble complet**, avec un score de silhouette de **0.723**, indiquant une séparation de groupes pertinente.

## ⚙️ Technologies utilisées

- Python 3.x
- pandas
- numpy
- matplotlib
- scikit-learn
- re (expressions régulières)
- openpyxl / odfpy (lecture de fichiers .ods)

## 📌 Objectif

Ce projet vise à :
- Structurer des données chimiques non conventionnelles.
- Appliquer des méthodes d'apprentissage automatique non supervisées pour identifier des familles d’alliages.
- Préparer la base pour des recommandations de matériaux ou des études avancées en science des matériaux.

## 🔧 Exécution

```bash
pip install -r requirements.txt
python traitement_alliages.py
