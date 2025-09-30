📌 Description

Ce projet vise à construire un système de recommandation de films à partir du jeu de données MovieLens.
Le dataset contient plus de 26 millions de notes attribuées par 270 000 utilisateurs à environ 45 000 films.

L’objectif est de :

Explorer et prétraiter les données.

Visualiser les tendances (notes, genres, démographie des utilisateurs).

Construire un modèle de régression pour prédire les notes.

Développer un système de filtrage collaboratif pour générer des recommandations.

Le projet est implémenté avec Apache Spark (PySpark) pour le traitement distribué et Matplotlib pour la visualisation.

🛠️ Technologies utilisées

Python 3.x

PySpark (Spark MLlib, DataFrames)

Matplotlib

Pandas

🧠 Approche technique

Le système de recommandation implémenté repose sur plusieurs techniques :

1. Filtrage collaboratif (Collaborative Filtering)

Utilisation de l’algorithme ALS (Alternating Least Squares) de Spark MLlib.

Principe :

Les utilisateurs et les films sont représentés comme des vecteurs dans un espace latent.

On approxime la matrice Utilisateur × Film contenant les notes observées par le produit de deux matrices (facteurs latents).

Cela permet de prédire les notes manquantes et de recommander des films similaires à ceux déjà appréciés.

2. Régression linéaire pour la prédiction de notes

Construction d’un modèle de régression supervisée basé sur des features (âge, genre, occupation de l’utilisateur, genre du film, etc.).

Objectif : prédire la note probable qu’un utilisateur attribuerait à un film.

Évaluation avec des métriques comme RMSE (Root Mean Squared Error).

3. Évaluation du modèle

Division en ensemble d’entraînement et de test.

Utilisation de métriques de précision et erreur quadratique moyenne pour valider la qualité des prédictions.

Comparaison entre la régression classique et le filtrage collaboratif.

4. Avantages de l’approche

Le filtrage collaboratif ALS est adapté aux grands jeux de données comme MovieLens (26M notes).

L’utilisation de PySpark permet un traitement distribué et scalable.

La combinaison de la régression et du filtrage collaboratif offre un système hybride plus robuste.

📂 Structure du projet

Projet.ipynb : notebook principal contenant l’analyse et les modèles.

ratings.csv : notes attribuées par les utilisateurs.

movies.csv : informations sur les films.

users.csv : données démographiques des utilisateurs.
