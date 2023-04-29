Link: https://realpython.com/python-keras-text-classification/

Application: Sentiment analysis, Text classification (i.e. detection of spam), auto tagging of customer queries, categorization of text into defined topics.
- My goal is to figure out if I can figure out what soft/hard skills are needed from a job description.

Set up a python virtual environment: [[private/personal/Setup Python Virtual Environment]]

**Choosing a Data Set**
Repository for ML Data Sets: https://archive.ics.uci.edu/ml/datasets/Sentiment+Labelled+Sentences
- Each review is marked with a score of 0 for negative sentiment, score of 1 for positive sentiment

How to predict the sentiment of the source:
- Count the freq. of each word in each sentence + tie this count back to the entire set of words
- Create a corpus (take the data and create a vocabulary from all words)
	- Vocabulary is a list of words from the text, with each word having an index
- This allows us to create a vector for a sentence where we count how many times a word appears in a sentence. Resulting vector is also called a feature vector (the dimension is a numeric or categorical feature, i.e. count of word in a vocabulary)
- Vocabulary serves as an index of each word and allows for the count of each word in a sentence to be represented by a vector 
- This new vector represents occurence of each word in the sentences based on the vocabulary
This is considered as a Bag of Words model.

**Define a Baseline model**
Split the data into a training and test set which will let me evacuate the accuracy, and check if the model generalizes well. This is to check if the model is **overfitting**.

Overfitting - the model is trained too well on training data (model is just memorizing the data). 

```
sklearn.model_selection.train_test_split(*arrays, **options) -> list
```
Options are the optional keywords to get a desired behavior:
- train_size, test_size - defines the size of training set and test set
- random_state - controls randomization during splitting
- shuffle - determines whether to shuffle dataset after splitting
- stratify - https://en.wikipedia.org/wiki/Stratified_sampling

https://docs.scipy.org/doc/scipy/reference/sparse.html
- Data type optimized for matrices with only a few non-zero elements (reduces memory loads)
- tokenization - separates the sentences into a set of tokens (removes punctuation and special character)

Classification model we use is logistic regression.

" You start by having a layer of input neurons where you feed in your feature vectors and the values are then feeded forward to a hidden layer. At each connection, you are feeding the value forward, while the value is multiplied by a weight and a bias is added to the value. This happens at every connection and at the end you reach an output layer with one or more output nodes. "




