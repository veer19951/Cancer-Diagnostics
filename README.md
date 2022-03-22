# Cancer-Diagnostics

Dataset Link-https://www.kaggle.com/c/msk-redefining-cancer-treatment/
Download training_variants.zip and training_text.zip from Kaggle.

**1-Problem Statement-**
  - Classify the given genetic variations/mutations based on evidence from text-based clinical literature. 
  
**2-Understanding the data**
  - We have two data files: one conatins the information about the genetic mutations and the other contains the clinical evidence (text) that  human experts/pathologists     use to classify the genetic mutations. 
  - Both these data files are have a common column called ID
    - training_variants (ID , Gene, Variations, Class)
    - training_text (ID, Text) 
  
**3-Understanding the problem**
  - The workflow is as follows
    - A molecular pathologist selects a list of genetic variations of interest that he/she want to analyze
    - The molecular pathologist searches for evidence in the medical literature that somehow are relevant to the genetic variations of interest
    - Finally this molecular pathologist spends a huge amount of time analyzing the evidence related to each of the variations to classify them
  
  Our goal here is to replace step 3 by a machine learning model. The molecular pathologist will still have to decide which variations are of interest, and also collect   the relevant evidence for them. But the last step, which is also the most time consuming, will be fully automated.
  Source Kaggle(https://www.kaggle.com/c/msk-redefining-cancer-treatment/discussion/35336#198462)
  
  My understanding about the problem is as follows-
  - every gene undergoes mutation this is the main reason why we have variation in human beings eg difference in heights, hair colour, eye colour etc
  - There are many factors due to which gene undergoes mutation 
  - Note mutation in gene is not always bad but some mutation can be dangerous leading to cancer 
  - Now in the dataset we are given a gene now this can have many mutation some of which are non dangerous leading to variation in human beings and some are dangerous     leading to cancer
  - Now the challenge here is given a gene and a variation using the text we need to find out whether it belongs to one of the 9 classes ie whether that                   varaition/mutation in the given gene is a dangerous or a normal

**4-Business Objetive and constraints**
  - No strict low latency requirments
  - Interpretability is important 
  - Making errors can be costly 
  - Probability of data point belongig to each class is needed 
  
**5-ML problem formulation**
    - There are nine different classes a genetic mutation can be classified into => Multi class classification problem
    - Objective: Predict the probability of each data-point belonging to each of the nine classes
    - Performance metric Multiclass log loss source(https://www.kaggle.com/c/msk-redefining-cancer-treatment#evaluation)
    - Confusion matrix to undestand the performance of model 
    -  Split the dataset randomly into three parts train, cross validation and test with 64%,16%, 20% of data respectively
