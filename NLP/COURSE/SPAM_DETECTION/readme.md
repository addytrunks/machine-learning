## Spam Detection in Python

This project implements a spam detection model using Multinomial Naive Bayes in Python.

### Libraries

The following libraries are used in this project:

* `nltk`: Natural Language Toolkit for text processing.
* `numpy`: Numerical computing library.
* `pandas`: Data analysis and manipulation library.
* `sklearn.model_selection`: Machine learning model selection utilities from scikit-learn.
* `sklearn.metrics`: Machine learning model evaluation metrics from scikit-learn.
* `sklearn.feature_extraction.text`: Feature extraction techniques for text data from scikit-learn.
* `sklearn.naive_bayes`: Naive Bayes classifiers from scikit-learn.

### Data Preprocessing

1. **Import the dataset:** The spam dataset is loaded using pandas and stored in a DataFrame named `df`.
2. **Data Cleaning:** Unnecessary columns are removed from the DataFrame.
3. **Feature and Label Separation:** The DataFrame is restructured to separate the text data (`data`) and labels (`labels`) into distinct columns.
4. **Train-Test Split:** The data is split into training and testing sets using `train_test_split` from scikit-learn for model evaluation.

### Text Preprocessing

1. **Tokenization:** Text data is split into individual words using `word_tokenize` from NLTK.
2. **Part-of-Speech Tagging:** Parts of speech (POS) tags are assigned to each word using `nltk.pos_tag`.
3. **Lemmatization:** Words are reduced to their base form using WordNetLemmatizer from NLTK. A custom `LemmaTokenizer` class is created to perform this step during the feature vectorization process.
4. **Stop Word Removal:** Common words (stop words) are removed from the preprocessed text using `stop_words='english'` argument in `CountVectorizer`.

### Feature Extraction

* **CountVectorizer:** A `CountVectorizer` object is created from scikit-learn to transform the preprocessed text data into numerical feature vectors. The custom `LemmaTokenizer` is used for tokenization and stop word removal during this step.

### Model Training

* **Multinomial Naive Bayes:** A Multinomial Naive Bayes classifier (`MultinomialNB`) is created and trained on the training feature vectors (`X_train`) and labels (`y_train`).

### Model Evaluation

1. **Accuracy:** The model's accuracy on the training and testing sets is evaluated using the `model.score` method.
2. **Classification Report:** Classification reports are generated using `classification_report` to analyze the model's performance on both the training and testing sets. This report provides metrics like precision, recall, F1-score, and support for each class (spam and not spam).
3. **ROC-AUC Score:** Due to potential class imbalance in spam datasets, ROC-AUC score is calculated using `roc_auc_score` to evaluate model performance. This metric is more robust to class imbalances compared to accuracy.