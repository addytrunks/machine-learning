# **VECTOR MODELS & TEXT PREPROCESSING**

## **BASIC DEFINITIONS (FOR NLP)**

1.  Tokens: A sentence consists of words or "*tokens".*

2.  Corpus: In the context of ML, corpus refers to the dataset a.k.a a *large collection of writings*

3.  N-Gram: N consecutive terms. E.g.: Hello world - 2 gram/bigram.

## **WHAT IS A VECTOR (IN THE CONTEXT OF ML)?**

-   Represent an array of scalars.

**BAG OF WORDS**

**-** Numerical representation of text. (the order of the numbers may
not be the same as the order of words in the text).

\- Vector and ML models use this approach, whereas DL does not.

## **COUNT VECTORIZER**

-   Bag of Words approach.

-   Tokenization - Process of converting a string into a list of words.

-   The final vector must be normalized.

## **TOKENIZATION (WE DO NOT USE ML FOR THIS)**

-   Character-based tokenization - Vocabulary size is small and easy to represent.

-   Subword-based tokenization

-   Word-based tokenization

    -   The main disadvantage is that there are millions of words out there for which a vector of a million entities might be required which is space-consuming.

    -   Word-based tokenization has a lot of meaning.

**STOP-WORDS**

-   Words that are not useful/meaningful.

-   Useful to reduce dimensionality

## 

## **STEMMING AND LEMMATIZATION**

-   Words like running, ran, and run have the same meaning in some contexts. However, they may not be treated as such during count vectorization and take up more space.

- One way to solve this is to consider the *root* words only. This can be done through two of the most popular methods: stemming and lemmatization.

-   Stemming - very crude, chops off the end of the word. PorterStemming is a widely used algo.

-   Lemmatization - much more sophisticated, uses actual rules of the language

**VECTOR SIMILARITY**

-   Finding out similar words after converting them into vectors.

-   Application - Article Spinning

    -   Generate new articles by replacing the existing article with new words that are similar to the old words.

    -   Black Hat SEO

-   Two vectors are similar when the:

    -   Euclidean distance between them is small and the other way around for dissimilar vectors.

    -   The cosine of the angle between them

## **TF-IDF (TERM FREQUENCY-INVERSE DOCUMENT FREQUENCY)**

-   Stopwords are unlikely to be used in NLP tasks.

-   The problem is, that stopwords/words we want to ignore may appear in many other documents.

-   **Term Frequency** (No of times a specific word appears)/ **DocumentFrequency** (No of documents that specific word appears).

-   Advantage: Considers the weight/importance/emphasis of each word.

-   $tfid(t,d)\  = \ tf(t,d)*\ idf(t)$

> $tf(t,d)$ = No of times word 't' appears in the document 'd'/ Total no
> of tokens in 'd'
>
> $idf(t)$ = log(N/N(t)) =\> N: No of documents ; N(t) =\> No of
> documents the word 't' occ*ur*

-   *"TF-IDF vectorization is essential for text data analysis because
    > it helps emphasize important terms while reducing the noise from
    > common words. It is advantageous in scenarios like document
    > classification, where distinguishing between topics based on
    > unique terms is crucial."*

-   Traits of words with high TFIDF score:

    -   The no of times the word occurs is high

    -   The word should be relatively unique compared to the other words in the document.

-   Won\'t consider semantic understanding.

**MOVIE RECOMMENDATION PROJECT:**

1.  Get the final string of each movie by concatenating the keywords into one string.

2.  Convert them into vectors using *TFIDFVectorizer*.

3.  Create a movie to index mapping.

4.  Get the movie prompt from the user and get its vector from the TFIDF vectors.

5.  Perform a cosine similarity search with the other movie vectors and store them in an array.

6.  Sort them in descending order.

7.  Get hold of the indices and return the first *n* movie names.

## **WORD-TO-INDEX MAPPING**

-   The problem with the count vectorization/TFIDF method is that we don't know which word is associated with each index.

## **NEURAL WORD EMBEDDINGS**

-   Each word is converted into a vector, so essentially each document consists of a collection/sequence of vectors.

-   Consider the sequence of words.

**How Word2Vec Works**:

-   **Training Data**: The model is trained on a large corpus of text.

-   **Context Window**: For each word in the text, the model looks at a window of surrounding words (context).

-   **Two Models**:

    -   **CBOW (Continuous Bag of Words)**: Predicts a word given its context. For example, given the context \"the cat sat on the \_\_\_,\" it predicts \"mat.\"

    -   **Skip-gram**: Predicts the context of a given word. For example, given the word \"cat,\" it predicts words like \"the,\" \"sat,\" and \"on.\"

**Learning Process**:

-   The model learns by adjusting the word vectors (embeddings) to make predictions more accurate over time.

-   For example, if the context words around \"king\" often include \"queen,\" \"royal,\" and \"crown,\" the vectors for these words will be adjusted to be close to each other.

-   The number of word vectors, or the dimensionality of the word embeddings, in a model like Word2Vec, is a hyperparameter that you, as the user, must decide before training the model.
