# Review 3 Different Methods for Explainability Artificial Intelligence (XAI)

In this repository, we use 3 different methods of XAI on Machine Learning Model for Text Classification (Sentiment classification using Bi-LSTM). 

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
