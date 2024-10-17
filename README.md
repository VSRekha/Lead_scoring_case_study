# Lead_scoring_case_study
Building a logistic regression model to assign a lead score between 0 and 100 to each of the leads which can be used by the company to target potential leads. 
A higher score would mean that the lead is hot, i.e. is most likely to convert whereas a lower score would mean that the lead is cold and will mostly not get converted.

Steps followed:

1)	Data Understanding & exploration
   
    o	Reading the data and exploring the variables to understand what they indicate
  	
  	o Reviewing the rows and column to check for duplicates, null values etc
  	
  	o	Understanding the datatypes of the columnn 

2)	Data cleaning
   
    o Dropping the column not useful for analysis
  	
  	o Treating the missing values - drop / substituting with mean or median/ impute with 'Others' or 'Not specified' etc wherever the data is not available, but cannot be imputed with other entries
  	
    o	Outlier treatment - consider the difference between quantiles selected and min/max value for capping

3)	Exploratory Data Analysis
   
    o	Analysing both categorical and numerical variables to identify the critical variables impacting lead conversion and dropping other variables which will not add value to the model
  	
    o	Building correlation matrix to check for correlation between variables and multicollinearity

4)	Data Preparation
    o	Conversion of few categorical variables with Yes/No as responses into 1s and 0s
  	
    o	Creation of dummy variables for categorical columns, concatenation with original dataset and dropping original columns after dummy variable creation
  	
    o	Splitting the data into train and test dataset
  	
  	o Scaling numerical columns through standard scaler
  	
    o	Checking conversion rate (target variable here) for class balance/imbalance to decide on any special treatment for the dataset.

5)	Model building
	
    o	Generalized Linear Model (GLM) from Stats models library is used to build logistics regression model
  	
    o	Considering a large number of variables in the dataset and insignificance of many towards building the model, initial feature selection of 15 variables were made through RFE
  	
    o	From the top 15 features, final variable selection was made manually by running iterations to eliminate features considering p-values and VIF
  
6)	Model Evaluation
   
    o Selecting an arbitrary cut-off probability point of 0.5 to find the predicted labels
  	
    o	Model evalaution using evaluation metrics for arbitrary cut off
   
7)	Drawing ROC curve
   
    o	The ROC curve is used to evaluate the performance of the model built. It shows the trade-off between true positive rate (TPR) and false positive rate (FPR) across different classification thresholds.
  	
    o	Finding the area under the curve of the ROC to know the performance of the model

8)	Finding optimal cut off point
   
    o	Arrival of the optimal cutoff probability
  	
    o	Model evaluation using evalaution metrics with optimal probabiity cut off

9)	Prediction on test data
    
    o	Making prediction on test dataset with optimal cut off probability & evaluating the model performance through evaluation metrics
  	
    o	Determining the lead score and checking final prediction’s conversion rate

    Relative Feature importance
  	
    Visualizing the sorted select variables showing the positive / negative impact on the conversion probability 


