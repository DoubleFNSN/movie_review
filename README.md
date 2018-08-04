# Sentiment analysis on movie reviews
## About
<img align="right" src="https://kaggle2.blob.core.windows.net/competitions/kaggle/3971/logos/front_page.png" />

This project is an exploration of methods involved in natural language processing, and in this case, sentiment analysis with text classification.

The data is obtained from a Kaggle tutorial competition, [`Bag of Words Meets Bags of Popcorn`](https://www.kaggle.com/c/word2vec-nlp-tutorial/data), and consists of movie reviews from IMDB. The objective is to give a binary classification, indicating a positive or negative sentiment.

## Methodology
### Data preprocessing
Typical data cleaning steps for text include removing stopwords and normalizing text. In this example, we also implement removal of HTML tags.

### Feature extraction
#### Bag-of-words word counts
In a bag-of-words model, the sequence of words within a sentence does not matter. Taking an example from [Bag of Words Meets Bags of Popcorn](#bag-of-words-meets-bags-of-popcorn), we have two sentences:

```
Sentence 1: "The cat sat on the hat"
Sentence 2: "The dog ate the cat and the hat"
```

Given that the vocabulary from the two sentences is `{the, cat, sat, on, hat, dog, ate, and}`, we simply construct a vector based on the number of occurrences of each word in a sentence.

| Sentence                        | the | cat | sat | on | hat | dog | ate | and |
|---------------------------------|-----|-----|-----|----|-----|-----|-----|-----|
| The cat sat on the hat          | 2   | 1   | 1   | 1  | 1   | 0   | 0   | 0   |
| The dog ate the cat and the hat | 3   | 1   | 0   | 0  | 1   | 1   | 1   | 1   |

Thus, the vectors produced for the sentences are:

```
Sentence 1: [2, 1, 1, 1, 1, 0, 0, 0]
Sentence 2: [3, 1, 0, 0, 1, 1, 1, 1]
```

Each sentence can thus be transformed into a vector, with the length of the vector being the number of words in the vocabulary. During classification, the model will then possibly learn that higher occurrences of certain words are more likely to lead to a particular prediction.

### Classification
#### Machine learning
We use a **random forest classifier** with `SciKit-Learn` as a ML classifier for extracted features.

#### RNN


#### CNN


## Resources
### [Bag of Words Meets Bags of Popcorn](https://www.kaggle.com/c/word2vec-nlp-tutorial#part-1-for-beginners-bag-of-words)
This tutorial guides the user through constructing a **bag-of-words** classification model. It begins with data cleaning methods, before feature extraction by **word counts** and **word2vec**. Classification is done by **random forest**.

### [Predicting Movie Review Sentiment with TensorFlow and TensorBoard](https://medium.com/@Currie32/predicting-movie-review-sentiment-with-tensorflow-and-tensorboard-53bf16af0acf)

### [Implementing a CNN for Text Classification in Tensorflow](http://www.wildml.com/2015/12/implementing-a-cnn-for-text-classification-in-tensorflow/)