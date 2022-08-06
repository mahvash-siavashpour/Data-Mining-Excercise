# Data-Mining-Excercise
There 4 different project in this repository that each cover a different section in the datamining world; from preprocessing and analyzing data to classification, clustering, etc.
## Project List
- [Analysing Iris Dataset](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/blob/main/Analyse_Iris_Dataset.ipynb)
- [Classification](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/blob/main/Classification.ipynb)
- [Clustering](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/blob/main/Clustering.ipynb)
- [Association Rule Extraction](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/blob/main/AssociationRules.ipynb)
## Project Description
A series of different data mining sub-projects are implemented in this project. This project was implemented to practice using different libraries and to work with different algorithms to gain knowledge and experience in this field of science. The full explanation of each sub-projects is written in the following sections.
### Analysing Iris Dataset
This project aimed at preprocessing the data obtained from the Iris dataset using two major preprocessing libraries in machine learning: [Pandas] (https://pandas.pydata.org/docs/), and (scikit-learn) [https://scikit-learn.org/stable/]. <br>
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
### Association Rule Extraction
