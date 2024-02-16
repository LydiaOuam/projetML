# Rapport TP Deep Learning
## Le problème des SPAMs

- Chargez l'ensemble de données.
- Inspectez et nettoyez les données si nécessaire.
  - Vérifier les nulls => y'a pas de valeurs nulls
  - Vérifier les doublons => y'a 404 linges en double, on a supprimé en utilisant le code suivant
    ```python
     data = data.drop_duplicates(keep='first')
    ```
- Encodez les caractéristiques catégorielles en numérique.
  - J'ai encoder les valeurs de la colonne Class en transformant les chaines de caractère en valeurs binaires (0 et 1) en utilsant
    ```python
    encoder = LabelEncoder()
    ```
- Divisez vos données en ensembles d'entraînement et de test. 
- Utilisez FEATURE ENGINEERING pour créer des nouvelles colonnes
  - J'ai rajouté trois colonnes : nombre de caractères, nombre de mot et nombre de phrases.
  - Aussi j'ai utilisé le tfidf pour tokenizer la colonne SMS, ce qui a été utilisé dans l'entrainement du modèle MultinomialNB ``` mnb = MultinomialNB() ```
  - Enfin j'ai utilisé le word2Vec, plus précisement ``` word_vectors = api.load("glove-twitter-25") ``` pour tokenizer le SMS, et pour ce cas on a utilisé le modèle LogisticRegression ``` logreg = LogisticRegression()```

- L'évaluation des modèles est faites en utilisant la matrice de confusion et l'accuracy :
  - Pour le modèle MultinomialNB on a eu ceci  comme résultat :
    ![capturecranMLprojet](https://github.com/LydiaOuam/TPDP/assets/84903904/249c8b78-50c1-4f31-852d-2d63c028dc5b)
    
  - Pour le modèle LogisticRegression on a eu ceci  comme résultat :
    ```Accuracy: 0.9168278529980658```
    
