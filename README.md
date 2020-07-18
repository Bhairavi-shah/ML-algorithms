ML-algorithms
=============
Most important machine learning algorithms in detail for easy reference

## 1. Linear Regression
https://www.kaggle.com/bhairavishah/housing-data-linear-regression

It is used to predict some y values based on the value of another set of X values

- used for regression
- created in 1800s by Francis Galton
- Galton was investigating the relationship between the heights of fathers and the heights of their sons.
- he said “A father’s son’s height tends to regress (or drift towards) the mean (average) height”

### Mathematics of Linear Regression
- While creating a regression model, all that we are trying to do is draw a line that is as close as possible to each point in a dataset
- The typical example of this is the “least squares method” of linear regression, which only calculates the closeness of a line to the x values in the up-and-down (vertical offsets) direction.

## 2. Logistic Regression
https://www.kaggle.com/bhairavishah/titanic-logistic-regression

It is similar to linear regression except that instead of calculating a numerical y value, it estimates which category a data point belongs to

- used to solve binary classification problems
- eg: 
  - spam emails (spam or not spam?)
  - car insurance claims (write-off or repair?)
  - disease diagnosis (positive or negative?)
- Binary classification: we assign categories as 0 or 1
- Linear regression cannot be used for classification (straight line) whereas logistic regression bends the line for best fit

### Sigmoid Function
- Linear regression - calculated using linear function
- Logistic regression models are built using the Sigmoid Function (aka Logistic Function because of its used in logistic regression)
- f(x) = 1 / (1+e<sup>-(x)</sup>)
- it will always return a value between 0 and 1
- The model will have a cut-off usually 0.5, if the sigmoid value is below 0.5 it is said to be one category otherwise another category

### Confusion Matrix
- tool to compare true positives, true negatives, false positives and false negatives in machine learning

## 3. K-Nearest Neighbors
https://www.kaggle.com/bhairavishah/knn-classifieddata

Can be used in cases where there are more than two categories in classification

- The K- nearest neighbors algorithm identifies "K" data points closest to the new observation
- The majority of the "K" closest points class in given to the new observation
- Algorithm:
    1. Store all of the data
    2. Calculate Euclidean distance (or any other distance metric) from the new data point x to all other points in the data set
    3. Sort the points in the data set in order of increasing distance from x
    4. Predict using the same category as the major of the K closest data points to x
- having very low K value => perfectly predict training data and poorly predict test data
- having too high K value => unnecessary complex model

## 4. Decision Trees & Random Forests
https://www.kaggle.com/bhairavishah/decisiontrees-randomforests-kyphosispatients

Examples of tree methods.

Decision trees => ML models used to make predictions by cycling through every feature in a data-set, one-by-one

Random forests => Ensembles(group) of decision trees that used random orders of the features in the data sets

### Tree Methods
#### Decision Tree
Every decision tree has two types pf elements:
    1. Nodes: locations where the tree splits according to the value of some attribute
    2. Edges: the outcome of a split to the nect node

Root => the node that performs the first split
Leaves => terminal nodes that predict the final outcome

##### Building Decision trees
Deciding which features to split your data on is a mathematically complex problem (Entropy and Information Gain)

#### Random forests
Random forests => Decision trees using a random sample of features chosen as the split (A new random sample of features is chosen for every single tree at every single split)

- We want to avoid taking the average of highly correlated variables which might significantly reduce variance.
- By randomly selecting features for each tree in a random forest, the trees become decorrelated and the variance of the resulting model is reduced. 
- This decorrelation is the main advantage of using random forests over handmade decision trees

## 5. Support Vector Machines (SVM)
Classification algorithms (technically could be used to solve regression problems) that divide a data set into categories by slicing through the widest gap between categories.

- ML models with associated learning algorithms that analyze data and recognize patterns
- Can be used for both classification and regression problems
- Uses geometry to make categorical predictions
- Maps the data points as points in space and divides the separate categories (shattering) so that they are divided by an open gap that is as wide as possible
- The line dividing is called a "hyperplane"
- "Optimal hyperplane" as the one that maximizes the margin between the closest data points from each category
- The data points which touch the margin are called support vectors

## 6. K-means Clustering
ML algorithm that allows you to identify segments of similar data within a data set

- Unsupervised machine learning algorithm
- Takes unlabelled data and will attempt to group similar clusters of observations together within your data
- Highly useful for real world problems:
  - customer segmentation for marketing teams
  - document classification
  - delivery route optimization
  - professional sport analytics
  - predicting and preventing cybercrime
- primary goal of a K means clustering algorithm is to divide a data set into distinct groups such that the observations within each group are similar to each other
- Algorithm:
    1. Select number of clusters - K (important choice)
    2. Randomly assign each point in your data set to a random cluster (initial assignment)
    3. Iterate until clusters stop changing:
       1. Compute each cluster's centroid by taking the mean vectr of each points within that cluster
       2. Re-assign each data point to the cluster that has the closest centroid
- Choosing proper K value:
  - Elbow method: 
    - Compute sum of squared errors (SSE) for your K-means clustering algorithm for a group of K values. 
    - SSE (in K-means algorithm) = sum of the squared distance between each data point in a cluster and that cluster's centroid
    - Plot SSE against different K values (2, 4, 6, 8, 10) - error decreases as K value increases
    - Choose the K value at which SSE slows its rate of decline abruptly (This is not the "best", just a good value)

## 7. Principal Component Analysis (PCA)
Used to transform a many-featured data set into a transformed data set with fewer features where each new feature is a linear combination of preexisting features. The transformed data set aims to explain most of the variance of the original data set with far more simplicity

- aka. Factor Analysis
- ML technique that is used to examine the interrelations between sets of variables
- Linear regression determines a line best fit through a dataset
- PCA determines several orthogonal lines of best fit for the data set
