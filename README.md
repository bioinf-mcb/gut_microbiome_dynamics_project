# Dynamics of interactions within the human gut microbiome using machine learning algorithms
this repo contains data and code produced during development of project 'Dynamics of interactions within the human gut microbiome using machine learning algorithms'

## Abstract

  The human gut microbiome is a dynamic milieu due to its interactions with the host, the environment, and each other. However, most of the research on the gut microbiome uses cross-sectional data (one sample per subject), limiting our understanding of microbiome dynamics which is crucial to better understand the causality between bacteria. 


  This project looks to build a machine learning-based model that will accurately fit and predict bacteria dynamics over time. We aim to better understand how bacteria interact with each other in time and how to model such data using machine learning. To test its practical value, we will use our model on the gut microbiome data of Inflammatory Bowel Disease (IBD) patients. 


  We hypothesize that bacteria-bacteria interactions may be derived from time-series data and that those interactions are stable in time and between subjects. Subsequently, we hypothesize that patterns of interactions between healthy subjects and IBD subjects are different. If the latter hypothesis proves true, this would lay the groundwork for microbiome-oriented therapies of the future.


  The project consists of 4 parts: 
  
  * data preparation 
  * analysis of linear interactions between bacteria
  * analysis of more complex interactions within gut microbiome
  * comparison of interactions between healthy and IBD subjects
  

  ### data preparation 
  We will use cross-sectional and time-series data from healthy and IBD adult subjects and preprocess it using our already developed pipeline that takes
  into account the limitations of microbiome data.

  ### analysis of linear interactions between bacteria
  First, we will analyze interactions between bacteria in the human gut microbiome from healthy individuals using linear models (LMs). LMs assume a   
  linear relationship between the target variable (ex. bacteria A) and regressors (ex. the rest of the gut microbiome in the sample). Our preliminary 
  results and literature indicate that LMs can be efficiently used to model basic dependencies in microbiome data. 
  We believe that an LM with low error correctly captures gut microbiome dynamics, thus, its coefficients can be used to construct a linear interaction
  matrix. 

  ###  analysis of more complex interactions within gut microbiome
  Second, we will analyze more complex interactions in the gut microbiome. Here, we will use neural networks (NNs). NNs will aim to accurately predict
  interactions within the gut microbiome in time. We intend to use and enhance our pre-developed multilayer perceptron and autoencoder-based models.
  We will pre-train our NN on cross-sectional data to train the model on the co-occurrence problem. Next, we will use the pre-trained NN on time-series 
  data and use the linear interaction matrix obtained in step 1 as additional input. Given the results from our NN, we will construct a bacteria-bacteria 
  interaction matrix. 


Steps 1 & 2 will help understand the dynamics of the gut microbiome in healthy subjects and answer questions such as: how do bacteria interact with each other in time?; are those interactions unique within the host?; to what extent is the gut microbiome self-explainable?; what are the main drivers of the gut microbiome community?

  ###  comparison of interactions between healthy and IBD subjects

  Finally, to test the practical value of our model, it will be used on IBD patients' gut microbiome data. Here, we want to understand how bacterial
  interactions differ between healthy and IBD subjects.


Steps 1 & 2 will be performed separately on healthy and IBD patients and for each subject, we will obtain a matrix of gut microbiome interactions. Then, we will use a classifier to separate interaction matrices from healthy and IBD subjects. As an interaction matrix is a graph, we will use graph NNs for this classification task. After training an efficient classifier we will analyze features (i.e. bacteria-bacteria interactions) that are influencing its results. 


To solve the problem of the limited IBD data we will use synthetically augmented (artificially manufactured) data points in the 3rd step. This way, we may determine optimal time-series data collection guidelines for future sample collection. We believe that understanding interactions between bacteria in the gut microbiome will help answer important questions in the future: 

  * which interactions are associated with disease
  * can we manipulate interactions
  * will removing or adding bacteria A affect the gut microbiome and improve patient health? Thus, we consider it a high risk/high reward part of our project.  

