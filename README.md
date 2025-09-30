# 🎬 Système de recommandation de films (MovieLens + PySpark)

## 📌 Description
Ce projet construit un **système de recommandation de films** à partir du jeu de données **MovieLens**. Il combine **PySpark** pour le traitement distribué et des modèles de **régression** + **filtrage collaboratif (ALS)** pour prédire des notes et recommander des films.

## 🧠 Approche technique
### Filtrage collaboratif — ALS (Spark MLlib)
- Facteurise la matrice `Utilisateurs × Films` en deux matrices latentes.
- Prédit les notes manquantes et recommande des films semblables à ceux appréciés.
- Avantages : efficace et scalable pour de grands jeux de données.

### Modèle supervisé — Régression linéaire
- Utilise des features comme l’âge, le genre et l’occupation de l’utilisateur, ainsi que des attributs du film.
- Optimisé et évalué avec **RMSE** sur un split train/test.

### Évaluation
- Séparation entraînement/test.
- Métriques : **RMSE** (erreur de prédiction), et, si applicable, **précision/rappel** sur des tâches dérivées.

## 🛠️ Stack & dépendances
- **Python 3.x**
- **Apache Spark / PySpark**
- **Pandas**, **Matplotlib**

## 📂 Données & structure
- `Projet.ipynb` — notebook principal (chargement, préparation, modèles).
- `ratings.csv` — notes des utilisateurs.
- `movies.csv` — métadonnées des films.
- `users.csv` — informations démographiques.

Le notebook :
1) Définit les **schémas** de chargement (Spark `StructType`).  
2) **Joint** ratings/movies/users pour obtenir un dataset unique.  
3) Fait des **agrégations** (distributions de `Rating`, `Age`, `Gender`, etc.).  
4) Entraîne un modèle **ALS** + un modèle de **régression** et compare.

## ⚙️ Installation & exécution
1. Cloner le dépôt
   ```bash
   git clone https://github.com/<votre-utilisateur>/<nom-du-projet>.git
   cd <nom-du-projet>
