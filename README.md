<font size="+4">**Problem Statement**</font>

In this project, we carried out sarcasm detection in Hindi-English code-mixed data using bilingual word embeddings and several deep learning techniques.

<font size="+24">**Dataset**</font>

We used two types of twitter data- unlabeled and labeled. Unlabeled tweets were used to create embeddings. Labeled tweets were labeled as either sarcastic or non-sarcastic. This data was used to train the deep learning models.

The unlabeled data was of two types. One consisted of Hinglish tweets, other consisted of English along with Hinglish tweets. There were 422415 tweets in the Hinglish English dataset and 201238 tweets in the Hinglish dataset. Labeled dataset included 94788 tweets.

<font size="+2">**Preprocessing**</font>

We removed all Twitter mentions, hash tags, emojis, punctuations, special chars, URLs, words containing numbers from the tweets. Then we created four types of embeddings such as Word2Vec, FastText, multilingual BERT embeddings and IndicBERT embeddings.

<font size="+2">**Model**</font>

The implementation has been carried out in the following steps:

1\. <font size="+2">**Preprocessing:**</font> All Twitter mentions, hash tags, emojis, punctuations, special chars, URLs, words containing numbers were removed from both labeled and unlabeled data.

1\.1. <font size="+2">**Creation of word embeddings:**</font>  We used two types of data to create embeddings as mentioned before. Hinglish data consisted of Hindi English code-mixed tweets. Hinglish-English data consisted of Hindi-Endlish code-mixed tweets and purely English tweets.

These two type of data are used to create four types of embeddings such as Word2Vec, FastText, multilingual BERT and IndicBERT.

1\.2. <font size="+2">**Dimensionality reduction:**</font> For the multilingual BERT pretrained model the dimensionality of the embedding vector was 768. It was reduced to 300 by using PCA.

2\. <font size="+2">**Training the deep learning models:**</font> We used 70% of total labeled data for training our deep learning models and remaining 30% for testing the models. 10% of training data was used for validation testing. We have tried several deep learning models like LSTM, bidirectional LSTM (Bi-LSTM), attention bidirectional LSTM (attention Bi-LSTM), series CNN and parallel CNN.


**Confusion matrix for multilingial BERT and attention Bi-LSTM on Hinglish English Dataset**












**Confusion matrix for IndicBERT and attention Bi-LSTM on Hinglish English Dataset**













<font size="+2">**Conclusion**</font>

Considering the performances of all types of word embeddings and deep learning models we drew conclusion that IndicBeRT produced the best embeddings whereas Attention Bi-LSTM emerged as the best deep learning model.
