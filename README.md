# Ames Housing Data and Fun Kaggle Competition Twist
*Data Modeling and Visualization*
 #### Arink Bertrand

This was the 3rd Project for General Assembly's Data Science Immersive course.
We used the Ames Housing Dataset to model and predict the prices in Ames, Iowa.

This project had a competitive element, where we could take our models that had good RMSE scores on the train datasets and see how well we scored on Kaggle with the test dataset. 

## Table of Contents
- [Objective](#obj)
    -  [Steps](#steps)
- [Other Attempts](#other)
- [Data Dictionary](#data)
- [Dependencies](#lib)
- [Future Plans](#fut)
- [Just Give me the Scores](#scores)

## Objective <a id='obj'></a>

The goal of this project was to predict the sale price of each house using the train dataset, then see how well the predictions did on the test dataset in the Kaggle competition.

The data was provided to us, but variations of it is available on Kaggle 

To achieve the best prediction model I read in the datasets (test.csv and train.csv) 


### Steps <a id='steps'></a>
- [x] Import and Read in Data
- [x] Breakup code into 3 Notebooks
- [x] Asses and Handle Null Values
- [x] Exploratory Data Analysis
- [x] Feature Engineering
- [x] Selecting Features
- [x] Modeling
- [x] Visualization
- [x] Cleanup
- [x] ReadMe

## Data Dictionary <a id='data'></a>
The descriptions of the columns and it's values can be found <a href='http://jse.amstat.org/v19n3/decock/DataDocumentation.txt'> here </a>

## Other Attempts <a id='other'></a>
In the code-addtl folder there are two more notebooks
- Ames - Predictions - OneHot.ipynb
    - A kitchen sink attempt, made polynomial features with the same selected features as 
    Ames - Predictions notebook, and created dummy variables for the rest of the dataset. I now had a dataset with 300+ columns. This was an experimental attempt.
    - Even thought the training dataset's lowest RMSE was in this notebook, it had the highest RMSE on the test dataset on Kaggle.

- Ames - Training-Data-Additional-Engineering.ipynb
    - This is an unfinished notebook but it is also a 'further step', since the one-hot notebook made so many columns and didn't do as well, the next plan I had was to take some of the categorical columns and shrink them down myself before dumming the columns. 

## Dependencies <a id='lib'></a>
- Python 3 (or newer)
- Numpy
- Pandas 
- Matplotlib
- Seaborn
- Sklearn    

## Future Plans <a id='fut'></a>    
As stated in the Other Attempts section, I'd like to finish the additional engineering notebook and see how well that does on my models.

Additionally some clasmates had great results with stacking models in their predictions, I'd like to explore that posibility further, and creating function pipelines to reduce some of the repetitiveness.

This project was alot of fun for me, even though my model has some things I need to explore further and evaluate (negative coefficients to Squarefeet of the home for example). The competitiveness was in fun and added a push to the project.

## Just Give me the Scores: <a id='scores'></a>

If you just want to see the scores, the tables are broken down by Notebook:

<table>
<tr><th> Predictions  </th><th> One Hot </th></tr>
<tr><td>

|| Train RMSE | Kaggle RMSE|Notes|
|--|--|--|--|
|LR| 32336.27|37027.42|Overfit|
|LR w. P| 26417.70|29072.82 |neg. coef_ |
|RidgeCv| 26305.96|29620.10||
|LassoCV| 27384.13|29409.22||
|ElasticCV| 66293.64|-|Not Sub.|
|LassoGS| 26410.38|26347.73 |Private Score 25182.79|



</td><td>

|| Train RMSE | Kaggle RMSE|Notes|
|--|--|--|--|
|LR|- | -||
|LR w. P| 22624.51|-|Overfit|
|RidgeCv| 22398.57|- |Overfit|
|LassoCV| 21016.95|- |So Exciting!|
|ElasticCV| -|- ||
|LassoGS| 20805.78|34390.38|WHAT?!?|

</td></tr> </table>

Lesson learned: Pay close attention to overfit and 300+ columns is not good. I was so excited about the lasso RMSE and score closeness, had I submitted any of the models prior in the One Hot I would have realized earlier that I was on the wrong track.