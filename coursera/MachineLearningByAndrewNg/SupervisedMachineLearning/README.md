# Supervised Machine Learning 

Course: [Supervised Machine Learning](https://www.coursera.org/learn/machine-learning)

## Supervised vs Unsupervised Machine Learning

   **Machine Learning** *is a field of study that gives computers the ability to learn without being explicitly programmed.* 
                                        ***~by Arthur Samuel(1959)***


This course is more than just teach what is Supervised ML, it will teach us practical approach for applying learning algorithms.

### Supervised Learning
    
They are ml algorithms which learn input to output labels, It learns from being given "Right answers"(correct labels), after series of iterations it can predict the answer using only input.
     
Classification algorithms predict categories(classes).they are also have small number of possible outputs compared to Regression

### Unsupervised Learning

There is no labels given, the purpose is to find something intresting (patterns or structure) in unlabelled data.

**Applications:**

Clustering :- Groups similar data points.
Anomaly Detection :- find unusual data points.
Dimensionality Reduction :- compress data using fewer numbers


Example for Clustering : Google News, DNA microarray 
See the example below this is news content about pandas.
when we choose this news we can see similar news with keywords which was not labeled, It just predicted on it's own.

<img src="/other/images/SupervisedML(1).png" width = 400 >

The machine see the pattern and clusters the news from the unlabelled news and show the recommedation.

<img src="/other/images/SupervisedML(2).png" width = 400 >

## Regression Model

### Linear Regression model

`Classification model predicts categories`

`Regression model predicts numbers`

Terminology that is used to talk about machine learning concepts.


|Term          |Meaning                        |Notation|
|--------------|:-----------------------------:|-------:|
|Training set|Data used to train the model.|x(input feature) y(output or target feature)|
|Testing set  |                               |     |

<img src="/other/images/LinearRegression(1).png" width = 400 >

   f<sub>wb</sub>(x) = wx + b 

 Linear Regression for single Variable


### Cost Function Formulae

`Cost Function` :- 
