# OBJECTIVE
Predicting the age of abalone from physical measurements. 
The age of abalone is determined by cutting the shell through the cone, staining it, and counting the number of rings through a microscope is a boring and time-consuming task. Other measurements, which are easier to obtain, are used to predict the age. Further information, such as weather patterns and location (hence food availability) may be required to solve the problem.

# SUMMARY
This Abalone data set contains measurement of physical characteristics of different abalones. There are total 9 attributes used in the dataset. These are: sex, length, diameter, height, whole weight, shucked weight, viscera weight, shell weight and rings. We use some classifiers like: Decision Tree, Support Vector Machine and Naïve Bayes. For each method, cross validation methods were used. We have used grid search in hyper parameter tuning and get the best performance of each model based on their accuracy. 
	The variable description is produced here:
* Name / Data Type / Measurement Unit / Description
* Sex / nominal / -- / M, F, and I (infant)
* Length / continuous / mm / Longest shell measurement
* Diameter / continuous / mm / perpendicular to length
* Height / continuous / mm / with meat in shell
* Whole weight / continuous / grams / whole abalone
* Shucked weight / continuous / grams / weight of meat
* Viscera weight / continuous / grams / gut weight (after bleeding)
* Shell weight / continuous / grams / after being dried
* Rings / integer / -- / +1.5 gives the age in years

# DATASET DESCRIPTION    
The abalone dataset is a dataset that contains measurements of physical characteristics of different abalones. The physical characteristics along with the unit of its measurement in brackets are:

# INDEX	ATTRIBUTE UNIT DESCRIPTION
1	Sex	-	It can be either one of Male, Female or Indeterminate (Infant). Abalone gender is not determined at birth but rather when they mature 
2	Length	mm	Longest shell measurement
3	Diameter	mm	Perpendicular to length
4	Height	mm	Height of abalone with meat in shell
5	Whole weight	grams	Weight of the whole abalone
6	Shucked weight	Grams	Weight of just the meat
7	Viscera weight	Grams	Gut weight (after bleeding)
8	Shell weight	grams	Weight of shell after being dried
9	Rings	-	This is the dependent variable (label). Number of rings + 1.5 gives age

# ALGORITHMS

## Naive Bayes Algorithm 
Naive Bayes classifier is a supervised machine learning algorithm that uses the Bayes Theorem, which assumes that features are statistically independent. The theorem relies on the naive assumption that input variables are independent of each other, i.e. there is no way to anything about other variables when given an additional variable. Regardless of this assumption, it has proven itself to be a classifier with good results.

#### Mathematical Equation:
Bayes Theorem provides a way of calculating posterior probability P(c|x) from P(c), P(x), and P(x|c). Consider the following equation:
Here,
*	P(c|x): posterior probability of class (c,target) givenpredictor(x,attributes).This represents the probability of c being true, provided x is true.
*	P(c): is the prior probability of class. This is the observed probability of class out of all the observations.
*	P(x|c): is the likelihood which is the probability of predictor givenclass. This represents the probability of x being true, provided x is true.
*	P(x): is the prior probability of predictor. This is the observed probability of predictor out of all the observations.

## Decision Tree
Decision Tree algorithm belongs to the family of supervised learning algorithms. Unlike other supervised learning algorithms, the decision tree algorithm can be used for solving regression and classification problems too.
The goal of using a Decision Tree is to create a training model that can use to predict the class or value of the target variable by learning simple decision rules inferred from prior data (training data).In Decision Trees, for predicting a class label for a record we start from the root of the tree. We compare the values of the root attribute with the record’s attribute. On the basis of comparison, we follow the branch corresponding to that value and jump to the next node.

#### Mathematical Equation:
Node impurity / Impurity Criterion
Both Scikit-learn and Spark provide information in their documentation on the formulas used for impurity criterion. For classification, they both use Gini impurity by default but offer Entropy as an alternative. For regression, both calculate variance reduction using Mean Square Error. Additionally, variance reduction can be calculated with Mean Absolute Error in Scikit-learn.

Information Gain
Another term worth noting is “Information Gain” which is used with splitting the data using entropy. It is calculated as the decrease in entropy after the dataset is split on an attribute:
Gain(T,X) = Entropy(T) — Entropy(T,X)
•	T = target variable
•	X = Feature to be split on
•	Entropy(T,X) = The entropy calculated after the data is split on feature X
 
## Support Vector Machine
The objective of the support vector machine algorithm is to find a hyperplane in an N-dimensional space (N — the number of features) that distinctly classifies the data points.
To separate the two classes of data points, there are many possible hyperplanes that could be chosen. Our objective is to find a plane that has the maximum margin, i.e the maximum distance between data points of both classes. Maximizing the margin distance provides some reinforcement so that future data.
Hyperplanes are decision boundaries that help classify the data points. Data points falling on either side of the hyperplane can be attributed to different classes. Also, the dimension of the hyperplane depends upon the number of features. If the number of input features is 2, then the hyperplane is just a line. If the number of input features is 3, then the hyperplane becomes a two-dimensional plane. It becomes difficult to imagine when the number of features exceeds 3.
Support vectors are data points that are closer to the hyperplane and influence the position and orientation of the hyperplane. Using these support vectors, we maximize the margin of the classifier. Deleting the support vectors will change the position of the hyperplane. These are the points that help us build our SVM.
 
#### Mathematical Equation:
Length of a vector
The length of a vector x is called its norm, which is written as ||x||. The Euclidean norm formula to calculate the norm of a vector x = (x1,x2,...,xnx1,x2,...,xn) is:
||x||=x21+x22+...+x2n−−−−−−−−−−−−−√
Direction of a vector
The direction of a vector x = (x1,x2x1,x2) is written as w, and is defined as:
w=(x1||x||,x2||x||)w=(x1||x||,x2||x||)
If we look at figure 1, we can see that cos(θ)=x1∥x∥cos(θ)=x1‖x‖ and cos(α)=x2∥x∥cos(α)=x2‖x‖. Thus, the direction vector w can also be written as:
w=(cos(θ),cos(α))
It is worth noting that the norm of a direction vector is always equal to 1. Because of this, the direction vector w is also called the unit vector.
