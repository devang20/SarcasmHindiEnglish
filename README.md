**Problem Statement**

In this project, we carried out sarcasm detection in Hindi-English code-mixed data using bilingual word embeddings and several deep learning techniques.

**Dataset**

We used two types of twitter data- unlabeled and labeled. Unlabeled tweets were used to create embeddings. Labeled tweets were labeled as either sarcastic or non-sarcastic. This data was used to train the deep learning models.

The unlabeled data was of two types. One consisted of Hinglish tweets, other consisted of English along with Hinglish tweets. There were 422415 tweets in the Hinglish English dataset and 201238 tweets in the Hinglish dataset. Labeled dataset included 94788 tweets.

**Preprocessing**

We removed all Twitter mentions, hash tags, emojis, punctuations, special chars, URLs, words containing numbers from the tweets. Then we created four types of embeddings such as Word2Vec, FastText, multilingual BERT embeddings and IndicBERT embeddings.

**Model**

The implementation has been carried out in the following steps:

1\. **Preprocessing:** All Twitter mentions, hash tags, emojis, punctuations, special chars, URLs, words containing numbers were removed from both labeled and unlabeled data.

1\.1. **Creation of word embeddings:**  We used two types of data to create embeddings as mentioned before. Hinglish data consisted of Hindi English code-mixed tweets. Hinglish-English data consisted of Hindi-Endlish code-mixed tweets and purely English tweets.

These two type of data are used to create four types of embeddings such as Word2Vec, FastText, multilingual BERT and IndicBERT.

1\.2. **Dimensionality reduction:** For the multilingual BERT pretrained model the dimensionality of the embedding vector was 768. It was reduced to 300 by using PCA.

2\. **Training the deep learning models:** We used 70% of total labeled data for training our deep learning models and remaining 30% for testing the models. 10% of training data was used for validation testing. We have tried several deep learning models like LSTM, bidirectional LSTM (Bi-LSTM), attention bidirectional LSTM (attention Bi-LSTM), series CNN and parallel CNN.

**Results**

**Table 1: Accuracies of different embeddings and Deep Learning models on Hinglish-English Dataset**


||Word2VEC|FastText|Multilingual BERT|IndicBERT|
| :-: | :-: | :-: | :-: | :-: |
|Series CNN|90\.13%|91\.52%|-|-|
|Parallel CNN|90\.81%|92\.05%|-|-|
|LSTM|95\.22%|95\.1%|-|-|
|Bi-LSTM|95\.49%|95\.38%|-|-|
|Attention Bi-LSTM|95\.78%|95\.1%|96\.7%|97\.25%|

**Table 2: Accuracies of different embeddings and Deep Learning models on Hinglish Dataset**


||Word2VEC|FastText|Multilingual BERT|IndicBERT|
| :-: | :-: | :-: | :-: | :-: |
|Series CNN|88\.17%|87\.03%|-|-|
|Parallel CNN|94\.37%|81\.95%|-|-|
|LSTM|95\.5%|94\.8%|-|-|
|Bi-LSTM|95\.46%|95%|-|-|
|Attention Bi-LSTM|95\.68%|95\.08%|-|-|


**Confusion matrix for multilingial BERT and attention Bi-LSTM on Hinglish English Dataset**












**Confusion matrix for IndicBERT and attention Bi-LSTM on Hinglish English Dataset**












**Observations**

1\. Attention Bi-LSTM performed the best among all deep learning models.

2\. The order of the embeddings in terms of their overall performance is IndicBERT>multilingual BERT>Word2Vec>FastText where IndicBERT is the best performer and FastText is the worst.

3\. For multilingual BERT embeddings the attention Bi-LSTM model was overfit which we couldn’t rectify due to time constraint.











4\. For IndicBERT embeddings we prevented the attention Bi-LSTM from being overfit

by setting the value of the patience variable to 2 in the EarlyStopping funstion and the values of dropout and recurrent\_dropout as 0.3.














**Conclusion**

Considering the performances of all types of word embeddings and deep learning models we drew conclusion that IndicBeRT produced the best embeddings whereas Attention Bi-LSTM emerged as the best deep learning model.
