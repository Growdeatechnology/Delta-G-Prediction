# &Delta;G Prediction

This ΔG prediction tool is developed at Growdea Technologies Pvt. Ltd. and is able to predict free energy of unfolding for protein molecules from its sequence with high accuracy. Free energy of unfolding represents the energy required for a protein molecule to denaturate from its native conformation to primary structure and thus helps in determination of protein thermodynamic stability. Thermodynamic stability of protein can be a crucial measure to classify a mutant sequence as pathogenic and benign. 

## Dataset 

This machine learning based tool is trained on a robust dataset with an acceptable distribution of datapoints. The dataset was taken from ProTherm database and curated further to obtain clean and significant data. The frequency distribution of the finalized dataset was calculated and is represented in fig. 1. This dataset was further divided into training, test and validation dataset to train and test the performance of the prepared ML model.

![Screenshot from 2023-08-30 10-29-08](https://github.com/Growdeatechnology/Delta-G-Prediction/assets/72397529/851978c9-09e9-45b2-9dbd-9346248b3800)

Fig. 1: Frequency distribution of curated dataset 

![image](https://github.com/Growdeatechnology/Delta-G-Prediction/assets/72397529/f2472964-518b-424a-a879-327fa1a3b23d)

Fig. 2: Plotting of Uppercase Alpha: &Alpha;G values on length of sequence length

## Encoder and Model 

The ML model takes protein sequence as input to predict ΔG, but before utilization of sequences, it is converted/encoded into a format comprehensible by machine. For encoding of protein sequences One Hot Encoding was performed which converts protein sequence into a matrix of 0s and 1s based on the amino acids. 

A total of three models, Random Forest (RF), Support Vector Regression (SVR) and Convolutional Neural Network (CNN) were used. Threefold validation was performed for each model and their performance was measured as R<sup>2</sup> (coefficient of determination) and MSE (mean squared error). These measured scores are represented in table 1. Based on the measured performance score, the best performing model was selected and used in the final model for ΔG prediction. 

Table 1: Measured performance score for three models. 
![Screenshot 2023-08-30 184647(1)](https://github.com/Growdeatechnology/Delta-G-Prediction/assets/72397529/522f76f6-a946-4767-a6d2-5c46c1b59f18)


The final ML model utilizes protein sequences which is further encoded by One Hot Encoding and using -CNN model predicts ΔG. The developed model can predict ΔG for single sequence as well as for multiple sequences stored in single file.  

The predicted value is reliable as the performance of the model is satisfactory with: 

R<sup>2</sup> = 0.78 and MSE = 3.278. 

The plot between predicted values and actual values are represented in the following figure.

![Screenshot from 2023-09-06 13-15-04](https://github.com/Growdeatechnology/Delta-G-Prediction/assets/72397529/20bfb8c8-f726-48f8-b9e2-104845928fc6)


The model is easy to use as only raw sequence or file with raw sequences is required. The predicted value is in the unit kcal/mol and easy to interpret. 
