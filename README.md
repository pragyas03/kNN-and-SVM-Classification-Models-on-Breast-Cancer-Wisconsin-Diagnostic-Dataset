# kNN-and-SVM-Classification-Models-on-Breast-Cancer-Wisconsin-Diagnostic-Dataset

I built a system for Benign or Malignant cancer classification based on various features. On the given dataset, KNN performed better than SVM possibly signifying that the dataset is not linearly separable (there could be other reasons also, like, outliers in the data set). This conforms to what scatter plot of features from dataset showed.

# Major Dependencies
* Python > 2.7
* Scikit Learn package
* Pandas toolkit 
* Numpy toolkit 

# Dataset
Here, Breast Cancer Wisconsin (Diagnostic) Dataset is used. The data is taken from the file 'breast_cancer_wisconsin.csv'. The headers are also added in the file representing the features used in the dataset. The abbreviations and corresponding column names list can be found in the file 'breast-cancer-wisconsin.names.txt'.

The first dataset looks at the predictor classes: 
* Malignant or
* Benign breast mass

The features characterize cell nucleus properties and were generated from image analysis of fine needle aspirates (FNA) of breast masses
* Sample ID (code number)
* Clump thickness
* Uniformity of cell size
* Uniformity of cell shape
* Marginal adhesion
* Single epithelial cell size
* Number of bare nuclei
* Bland chromatin
* Number of normal nuclei
* Mitosis
* Classes, i.e. diagnosis

# Tasks Performed

* At first the data preprocessing is done. The dataset file is read and stored in the variable named data. It is found that the class value 2 corresponds to Benign as the diagnosis and 4 corresponds to malignant. The value of Benign is set as 1 and Malignant is set as 0. <br>
* There were some missing values in the dataset. These missing values require proper handling in order to achieve more accuracy in the model. Since the dataset is small, removal of the missing values can drastically impact the quality of the machine learning model and hence the technique of imputation is used to handle the missing values. There are in total of 18 missing values.<br>
* Using matplotlib and seaborn libraries the features are visualized and the features distribution plot for all the nine features of the dataset is created. The red plot depicts benign and the blue plot depicts malignant categories. From the visualised data, it can be interpreted that for benign class the data is skewed and it is concentrated between 0 & 2, whereas for malignant class the data is evenly distributed. However, this is not the case for the feature, 'Clump Thickness' and for this feature the data for benign and malignant class is evenly distributed.<br>
* Then feature scaling is done. Feature scaling refers to putting the values in the same range or same scale so that no variable is dominated by the other. Here, the values are shifted and rescaled so that they end up ranging between 0 and 1. It is also known as Min-Max scaling.<br>
* The technique of imputation is used in order to handle missing values and these values are replaced with the mean or average of the corresponding feature values. Then those rows are printed that contained the missing values, just to show that after imputation there are no missing values in the data.<br>
* Outliers are data points or observations that lie at an abnormal distance from other values in a random sample. Handling outliers is important as these create problems in statistical analysis of the data. Here, a box and whisker plot is used to identify outliers. The points that are outside the box length are the outliers. <br>
* Zee score is to determine the number of standard deviations a given raw score is above or below the mean. In other words, we just need to subtract the mean from the raw score and divide by the standard deviation. In order to handle the outliers I used Z score.<br>
* Correlation analysis is an extensively used technique that identifies interesting relationships in data. Here, correlation analysis is done by plotting a heatmap using seaborn library. A heatmap is a graphical representation of data in which data values are represented as colors. <br>
* Univariate feature selection is done. It works by selecting the best features based on univariate statistical tests. SelectKBest from scikit library is used here. It removes all but the highest scoring features.<br>
* Principal Component Analysis, or PCA, is a dimensionality-reduction method that is often used to reduce the dimensionality of large data sets, by transforming a large set of variables into a smaller one that still contains most of the information in the large set. The PC1 axis is the first principal direction along which the samples show the largest variation. The PC2 axis is the second most important direction. A plot of PC1 v/s PC2 is shown. It is very evident from the plot that the Malignant class is spread out as compared to the Benign class.<br>

# kNN Classification Model
KNN is a model that classifies data points based on the points that are most similar to it. It is a supervised machine learning algorithm that uses test data to make an “educated guess” on what an unclassified point should be classified as.
The value of the nearest neighbor is taken as 10 and then the prediction is done using the training data.
Further, the normalized confusion matrix is plotted, which shows that using the kNN model the accuracy of the prediction of the malignant class is around 99% and for the benign class around 92%.

# SVM Classification Model
Support Vector Machine” (SVM) is a supervised machine learning algorithm which can be used for both classification or regression challenges. However,  it is mostly used in classification problems. In the SVM algorithm, we plot each data item as a point in n-dimensional space (where n is the number of features in the dataset) with the value of each feature being the value of a particular coordinate. Then, we perform classification by designing a hyperplane that classifies all training vectors in two classes very well. In d dimensional space the hyperplane is d-1 separator. Hence, in 2D space the hyperplane is a 1 dimensional line and in 3 dimensional space the hyperplane is a 2 D plane.

![Graphical Representation of SVM Model](https://github.com/pragyas03/kNN-and-SVM-Classification-Models-on-Breast-Cancer-Wisconsin-Diagnostic-Dataset/blob/main/SVM.png)

Further, the normalized confusion matrix is plotted, which shows that using the SVM model the accuracy of the prediction of the malignant class is around 89% and for the benign class around 99%.

# Evaluation of kNN and SVM Models
A verification of both the trained models is done by simply testing a random sample and getting the prediction. Here, it is found that for the given dataset, the accuracy of kNN model for k=5 is more as compared to the SVM model.
