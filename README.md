# Prédiction de l'écurie vainqueure d'un Grand Prix de Formule 1

Notre projet a pour but d'explorer l'historique des données de la Formule 1 (de 1950 à aujourd'hui) pour construire un modèle capable de prédire quelle écurie (Constructeur) remportera une course donnée. 

## Nos objectifs

La Formule 1 est un sport régi par des milliers de variables. L'objectif est de déterminer si l'issue d'une course est prévisible en se basant sur des facteurs historiques et contextuels tels que :
- Les performances en qualifications.
- L'historique des pilotes et des écuries.
- Les caractéristiques des circuits.
- Les conditions de course (arrêts aux stands, tours rapides).

## Structure du Projet

Le projet est centralisé dans le notebook principal (actuellement `F1_prediction.ipynb`), qui suit cette logique :

1.  **Ingestion des Données** : Chargement de 14 datasets interconnectés (via Kaggle).
2.  **Audit & Nettoyage** :
    - Gestion des valeurs manquantes (`\N` converties en `NaN`).
    - Analyse des types de données et nettoyage des colonnes inutiles (URLs, etc.).
3.  **Exploration (EDA)** : Analyse univariée et multivariée pour comprendre les corrélations.
4.  **Modélisation** :
    - Comparaison de plusieurs algorithmes : **Logistic Regression, Decision Tree, Random Forest, XGBoost**.
    - Utilisation de `GridSearchCV` et `RandomizedSearchCV` pour l'optimisation.
5.  **Évaluation** : Analyse de l'importance des features (Feature Importance) et métriques de performance.

## Stack Technique

* **Langage** : Python 3.x
* **Manipulation de données** : Pandas, NumPy
* **Visualisation** : Matplotlib, Seaborn
* **Machine Learning** : Scikit-learn, XGBoost, SciPy

## Installation et Utilisation

1.  **Cloner le dépôt** :
    ```bash
    git clone [https://github.com/votre-username/F1-Winner-Prediction.git](https://github.com/votre-username/F1-Winner-Prediction.git)
    cd F1-Winner-Prediction
    ```

2.  **Installer les dépendances** (celles-ci sont listées dans `Requirements.txt`:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn xgboost scipy
    ```

3.  **Lancer le notebook** :
    Ouvrez `F1_prediction.ipynb` via Jupyter Notebook ou JupyterLab pour exécuter l'analyse complète.

## Résultats Clés

*Le modèle **XGBoost** (après fine-tuning) a démontré les meilleures performances.*
Les facteurs les plus déterminants identifiés par le modèle incluent (selon l'analyse d'importance des features) :
* La position sur la grille de départ (Grid Position).
* Les temps au tour précédents.
* L'historique récent de l'écurie.

## Données

Les données proviennent du [Dataset Formula 1 World Championship](https://www.kaggle.com/datasets/melissamonfared/formula-1/data) sur Kaggle. Elles comprennent des fichiers CSV séparés pour les circuits, constructeurs, pilotes, temps au tour, arrêts aux stands, etc.
