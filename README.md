# Data-Mining-Excercise
There 5 different project in this repository that each cover a different section in the datamining world; from preprocessing and analyzing data to classification, clustering, etc.
## Project List
- [Analysing Iris Dataset](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/AnalyseIrisDataset)
- [Classification](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/AssociationRuleExtraction)
- [Clustering](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/Classification)
- [Association Rule Extraction](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/Clustering)
- [Diabetes Detection](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/Diabetes-Detection)
## Project Description
A series of different data mining sub-projects are implemented in this project. This project was implemented to practice using different libraries and to work with different algorithms to gain knowledge and experience in this field of science. The full explanation of each sub-projects is written in the following sections.
### Analysing Iris Dataset
This project aimed at preprocessing the data obtained from the Iris dataset using two major preprocessing libraries in machine learning: [Pandas](https://pandas.pydata.org/docs/), and [scikit-learn](https://scikit-learn.org/stable/). <br>
The Iris dataset contains information on three types of flowers (iris-setosa، iris-versicolor, iris-virginica). The data collected for each of these categories of data contains four columns named: <br>
- sepal length in cm <br>
- sepal width in cm <br>
- petal length in cm <br>
- petal width in cm <br>

For preprocessing purposes, the missing values were deleted from the dataset. Also, the non-numeric (categorical) data was encoded using label encoding. Although label encoding is a very suitable approach to solving this problem, it can only be applied to ordered data. In the case of encoding data with no order, one hot encoding is a feasible method.<br> 
Normalization eas also done on this dataset in order to get better results in training phase. <br>
Visualizing the data before applying any ml algorithm can help understand and analyze data better. Visualizing data with more than three dimensions is not feasible nor easy. To address this problem, PCA was applied to this data to obtain a 2 dimensional dataset for visualizing purposes.<br>
### Classification
The main goal of this project was to practice using and finding the best classification algorithms and functions for each type of data distribution. Different parameters were analyzed during this project, including learning_rate, to obtain the best results and accuracy. <br>
In the last section of this project, the fashion_mnist dataset was imported to test the classification algorithm.
### Clustering
In this project some clustering algorithms were used to cluster data. 
#### 1. K-Means for Random Data
First a set of random data was generated and then clustered using k-means algorithm. The issue with this problem is that we have to set the number of the clusters manually. To overcome this issue I used elbow method and calculated the cost function for 1 to 10 clusters and found the optimal number of clusters.
<br>
<img src="https://github.com/mahvash-siavashpour/mahvash-siavashpour.github.io/blob/main/assets/img/elbow.png?raw=true" alt="img" width="500"/>
<br>

#### 2. K-Means for Digit Dataset
In this section the digit dataset from Sklearn was used. K-means algorithm was applied to this dataset to group them into 10 clusters. Then the centroids were calculated. As it is shown below, the centroids almost accurately represent the labels of their clusters:
<br>
<img src="https://github.com/mahvash-siavashpour/mahvash-siavashpour.github.io/blob/main/assets/img/cluster-digit.png?raw=true" alt="img" width="300"/>
<br>

#### 3. K-Means for Image Compression
In this section k-means algorithms was used to compress images. To achieve this goal the clustering was performed on the colors of the image. The image was reshaped into a matrix of shape (rows*cols, 3) and then each vector in the image was gouped into one of the 4 clusters using k-means algorithm. Then the image was reshaped back into its original shape and saved. The original and compressed images are shown below:
<br>
<img src="https://github.com/mahvash-siavashpour/mahvash-siavashpour.github.io/blob/main/assets/img/bird.png?raw=true" alt="img" width="400"/>
<br>

#### 4. DBSCAN for More Complex Data Clustering
DBSCAN algorithm was used in this section to cluster more complex data distributions that cannot be properly clustered using k-means. To used this algorithm it is necessary to set min pts and eps properly. In order to find the optimal eps KNN algorithm was used.<br> 

Howevet, the min pts was set using some rules and experiments. <br>
The larger the data set, the larger the value of MinPts should be<br>
If the data set is noisier, choose a larger value of MinPts<br>
Generally, MinPts should be greater than or equal to the dimensionality of the data set<br>
For 2-dimensional data, use DBSCAN’s default value of MinPts = 4 (Ester et al., 1996).<br>
If your data has more than 2 dimensions, choose MinPts = 2*dim, where dim= the dimensions of your data set (Sander et al., 1998)<br>
<br>

Also having the optimal eps, min pts can be obtained via testing different values. 
<br>
<img src="https://github.com/mahvash-siavashpour/mahvash-siavashpour.github.io/blob/main/assets/img/minpts.png?raw=true" alt="img" width="300"/>
<br>



### Association Rule Extraction
Association rules represent relationships and interdependencies between large sets of data items.

A common example of association rule discovery is "shopping cart analysis". In this process, according to the various items that customers put in their shopping carts, the buying habits and behavior of customers are analyzed, and by identifying the relationship between products, repeating patterns during shopping can be obtained.<br>

Three important parameters:<br>
1. Support shows the popularity of a set of items according to the frequency of transactions.
2. Confidence shows the probability of buying item y if item x is bought. x -> y
3. Lift is a combination of the above two parameters.
To implement association rules in this project, we use the Apriori algorithm, which is one of the most popular and efficient algorithms in this field.


#### How does the Lift parameter affect the probability of occurrence
The lift value calculates the probability of an item occurring if another item has occurred, while also considering the frequency of each of the two items.
The amount of lift can be calculated using the following equation:<br>
```
lift = confidence / expected_confidence = confidence / ( s(body) * s(head) / s(body) ) = confidence / s(head)
```
The lift value can have values ​​from 0 to infinity<br>

Three different scenarios can happen:<br>

1. If the lift value is greater than 1, it indicates that the body and head of the rule appear together more than expected, meaning that the body event has a positive effect on the head event.
2. If the lift value is less than 1, it means that the body and the head of the rule appeared together less than expected, and in this way, the occurrence of the body has a negative effect on the probability of the occurrence of the head.
3. If the lift value is close to 1, it shows that the body and the head occur together almost as expected, meaning that the body event will not affect the head event.
<br>

#### Apriori Algorithm
The algorithm works in a way that a minimum support value is considered and repetitions occur with frequent itemsets. If the sets and subsets have a support value lower than the threshold, they are removed. This process continues until there is no possibility of deletion.<br>

First I prepared the dataset in the form of a sparse matrix with the purchased products in the column and the purchase order number as the index. For convenience, the purchased products were coded using 0 and 1 in each column. Then by using `TransactionEncoder` function from `mlxtend.preprocessing` the transaction were encoded. Finaly the apriory algithm was applied with a min_support of 0.07 .
<br>
<img src="https://github.com/mahvash-siavashpour/mahvash-siavashpour.github.io/blob/main/assets/img/apriori.png?raw=true" alt="img" width="300"/>
<br>

Then the implemented `extract_rules` function was used with dynamic lift and confidence values to extract association rules.


### Diabetes Detection
The description of this project can be found [here](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/blob/main/Diabetes-Detection/README.md)
