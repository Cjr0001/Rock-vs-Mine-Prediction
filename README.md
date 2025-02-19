# Rock-vs-Mine-Prediction

### PROBLEM STATEMENT 

Consider there is a submarine so there is a war going on between two countries so, the submarine of a country is going in know underwater to another country and the enemy country has planted some mines in the ocean, here mines are nothing but explosives that explodes when some object comes in contact with it right so there can also be rocks in the ocean so the submarine needs to predict whether it is crossing a mine or a rock so our task is to make a system that can predict whether the object beneath the Submarine is a mine or a rock so how this has done is the Submarine since a sonar. This sonar [Sound Navigation and Ranging] sends the sound signals and reviews switchbacks so this signal is then processed to detect whether the object is a mine or it is just a rock in the ocean.

![workflow ROCK vs MINE PREDICTION ](https://github.com/DeepikaA2004/Rock-VS-Mine-prediction-ML-project/assets/110418508/0acdd91d-ce4b-476b-9563-60c1398f0594)


## ALGORITHM :-
  SUPERVISED MACHINE LEARNING [LOGISTIC REGRESSION]

This document is written to provide aid in understanding the project.

Contents of the document - 
1. Understanding the problem statement 
2. Machine learning 
3. Types of machine learning models with examples 
4. Machine learning algorithm used for the model - Logistic Regression
5. NumPy library 
6. Pandas library 
7. Scikit-learn library 
8. Exploratory data analysis 
9. Train-test split 
10. Model evaluation - accuracy 

About the dataset - 

There are 5 rows and 61 columns of data

The 60th column gives us the rock and mine classification label

R - the object is rock 

M - the object is mine

### Machine learning

Machine learning enables the processing of sonar signals and target detection. Machine Learning is a subset of Artificial Intelligence. This involves the development of computer systems that are able to learn by using algorithms and statistical measures to study data and draw results from it. Machine learning is basically an integration of computer systems, statistical mathematics and data.

Machine Learning is further divided into three classes - Supervised learning, Unsupervised learning and Reinforcement Learning. 

Supervised learning is a machine learning method in which models are trained using labelled data. In supervised learning, models need to find the mapping function and find a relationship between the input and output. In this, the user has a somewhat idea of what the output should look like. It is of two types - regression (predicts results with continuous output. For example, given the picture of a person, we have to predict their age on the basis of the given picture) and classification (predict results in a discrete output. For example, given a patient with a tumor, we have to predict whether the tumor is malignant or benign.) 

Unsupervised learning is a method in which patterns are inferred from the unlabelled input data. It allows us to approach problems with little or no idea what the results should look like. We can derive structure from the data where we don’t necessarily know the effect of variables. We can derive the structure by clustering the data based on relationships among the variables in the data. With unsupervised learning there is no feedback on the prediction results. It is of two types - clustering (model groups input data into groups that are somehow similar or related by different variables. For example, clustering data of thousands of genes into groups) and non-clustering (models identifies individual inputs. It helps us find structure in a chaotic environment. For example, the cocktail party problem where we need to identify different speakers from a given audiotape.)

Reinforcement learning is a feedback-based machine learning technique. It is about taking suitable action to maximise reward in a particular situation. For example, a robotic dog learning the movement of his arms or teaching self-driving cars how to depict the best route for travelling. 

For this case, I will use Logistic regression to determine whether the object is a rock or mine. 
Regression models describe the relationship between variables by fitting a line to the observed data. Linear regression models use a straight line and logistic and non-linear regression models use a curved line. Regression allows to estimate how a dependent variable changes as the independent variables change. 

Logistic regression (or sigmoid function or logit function) is a type of regression analysis and is commonly used algorithm for solving binary classification problems. It predicts a binary outcome based on a series of independent variables. The output is a predicted probability, binary value rather than numerical value. If the predicted value is a considerable negative value, it’s considered close to zero. If the predicted value if a significant positive value, it’s considered close to one. The dependent variable generally follows bernoulli distribution. Unlike linear regression model, that uses ordinary least square for parameter estimation, logistic regression uses maximum likelihood estimation, gradient descent and stochastic gradient descent. There can be infinite sets of regression coefficients. The maximum likelihood estimate is that set of regression coefficients for which the probability of getting data we have observed is maximum. To determine the values of parameters, log of likelihood function is taken, since it does not change the properties of the function. The log-likelihood is differentiated and using iterative techniques like newton method, values of parameters that maximise the log-likelihood are determined. A confusion matrix may be used to evaluate the accuracy of the logistic regression algorithm. 

Python libraries used in the project - 

#### NumPy  

It is a python library used for working with arrays. It has functions for working in the domain of linear algebra, fourier transform, and matrices. It is the fundamental package for scientific computing with python. NumPy stands for numerical python. 

NumPy is preferred because it is faster than traditional python lists. It has supporting functions that make working with ndarray very easy. Arrays are frequently used where speed and resources are very important. NumPy arrays are faster because it is stored at one continuous place in memory unlike lists, so processes can access and manipulate them very efficiently. This is locality of reference in computer science. 

#### Pandas  

Pandas is made for working with relational or labelled data both easily and intuitively. It provides various data structures and operations for manipulating numerical data and time series. 

It has a lot of advantages like - 
1. Fast and efficient for manipulating and analyzing data
2. Data from different file objects can be loaded 
3. Easy handling of missing data in data preprocessing 
4. Size mutability 
5. Easy dataset merging and joining 
6. Flexible reshaping and pivoting of datasets 
7. Gives time-series functionality 

Pandas is built on top of NumPy library. That means that a lot of structures of NumPy are used or replicated in Pandas. The data produced by pandas are often used as input for plotting functions of Matplotlib, statistical analysis in SciPy, and machine learning algorithms in Scikit-learn. 

#### Scikit-Learn

It provides efficient tools for machine learning and statistical modeling including classification, regression, clustering and dimensionality reduction. It has numerous machine learning, pre-processing, cross validation, and visualization algorithms. 

### Exploratory data analysis 

‘describe()’ method returns description of data in DataFrame. It tells us the following information for each column - 
- Count - number of non-empty values
- Mean - the average (mean) value  
- Std - standard deviation
- Min - minimum value
- 25% - the 25 percentile 
- 50% - the 50 percentile 
- 75% - the 75 percentile
- Max - maximum value

Unbalanced classes - 

In classification cases, when the data available on one or more classes are extremely low, then it is a unbalanced class. 

This can be a problem because - 
1. We don’t get optimized results for the class which is unbalanced in real time as the algorithm model does not get sufficient insight at the underlying class. 
2. It creates a problem in making validation to test data because it is difficult to have representation across classes in case number of observations for few classes is extremely less. 

Following are some of the ways of handling it - 
1. Undersampling - Here, we randomly delete the class which has sufficient observations so that the comparative ration of two classes is significant in our data. This approach is simple but it can introduce a bias in the data because there is a high possibility that the data we are deleting may contain important information about the predictive class. 
2. Oversampling - For the unbalanced class randomly increase the number of observations which are just copies of existing samples. This ideally gives a sufficient number of samples to work with. However, oversampling may lead to overfitting to the training data. 
3. Synthetic sampling - synthetically manufacture observations of unbalanced classes which are similar to the existing using nearest neighbour classification. The problem comes when the number of observations are of extremely rare class. 


### Train-test split

The entire dataset is split into training dataset and testing dataset. Usually, 80-20 or 70-30 split is done. The train-test split is used to prevent the model from overfitting and to estimate the performance of prediction-based algorithms. We need to split the dataset to evaluate how well our machine learning model performs. The train set is used to fit the model, and statistics of training set are known. Test set is for predictions. 

This is done by using scikit-learn library and train_test_split() function. 

Parameters - 
1. *arrays: inputs such as lists, arrays, data frames, or matrices
2. test_size: this is a float value whose value ranges between 0.0 and 1.0. it represents the proportion of our test size. its default value is none.
3. train_size: this is a float value whose value ranges between 0.0 and 1.0. it represents the proportion of our train size. its default value is none.
4. random_state: this parameter is used to control the shuffling applied to the data before applying the split. it acts as a seed.
5. shuffle: This parameter is used to shuffle the data before splitting. Its default value is true.
6. stratify: This parameter is used to split the data in a stratified fashion.

### Model evaluation

Model evaluation is done to test the performance of machine learning model. It is done to determine whether the model is a good fit for the input dataset or not. 

In this case, we use accuracy. Accuracy is a performance metrics that is used to test a binary classification model. Accuracy measures the proportion of correct prediction to total data points.

Accuracy = ( tp + tn) / ( tp + fp + tn + fn )

Tp - true positive. This refers to the total number of observations that belong to the positive class and have been predicted correctly. 
Tn - true negatives. It is total number of observations that belong to the negative class and have been predicted correctly 
Fp - false positives. It total number of observations that have been predicted to belong to positive class, but instead belong to the negative class. 
Fn - false negatives. It is total number of observations that have been predicted to be a part of negative class but instead belong to the positive class. 
