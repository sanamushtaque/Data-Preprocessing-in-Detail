# Data-Preprocessing-in-Detail

The probability of anomalous data has increased in today’s data due to its humongous size and its origin for heterogenous sources. Considering the fact that high quality data leads to better models and predictions, Data Preprocessing has become vital and the fundamental step in the Data Science/Machine Learning/AI pipeline. In this article, we will talk about the need to process data, and approaches for doing so.

While gathering data, one might come across three main factors that would contribute to the quality of data.
1.	**Accuracy**: Erroneous values, one that deviate from the expected. The causes for inaccurate data can be various, which include 
    *	human/computer errors during data entry and transmission
    *	users deliberately submitting incorrect values (called disguised missing data)
    *	incorrect formats for input fields
    *	duplication of training examples
2.	**Completeness**: Lacking attribute/feature values or values of interest. The dataset might be incomplete due to 
    *	unavailability of data 
    *	deletion of inconsistent data
    *	deletion of data deemed irrelevant initially
3.	**Consistency**: Aggregation of data is inconsistent.

Some other features that also affect the data quality include **timeliness** (the data is incomplete until all relevant information is submitted after certain time periods), **believability** (how much the data is trusted by the user) and **interpretability** (how easily the data is understood by all stakeholders).

To ensure that the data is high in terms of its quality, it is crucial to preprocess it. To make the process easier, data preprocessing is divided into four stages: **data cleaning**, **data integration**, **data reduction** and **data transformation**.

## Data Cleaning:

Data cleaning refers to techniques to ‘clean’ data by removing outliers, replacing missing values, smoothing noisy data and correcting inconsistent data. Many techniques are used to perform each of these tasks, where each technique is specific to user’s preference or problem set. Below, each task is explained in terms of the techniques used to overcome it.

### Missing Values:

In order to deal with missing data, multiple approaches can be used. Let’s look at each of them.
1.	**Removing the training example**: You can ignore the training example if the output label is missing (if it is a classification problem). This is usually discouraged as it leads to loss of data, as you are removing the attribute values that can add value to data set as well.
2.	**Filling in missing value manually**: This approach is time consuming, and not recommended for huge data sets.
3.	**Using a standard value to replace the missing value**: The missing value can be replaced by a global constant such as ‘N/A’ or ‘Unknown’. This is a simple approach, but not foolproof.
4.	**Using central tendency (mean, median, mode) for attribute to replace the missing value**: Based on data distribution, mean (in case of normal distribution) or median (for non-normal distribution) can be used to fill in for the missing value.
5.	**Using central tendency (mean, median, mode) for attribute belonging to same class to replace the missing value**: This is the same as method 4, except that the measures of central tendency are specific to each class. 
6.	**Use the most probable value to fill in the missing value**: Using algorithms like regression and decision tree, the missing values can be predicted and replaced.

### Noisy data:

Noise is defined as a random variance in a measured variable. For numeric values, boxplots and scatter plots can be used to identify outliers. To deal with these anomalous values, data smoothing techniques are applied, which are described below.

1.	**Binning**: Using binning methods smooths sorted value by using the values around it. The sorted values are then divided into ‘bins’. There are various approaches to binning. Two of them are smoothing by bin means where each bin is replaced by the mean of bin’s values, and smoothing by bin medians where each bin is replaced by the median of bin’s values.
2.	**Regression**: Linear regression and multiple linear regression can be used to smooth the data, where the values are conformed to a function.
3.	**Outlier Analysis**: Approaches such as clustering can be used to detect outliers and deal with them.

## Data Integration:

Since data is being collected from multiple sources, data integration has become a vital part of the process. This may lead to redundant and inconsistent data, which could result in poor accuracy and speed of data model. To deal with these issues and maintain the data integrity, approaches such as tuple duplication detection and data conflict detection are sought after. The most common approaches to integrate data are explained below.

1.	**Data Consolidation**: The data is physically bought together to one data store. This usually involves Data Warehousing.
2.	**Data Propagation**: Copying data from one location to another using applications is called data propagation. It can be synchronous or asynchronous and is event-driven.
3.	**Data Virtualization**: An interface is used to provide a real-time and unified view of data from multiple sources. The data can be viewed from a single point of access.

## Data Reduction:

The purpose of data reduction is to have a condensed representation of the data set which is smaller in volume, while maintaining the integrity of original. This results in efficient yet similar results. Few methods to reduce the volume of data are:

1.	**Missing Values Ratio**: Attributes that have more missing values than a threshold are removed.
2.	**Low Variance Filter**: Normalized attributes that have variance (distribution) less than a threshold are also removed, since little changes in data means less information.
3.	**High Correlation Filter**: Normalized attributes that have correlation coefficient more than a threshold are also removed, since similar trends means similar information is carried. Correlation coefficient is usually calculates using statistical methods such as Pearson’s chi-square value etc.
4.	**Principal Component Analysis**: Principal Component Analysis, or PCA, is a statistical method which reduces the numbers of attributes by lumping highly correlated attributes together. With each iteration, the initial features are reduced to principal components, with greater variance than the original set on the condition that they are uncorrelated with the preceding components. This method, however only works for features with numerical values.

## Data Transformation:

The final step of data preprocessing is transforming the data into form appropriate for Data Modeling. Strategies that enable data transformation are as following:

1.	**Smoothing**
2.	**Attribute/Feature Construction**: New attributes are constructed from the given set of attributes.
3.	**Aggregation**: Summary and Aggregation operations are applied on the given set of attributes to come up with new attributes.
4.	**Normalization**: The data in each attribute is scaled between a smaller range e.g. 0 to 1 or -1 to 1.
5.	**Discretization**: Raw values of the numeric attributes are replaced by discrete or conceptual intervals, which can in return be further organized into higher level intervals.
6.	**Concept hierarchy generation for nominal data**: Values for nominal data are generalized to higher order concepts.

Despite having multiple approaches to preprocessing data, it is still an actively researched field due to the amount of incoherent data being generated each day. To facilitate, IBM Cloud provides a platform for Data Scientists called **Watson Studio**, which includes services that enable the data scientists to preprocess data using drag and drop services as well as the conventional method of programming. 

* To check out more about Data Preporocessing using **SPSS Modeler** in Watson Studio, click on https://developer.ibm.com/tutorials/build-and-compare-models-using-ibm-spss-modeler/

* To check out more about Data Preporocessing using **Data Refinery** in Watson Studio, click on 
https://developer.ibm.com/tutorials/data-preparation-with-ibm-data-refinery/

* To check out more about Data Preporocessing using **Jupyter Notebook** in Watson Studio, click on https://developer.ibm.com/patterns/data-science-life-cycle-in-action-to-solve-employee-attrition-problem/
