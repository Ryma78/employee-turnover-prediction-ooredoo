Prédiction du Turnover des Employés
Ce projet a pour objectif de prédire le turnover des employés au sein d'une entreprise en utilisant des modèles de Machine Learning. Il comprend une exploration des données, un nettoyage et une préparation, une modélisation et le déploiement d'une application Shiny interactive.

Structure du Projet
turnover predection v.f.xlsx: Le jeu de données initial contenant les informations sur les employés.
dataset_clean_final.csv/dataset_clean_final.xlsx: Le jeu de données après le nettoyage et la préparation initiale.
dataset_clean_encoded_final.csv/dataset_clean_encoded_final.xlsx: Le jeu de données après l'encodage des variables catégorielles.
random_forest_model.rds: Le modèle Random Forest entraîné, sauvegardé pour un déploiement ultérieur.
model_columns.rds: Les noms des colonnes utilisées pour l'entraînement du modèle, nécessaires pour garantir que les nouvelles données ont la même structure.
app.R: Le code source de l'application Shiny pour la prédiction interactive.
Pré-requis
Pour exécuter ce projet, vous aurez besoin de R et des packages suivants:

readxl
dplyr
stringr
ggplot2
caret
rpart
rpart.plot
randomForest
fastDummies
writexl
shiny
Vous pouvez installer ces packages avec la commande suivante dans votre console R:

install.packages(c("readxl", "dplyr", "stringr", "ggplot2", "caret", "rpart", "rpart.plot", "randomForest", "fastDummies", "writexl", "shiny"))
Utilisation
1. Préparation des Données et Entraînement du Modèle
Le notebook contient toutes les étapes de chargement, de nettoyage, de préparation des données et d'entraînement des modèles de Machine Learning (Régression Logistique, Arbre de Décision, Random Forest).

Les étapes clés incluent:

Nettoyage des données: Renommage des colonnes, standardisation des valeurs textuelles, gestion des doublons.
Traitement des valeurs manquantes: Identification des colonnes avec des valeurs manquantes.
Encodage des variables: Conversion des variables catégorielles en format numérique (One-Hot Encoding, Recodage).
Sélection des variables: Analyse des corrélations avec la variable cible pour identifier les caractéristiques importantes.
Modélisation: Entraînement et évaluation de différents modèles de classification.
2. Déploiement de l'Application Shiny
Le modèle Random Forest entraîné est sauvegardé (random_forest_model.rds) ainsi que les noms des colonnes utilisées (model_columns.rds). Ces fichiers sont utilisés par l'application Shiny pour effectuer des prédictions.

Pour exécuter l'application Shiny:

Assurez-vous d'avoir les fichiers random_forest_model.rds, model_columns.rds et app.R dans le même répertoire.
Ouvrez le fichier app.R dans RStudio ou un éditeur de texte.
Exécutez l'application en utilisant la commande suivante dans votre console R (dans le répertoire du projet):
library(shiny)
runApp("app.R")
L'application s'ouvrira dans votre navigateur web, vous permettant d'entrer des données d'employés et d'obtenir une prédiction de turnover.
