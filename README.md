# Fake-ATM-Transaction-predictor
## Packages used 
1-Numpy-> The full name of tf this ppackage is numerical python.This package allows working eith arrays and fast execution of all the operations related to matrices like addition,subtraction,transpose etc.
The basic data structure in which all the values on which calculations are performed is numoy.array

2-Matplotlib-> This package is used for data visualization which is an important part of every machine learning model.
Plots like bar graphs,scatter plot,histogram are created using this package.

3- Pandas-> This Package is used for loading data in the form of DataFrame or Series from any type of file.
Operations like data cleaning,data preprocessingare done with the help of pandas package.

##Dataset Description
This dataset was taken from kaggle.com website.
The dataset contains the credit card details of a person and its records.
This dataset has 284808 rows with 31 attributes.
Due to security purpose the main feature names are removed and replaced with V1 to V28
The dataset has no null values and is cleaned.
Because of so large data, The clustering has been performed first so that more insights can be observed.

## Clustering Of Data

### KMEANS CLUSTERING
In this Clustering n number of points are considered in a plane.
Those points which lies near to a point are placed in one cluster.
In this Case the number of clusters taken is 2.
The reason is that data is divided in 2 cateogaries whether transaction is true or false.
The clustering is multi leveled i.e  the division is done by using more than one attributes.

#### Verification by elbow graph
In this plot we plot sum of square of error for each number of clusters.
SSE is calculated by total of distance between a considered point with all other points in cluster and tehn adding this result of each cluster together i.e

SSE(nth cluster)=SSE(1)+SSE(2)+......SSE(n)

The graph looks like hand .The point where elbow like shape is generated is the ideal value of k.
In this case the ideal value of number of custers was 2.
Now we will apply Model on the dataset.

## Machine Learning
In This Case the output will be in the form of whether transaction is True or False. So Classification takes place since output is categorical.
Following are the Main steps-:

1- Determining Dependent and Independent variables.
The main aim of this model is to determine whether the transaction is origional or not.
So the KMeans column generated by clustering is dependent variable and columns from "Time" to "V28" are independent variables.

2- Splitting Data into test and train Data
Test data is the data on which model is applied and results are calculated.
Train data is the data by which the model is generated.
In this project,The size of test data is 25% data of the dataset and size of train data is 75% of the dataset.

3-Feature Scaling Of the data
Feature Scaling means that that the feature values are converted to standard values depending upon which scaling algorithm is applied.
In this Case, Standard Scaler is applied where the standard value is the normalized value i.e value given by normal dstribution.

4-Applying Suitable Machine Learning Algorithms on train data and predicting output on test data.
There are 3 Supervised Learning  Algorithms applied in this dataset

### SVC Classifier
*It is abbreviated as Support Vector Classifier.
*The Idea Of SVM is to Draw a hyperplane which divides the values into two cateogaries.
*Here the plane is drawn at centroid of the distance between two types of values.
*The distance between the point and hyperplane is called margin.
*Other terminologies are regularization and kernel.
*kernel defines the type of algorithm used for calculating the distance between point and plane.
* This Algorithm gave an accuracy of 99.54916996713575% on test data.

### Naive Bayes Classifier
*It is furthur divded into 3  types i.e Gaussian,Multinomial and Bernouli.
*Since it is classification problem so here Gaussian is used.
*This algorithm works on the concept of conditional probability and Bayes Theorm.
*Here The conditional probability for both the conditions are calculated and the possibility which has higher probability is considered as output.
* The Basic Formula is P(A/B)=(P(B/A)*P(A))/P(B) where P(A/B) is called posterior probability, P(A) is called prior probability,P(B/A) is called likelihood probability.
* After training model using Naive Bayes Algorithm and applying it on test data the accuracy of final result was 98.1517373107497%

### Logistic Regression
