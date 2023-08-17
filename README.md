# AlgerianForestProject

### Goal : This Project is used to Predict the FWI (Fire Weather Index) based on the other variables provided.

# How to use the project

## Contents of the project
- models folder contains the pickle files of Standard Scaler and Ridge CV model
- notebooks folder contains the uncleaned dataset and the Jupyter notebook file of the EDA & Regression performed
- templates file contains the home.html file which is used for rendering the template in our flask app
- application.py is the main file which uses flask and render template for using the home.html file
- requirements.txt contains the requirements to be dowloaded before running the application

## First clone the git project by using command
   ```javascript
   git clone https://github.com/rachitdani/AlgerianForestProject.git
   ```
## Then install the requirments.txt file using command
  ```javascript
  pip install -r requirements.txt
  ```
## Then run the application.py file 
 ```javascript
  application.py
  ```

# Approach Used for Development of Project
## Step 1 : EDA & Feature Selection

### Algerian Forest Fires Dataset 

#### Data Set Information:

The dataset includes 244 instances that regroup a data of two regions of Algeria,namely the Bejaia region located in the northeast of Algeria and the Sidi Bel-abbes region located in the northwest of Algeria.

122 instances for each region.

<br>The period from June 2012 to September 2012.
<br>The dataset includes 11 attribues and 1 output attribue (class)
<br>The 244 instances have been classified into fire(138 classes) and not fire (106 classes) classes.

#### Attribute Information:

1. Date : (DD/MM/YYYY) Day, month ('june' to 'september'), year (2012)
Weather data observations
2. Temp : temperature noon (temperature max) in Celsius degrees: 22 to 42
3. RH : Relative Humidity in %: 21 to 90
4. Ws :Wind speed in km/h: 6 to 29
5. Rain: total day in mm: 0 to 16.8
FWI Components
6. Fine Fuel Moisture Code (FFMC) index from the FWI system: 28.6 to 92.5
7. Duff Moisture Code (DMC) index from the FWI system: 1.1 to 65.9
8. Drought Code (DC) index from the FWI system: 7 to 220.4
9. Initial Spread Index (ISI) index from the FWI system: 0 to 18.5
10. Buildup Index (BUI) index from the FWI system: 1.1 to 68
11. Fire Weather Index (FWI) Index: 0 to 31.1
12. Classes: two classes, namely Fire and not Fire

## Step 2 : Perform Various Regression Algorithms
- Performed various regression algorithmns as the output feature to be predicted is a continous variable.
- Performed Algorithms like Linear ,Lasso,Lasso CV,Ridge ,Ridge CV ,ElasticNet ,ElasticNet CV .
- Out of the Algorithms used Ridge CV proved to gives us an accuracy of 98.43%.

## Step 3 : Downloading Model with the best accuracy & Standard Scaler pickle file 
- Downloading the Ridge Cv and StandardScalar pickle file so we can use it in future for our deployment.
- The StandardScaler file is required because the input we provide must be standarized before passing to the model.

## Step 4 : Developing a flask app
- Finally the application.py is created which takes inputs of the other parameters from the user and predicts the FWI index.
