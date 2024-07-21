## Spam Detection in Python

This project explores building a spam detection model using Python libraries and machine learning techniques.

### Libraries Used

* `nltk`: Natural Language Toolkit for text processing
* `numpy`: Numerical computations
* `pandas`: Data manipulation and analysis
* `scikit-learn`: Machine learning algorithms

### Data Preprocessing

1. **Import and Load Data:**
   - The code assumes a CSV file named `spam.csv` with specific columns (adapt accordingly).
   - Handles potential encoding issues (e.g., `encoding='ISO-8859-1'`).
2. **Clean and Prepare Data:**
   - Removes unnecessary columns (adjust column names if different).
   - Renames the remaining columns for clarity (`'data'` and `'labels'`).
   - Splits data into features (`X`) and target labels (`y`).
3. **Feature Engineering:**
   - Uses `CountVectorizer` to convert text data to numerical features (TF-IDF or other options could be explored).
   - Removes stop words (adjust `stop_words` parameter if needed).

### Model Building and Evaluation

1. **Train-Test Split:**
   - Splits data into training and testing sets (70%/30% split is common, adjust as needed).
2. **Model Training:**
   - Uses `MultinomialNB` for spam classification, considering class imbalance if present.
   - Trains the model on the training data.
3. **Model Evaluation:**
   - Calculates and prints training and testing accuracy.
   - Generates classification reports for in-depth performance analysis (precision, recall, F1-score, etc.).
   - Calculates and prints ROC-AUC scores for better evaluation in case of class imbalance.