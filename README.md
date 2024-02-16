# Rapport TP Deep Learning
## Le problème des SPAMs

- Chargez l'ensemble de données.
- Inspectez et nettoyez les données si nécessaire.
  - Vérifier les nulls => y'a pas de valeurs nulls
  - Vérifier les doublons => y'a 404 linges en double, on a supprimé en utilisant le code suivant
    ```python data = data.drop_duplicates(keep='first')```
- Encodez les caractéristiques catégorielles en numérique.
  - J'ai encoder les valeurs de la colonne Class en transformant les chaines de caractère en valeurs binaires (0 et 1) en utilsant ```python encoder = LabelEncoder()```
- Divisez vos données en ensembles d'entraînement et de test. 
- Utilisez FEATURE ENGINEERING pour créer des nouvelles colonnes
  - J'ai rajouté trois colonnes : nombre de caractères, nombre de mot et nombre de phrases.
  - Aussi j'ai utilisé le tfidf pour tokenizer la colonne SMS, ce qui a été utilisé dans l'entrainement du modèle ```python mnb = MultinomialNB()```
  - Enfin 
- Utilisez un algorithme de votre choix pour faire la classification.
- Faites des prédictions.
- Évaluer le modèle à l'aide de la matrice de confusion et du rapport de classification.
