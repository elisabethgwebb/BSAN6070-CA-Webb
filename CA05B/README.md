# BSAN6070-CA-Webb
Elisabeth Webb - BSAN6070 Assignments

## Data: ##
The data can be accessed and read in using this link https://raw.githubusercontent.com/ArinB/CA05-kNN/master/movies_recommendation_data.csv

## Libraries to Import: ##
import pandas as pd

import numpy as np

from sklearn.neighbors import NearestNeighbors

## Instructions to Run: ##
Run each section in the file named ElisabethWebb_CA05_B.ipynb in the CA05B folder. Each section in the notebook is labelled above the code and explained either in detailed comments below the code.

## Method: ##
First we import the necessary libraries, read in the data, and take a look at it. For this dataset there are only 30 records, so I did not split the data into train and test. I identified the X and y variables as X everything but the Movie Name, Movie ID, and Label, and y as the Movie Name. I then built the model using NearestNeighbors and specifying 5 n_neighbors. Next, I fit the model to the data. Using the data for the movie The Post, the goal is to identify 5 movies that are similar. For this, I put The Post's data into the neigh.neighbors() function, printed the indices, and used a for loop to find out which movie names the model identified as The Post's 5 nearest neighbors. 

## Conclusion: ##
The model identifed the 5 most similar movies to The Post. These inlcude Hacksaw Ridge, 12 Years a Slave, Queen of Katwe, The Wind Rises, and A Beautiful Mind. The Post is considered as a biography, drama, and history in its genres. When looking at the data on the 5 movies recommended by the model, they are also a combination of either two or three of these genres, so it makes sense that the model recommended these movies given that the person wanted movies that are similar to The Post.

