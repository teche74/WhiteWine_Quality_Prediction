![download](https://user-images.githubusercontent.com/129526047/236655142-44456ce9-8d88-4e5f-8a08-d55d38953ba0.png)


# WHITE WINE QUALITY PREDICTION

White wine is a beloved beverage that has gained popularity all over the world. One of the most sought-after white wines is the Portuguese "Vinho Verde," which has gained a reputation as a unique and highly valued wine in the wine industry. This type of wine is part of one of the largest and oldest wine regions in the world, known for its natural characteristics that make it stand out from the rest. The Vinho Verde region is located in the northwest of Portugal, where the dense green foliage of the area contributes to the distinct flavors of the wine. In this article, we will delve into the history, characteristics, and production of this exceptional white wine.

# Dataset, Features and Target Variable

The dataset available at the UCI machine learning repository ( https://archive.ics.uci.edu/ml/datasets/wine+quality ) contains 4898 entries (rows) with 12 columns. 
Dataset consisting solely of physicochemical properties of white wines. 

Features of the dataset :

< > Fixed acidity refers to the non-volatile acids present in the wine.

< > Volatile acidity measures the amount of acetic acid present. 

< > Citric acid adds freshness and flavor to wines in small quantities, while residual sugar refers to the amount of sugar left in the wine after fermentation stops. 

< > Chlorides measure the amount of salt in the wine, while free and total sulfur dioxide indicate the amount of sulfur dioxide gas present. 

< > Density is the density of the wine. 

< > pH measures the acidity or basicity of the wine. 

< > Sulphates are a wine additive that contributes to sulfur dioxide gas levels, and alcohol refers to the percentage of alcohol in the wine. 

NOTE -> In this dataset, quality is the target variable.

## MISSING VALUES

The dataset comprising 4898 entries of white wine does not contain any missing values. This implies that all the values for the different features in the dataset were recorded, making it possible to carry out accurate and reliable analyses. However, it is crucial to perform a comprehensive check for missing values in a dataset as they could affect the accuracy and reliability of the results obtained from the analysis.


## DUPLICATED VALUES

It was observed that the white wine dataset contained 937 duplicated values. To handle this, the duplicates were dropped, and only the first instance of each duplicated value was retained. This helps to ensure that the dataset contains only unique values, which is essential for accurate and reliable analysis. It is crucial to identify and handle duplicated values appropriately, as they could significantly affect the outcome of any analysis carried out on the dataset.

## TARGET VARIABLE

According to the information available on the UCI machine learning repository, the target variable for the white wine dataset is quality, which is based on sensory data ranging from 0 (very bad) to 10 (very excellent). However, upon analyzing the dataset, it was observed that the quality attribute had a data distribution ranging from 3 to 9. This implies that the problem of predicting the quality of white wine can be considered as a classification problem, rather than a regression problem as initially expected. In a classification problem, the aim is to predict the class or category of the target variable based on the input features, while in regression, the aim is to predict the continuous value of the target variable based on the input features.



![download](https://user-images.githubusercontent.com/129526047/236655523-14659a4b-4b66-4ce1-98bc-8645ecc43237.png)




![download](https://user-images.githubusercontent.com/129526047/236655534-a525bdb1-f18e-4cbd-956e-34291f5ffb00.png)

After realizing that the quality attribute of the white wine dataset had a data distribution ranging from 3 to 9, the number of instances for each recorded value was counted. The results were arranged in descending order, indicating that there were 1788 instances of white wine with a quality rating of 6, followed by 1175 instances with a quality rating of 5, 689 instances with a quality rating of 7, 153 instances with a quality rating of 4, and 131, 20, and 5 instances with quality ratings of 8, 3, and 9 respectively. This information can provide useful insights into the dataset and can be used to guide the selection of appropriate machine learning algorithms and evaluation metrics for modeling the quality of white wine.



![download](https://user-images.githubusercontent.com/129526047/236655552-225fe2cc-2201-4e9e-803b-f87d587f06f3.png)

After realizing that the original target variable had a data distribution ranging from 3 to 9, a new binary target variable was created for the white wine dataset to classify wines as either low quality or high quality. Wines with a quality value greater than the mean value of the quality feature were classified as high quality, while wines with quality values less than the mean value were classified as low quality.

Upon creating the new target variable, it was observed that the number of wines classified as high quality was greater than the number of wines classified as low quality. This indicates that the dataset is imbalanced, as the number of instances in one class is significantly greater than the other class. Imbalanced classification problems pose unique challenges for machine learning algorithms, as they tend to be biased towards the majority class. Therefore, appropriate strategies such as resampling techniques, class weighting, or using specialized algorithms for imbalanced datasets may need to be employed to address this issue and ensure that the model can accurately classify both low and high-quality wines.



![download](https://user-images.githubusercontent.com/129526047/236655578-87528a62-0dd9-4d57-a44c-acbf679933e3.png)




## EDA ( EXPLORATORY DATA ANALYSIS )

A total of 1018 outliers were detected in the white wine dataset, with citric acid having the highest number of outliers (223) and chlorides coming in second with 178 outliers. Interestingly, no outliers were found in the alcohol data feature.

For a detailed summary of the outliers, please refer to the outlier_info.csv file located in the csv_tables directory of this repository. In addition, a distribution plot and box plot for alcohol have been provided below. Further plots for other data features can be found in the White Wine Quality EDA and Data Preprocessing notebook as well as in the figures directory of this repository.


![download](https://user-images.githubusercontent.com/129526047/236655623-36e9f88a-76ee-4348-a8cd-6ad30646a05a.png)



![download](https://user-images.githubusercontent.com/129526047/236655629-173dfc65-1e2d-4608-8cf4-cbbb3d03b9c4.png)



![download](https://user-images.githubusercontent.com/129526047/236655639-52e2bf96-0266-46ca-b66a-e2df1fd08e7b.png)


## CORRELATION OF FEATURES

Although the physicochemical features in the dataset don't have a strong correlation with the output feature, there are some significant correlations between certain physicochemical features. For instance, residual sugar is highly correlated (0.82) with density, while total sulfur dioxide has a moderate correlation (0.62) with free sulfur dioxide, density has a moderate correlation (0.54) with total sulfur dioxide, and alcohol has a strong negative correlation (-0.76) with density. You can refer to the correlation matrix below for a visual summary of the feature correlations.



![download](https://user-images.githubusercontent.com/129526047/236655679-0e1037d9-da19-417c-8a85-29a61ef9f7c7.png)


## DESCRIPTIVE FEATURE STATISTICS

During the analysis of the white wine dataset, interesting insights were observed about the dataset features.

< > The mean value of fixed acidity in high quality white wines was found to be 6.779, while it was 6.957 for low quality white wines.

< > The mean value of residual sugar in high quality white wines was found to be 5.532, while it was 6.656 for low quality white wines.

< > The mean value of density in high quality white wines was found to be 0.993, while it was 0.995 for low quality white wines.

< > The mean value of alcohol in high quality white wines was found to be 10.940, while it was 9.909 for low quality white wines.

### BARPLOT FOR VARIOUS FEATURES


![download](https://user-images.githubusercontent.com/129526047/236655762-e3400ffc-eff1-44b3-af70-424ddd601d83.png)


### KDE PLOT OF pH


![download](https://user-images.githubusercontent.com/129526047/236655786-3639c90d-8be5-46c7-a7d9-3f05bb8e96da.png)



## DATA PREPROCESSING

The decision was made to drop the quality feature from the dataset and replace it with a new target variable.

## COVERTING TO FEATURE MATRIX

The quality feature was removed from the dataset, resulting in the feature matrix consisting of the 11 physicochemical properties of the dataset and the newly created target feature as the target label.


## BALANCING DATSET

To balance the imbalanced dataset, an undersampling technique was used which involves randomly removing samples from the majority class to match the number of samples in the minority class. The Random Under Sampling (RUS) technique was used to create a balanced dataset for training the machine learning algorithms.

## TRAIN AND TEST SPLIT

Once the dataset was upsampled, it was split into training and testing sets to evaluate the performance of the machine learning models. The dataset was split into a 70:30 ratio, where 70% of the data was used for training and 30% for testing.


## STANDARDIZATION OF DATA

The data was normalized using the scale() function in R, which standardizes the range of data values to have a mean of 0 and a standard deviation of 1. This helps machine learning algorithms achieve better results.


## MODELLING

 6 different machine learning algorithms were selected for the task including 1 tree algorithm (Decision Tree) and 5 ensembles (Random Forest, AdaBoost, ExtraTree, GradientBoosting, and XGBOOST) to determine the best performing algorithm for this classification task. All the models were trained using the default parameters of the algorithms and a random state value of 81.
 
 

![download](https://user-images.githubusercontent.com/129526047/236658660-6e31d418-1136-4bdc-a83f-357359af5a66.png)


## FEATURE IMPORTANCE

performs L1-penalized logistic regression on the Wine Quality dataset. It first converts the response variable "quality" to a numeric variable, and creates the design matrix for the predictor variables.

The "cv.glmnet" function is then used to perform cross-validated Lasso regression and select the optimal value of lambda. The function plots the cross-validated deviance vs. log(lambda) to help with selecting lambda.

Next, the L1-penalized logistic regression model is fit using the optimal lambda value, and the important features are extracted using the "coef" function. The intercept is excluded from the coefficient list, and the magnitude of the coefficients are plotted.


![download](https://user-images.githubusercontent.com/129526047/236659641-83ac339d-290c-45dd-8117-1683fc3b18bd.png)



![download](https://user-images.githubusercontent.com/129526047/236659644-f9bc795d-c04a-45cd-813c-9e31f918e0e2.png)


## EVALUTAION

After fitting the algorithms on the top six features, it was observed that only two models (K-nearest and random forest ) fit well on the dataset, while two models (Decision Tree, SVM) overfitted the data.


The Random Forest model had:

An Accuracy Score of 0.7759
A Precision Score of 0.7825
A Recall Score of 0.7689
An F1-Score of 0.7757


## CONCLUSION

This experiment aimed to predict the quality of vinho verde white wine using analytical tests. The dataset used had 4898 entries, consisting of white wine samples from the northwest region of Portugal. The goal was to classify the wines into low quality (0) or high quality (1) using six different machine learning classification algorithms.

This experiment showcased an approach to deal with imbalanced classes in the dataset and identified the physicochemical properties of white wines that highly correlate with each other. It was also shown that the mean and standard deviation statistics of the physicochemical properties could be considered for predicting the quality of white wines.

Additionally, the features that were considered important for predicting the quality of vinho verde white wines were identified based on the classifiers that were chosen for the task. This experiment provides valuable insights for the wine industry and can help improve the quality of white wine production.


# REFRENCES
[1] P. Cortez, A. Cerdeira, F. Almeida, T. Matos and J. Reis. Modeling wine preferences by data mining from physicochemical properties. In Decision Support Systems, Elsevier, 47(4):547-553, 2009.

[2] Dua, D. and Graff, C. (2019). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.
