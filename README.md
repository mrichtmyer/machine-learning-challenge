# Classify Potential Plannets
![cover_photo](exoplanets.jpg)

## Matthew Richtmyer | May 04 2020

--- 

## Data:
* 40 measurements taken from Hubble Telescope for ~7k potential planets. This data is labeled with a true value (e.g. false postive, confirmed and candidate plannets). 

## Preprocessing:
* The Standard Scaler function was used to scale our data. 
* It seems like 40 features may be too many measurements for 7k total measurements. We will perform a PCA to identify if we can reduce dimensionality in our dataset, which will help at runtime, but potentially also help improve model accuracy by removing noisy data. 

## Models Explored
* [PCA](https://github.com/mrichtmyer/machine-learning-challenge/blob/master/PCA.ipynb): 
  * Data was cast down from 40 dimensions onto 2 dimensions. These two eigenvectors explain ~97% of the variance within the dataset. 

* [SVM](https://github.com/mrichtmyer/machine-learning-challenge/blob/master/SVM.ipynb):
  * Hyperparameters tuned using Grid Search
  * Repeated with 2 dimension data calculated with PCA

* [KNN](https://github.com/mrichtmyer/machine-learning-challenge/blob/master/KNN.ipynb):
  * The optimal number of clusters was initially calculated on our training set, and then predictions/scoring were then calculated. 
 
* These models were exported using the pickle library to .sav files. This saves the model weights so that training does not need be be done at run time. This allows the model to be deployed in a production setting (e.g. app, server)
  
## Results
* The SVM Model shows the highest score, at ~88% accurate. 
