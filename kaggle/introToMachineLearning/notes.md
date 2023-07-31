# Intro to Machine Learning
this course consist of 7 lessons those are :

1. **How Models Work**
The first step if you're new to machine learning.

2. **Basic Data Exploration**
Load and understand your data.

3. **Your First Machine Learning Model**
Building your first model. Hurray!

4. **Model Validation**
Measure the performance of your model, so you can test and compare alternatives.

5. **Underfitting and Overfitting**
Fine-tune your model for better performance.

6. **Random Forests**
Using a more sophisticated machine learning algorithm.

7. **Machine Learning Competitions**
Enter the world of machine learning competitions to keep improving and see your progress.

## 2. Basic Data Exploration

The first step in any machine learning project is familiarize yourself with the data. You'll use the Pandas library for this. Pandas is the primary tool data scientists use for exploring and manipulating data. Most people abbreviate `pandas` in their code as   `pd`. We do this with the command

The example (Melbourne) data is the file melb_data.csv.

We load and explore the data with the following commands:
```python
# save filepath to variable for easier access
melbourne_file_path = '../input/melbourne-housing-snapshot/melb_data.csv'
# read the data and store data in DataFrame titled melbourne_data
melbourne_data = pd.read_csv(melbourne_file_path) 
# print a summary of the data in Melbourne data
melbourne_data.describe()
```
this will print the data in tabulated form

## 3. Your first machine learning model

To choose variables/columns, we'll need to see a list of all columns in the dataset. That is done with the columns property of the DataFrame 

```python
import pandas as pd

melbourne_file_path = '../input/melbourne-housing-snapshot/melb_data.csv'
melbourne_data = pd.read_csv(melbourne_file_path) 
melbourne_data.columns
```
**dropna** drops missing values (think of na as "not available")
```python
melbourne_data = melbourne_data.dropna(axis=0)
```
There are many ways to select a subset of your data.
we will focus on two approaches for now.

    * Dot notation, which we use to select the "prediction target"
    * Selecting with a column list, which we use to select the "features"

### Selecting The Prediction Target

You can pull out a variable with dot-notation. This single column is stored in a Series, which is broadly like a DataFrame with only a single column of data.

We'll use the dot notation to select the column we want to predict, which is called the prediction target. By convention, the prediction target is called y. So the code we need to save the house prices in the Melbourne data is
```python
y = melbourne_data.Price
```
### Choosing "Features

The columns that are inputted into our model (and later used to make predictions) are called "features." In our case, those would be the columns used to determine the home price. Sometimes, you will use all columns except the target as features. Other times you'll be better off with fewer features.

For now, we'll build a model with only a few features. Later on you'll see how to iterate and compare models built with different features.

We select multiple features by providing a list of column names inside brackets. Each item in that list should be a string (with quotes).

```python
melbourne_features = ['Rooms', 'Bathroom', 'Landsize', 'Lattitude', 'Longtitude']
```
**By convention, this data is called X.**  

### Building Your Model

You will use the **scikit-learn** library to create your models. When coding, this library is written as **sklearn**, as you will see in the sample code. Scikit-learn is easily the most popular library for modeling the types of data typically stored in DataFrames. 

The steps to building and using a model are:

1. Define: What type of model will it be? A decision tree? Some other type of model? Some other parameters of the model type are specified too.

2. Fit: Capture patterns from provided data. This is the heart of modeling.

3. Predict: Just what it sounds like

4. Evaluate: Determine how accurate the model's predictions are.
    


Here is an example of defining a decision tree model with scikit-learn and fitting it with the features and target variable.

```python
from sklearn.tree import DecisionTreeRegressor

# Define model. Specify a number for random_state to ensure same results each run
melbourne_model = DecisionTreeRegressor(random_state=1)

# Fit model
melbourne_model.fit(X, y)
```
Many machine learning models allow some randomness in model training. Specifying a number for random_state ensures you get the same results in each run. This is considered a good practice. You use any number, and model quality won't depend meaningfully on exactly what value you choose.

Example:
```python
print("Making predictions for the following 5 houses:")
print("The predictions are")
print(melbourne_model.predict(X.head()))
```
output : `The predictions are
[1035000. 1465000. 1600000. 1876000. 1636000.]`
