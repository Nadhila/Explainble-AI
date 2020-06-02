# Review 3 Different Methods for Explainability Artificial Intelligence (XAI)

In this repository, we use 3 different methods of XAI on Machine Learning Model for Text Classification (Sentiment classification using Bi-LSTM and BI-GRU+LSTM+CNN). 

Explainable Methods we use :

* LIME explanation method for text:Local interpretable model-agnostic explanations (LIME) are a concrete implementation of local surrogate models. Surrogate models are trained to approximate the predictions of the underlying black box model. Instead of training a global surrogate model, LIME focuses on training local surrogate models to explain individual predictions. LIME for text has variations of the data which are generated differently: Starting from the original text, new texts are created by randomly removing words from the original text. The dataset is represented with binary features for each word. A feature is 1 if the corresponding word is included and 0 if it has been removed.
* SHAP (kernel Explanation) method for text: SHAP (SHapley Additive exPlanations) is a game theoretic approach to explain the output of any machine learning model.SHAP has the goal to explain the prediction of an instance x by computing the contribution of each feature to the prediction
* Anchor explanation method: The anchor algorithm is based on the Anchors: High-Precision Model-Agnostic Explanations paper by Ribeiro et al. For text classification, an interpretable anchor consists of the words that need to be present to ensure a prediction, regardless of the other words in the input.

To compare the methods we use the commons datasets :

* Review of Indonesian e-comerce for classification dataset “blibli.com”
* US Airlines for Sentiment classification [dataset](https://www.kaggle.com/crowdflower/twitter-airline-sentiment)


Contributor:
* [Nadhila](https://github.com/Nadhila)
* [Dimdimadi](https://github.com/dimdimadi)


## Model description:

### Data Cleaning

* Lowering case :  We decide to reduce the noise by normalizing each word to be lowercase
*	Punctuation removing : We removed punctuation such as question marks, commas, colons and periods.
* url removing (tweet data) : All instances of real URLs were removed to reduce the noise of the data.
*	Mention removing (tweet Data) : Tweet content data consisted some metion to other user. These user mentions which would be of little value to the model, and thus all such mentions were removed.

### Preprocessing Data : Sequence Padding 


  Padding is a special form of masking were the masked steps are at the start or at the beginning of a sequence. Padding comes from the need to encode sequence data into contiguous batches: in order to make all sequences in a batch fit a given standard length, it is necessary to pad or truncate some sequences.
When processing sequence data, it is very common for individual samples to have different lengths.A requirement for our LSTM models was that the input sentence length has to be ﬁxed for all training dataset. We use sequence_pads () function from keras with maxlen= input_length which is 100. 


### Embedding (embedding layer) word2vec:

  We trained our own word embeddings during the execution of the whole model, with a randomly initialized embedding layer.

### Model Architecture:

We used two different deep recurrent network architectures, they are :

•	Bidirectional LSTM 
The model are inspired by the paper Bidirectional Recurrent Models for Offensive Tweet Classiﬁcation
We build model which are contains layers:
-	1 Embedding layer responsible for the word embedding
-	1 spatialDropout1D layer Decreasing the number of features that we train on
-	Bidirectional LSTM layer A variant of the LSTM That uses two LSTMs one forward and one backward.
-	2 dense layer 
-	1 dropout layer which located between the dense layer 
-	Last dense layer with softmax
The details architecture of the model bi-directional (picture)

![Alt text](https://github.com/Nadhila/Explainble-AI/blob/master/bi-LSTMmodel.png "Bi-LSTM Model")


•	Model 2 bi gru +LSTM +cnn
We build model which are contains layers:
-	1 Embedding layer responsible for the word embedding
-	1 spatialDropout1D layer Decreasing the number of features that we train on
-	Bidirectional GRU layer A variant of the LSTM That uses two LSTMs one forward and one backward.
-	1D Convolutional layer
-	1 Global average polling 1D layer and 1 global max polling 1D layer  (this two layer are concatenate to be one layer) 
-	2 dense layer 
-	1 dropout layer which located between the dense layer
-	Last dense layer with softmax

The details architecture of the model Bi-GRU+LSTM+CNN (picture)


![Alt text](https://github.com/Nadhila/Explainble-AI/blob/master/bi-GRULSTMCNN.png "Bi-GRU+LSTM+CNN Model")


