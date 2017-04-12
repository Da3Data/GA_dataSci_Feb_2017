Rubric for the Student Project
Dennis Alishah

# Acquisition

Explain how you acquired the data
- Acquired the public data set from https://grouplens.org/datasets/movielens/1m/.
- Contains a zip file with 3 tables in .dat format and a README file.
- Once data was extracted I imported into excel first to see the structure and contents.

Justify why this is a reasonable sample to work from. 
- Easy to understand
- Good practice for data wrangling using pandas; merging multiple tables into one dataframe, splitting categorical data using dummy variables, mapping coded values in columns to more meaningful values.
- Good practice for predicting recommendations using content and colloborative filtering.

Identify any sampling biases or issues.
- Age is only an Age range; there are no specific ages only age ranges. Therefore when calculating the mean Age its only an estimate and not entirely accurate. 

# Preprocessing

State what transformations you did on the data and why these were necessary

- Age mapped to AgeRange; needed to display the exact age ranges. 

- Occupation code mapped to Occupation name; more meaningful names. Will be more understandable when applying any analysis on the occupation column.

- Merging all separate tables into one dataframe; the data is related so once all tables are combined can apply different analysis. Allows for more observations, understanding and conclusions to made of the data once its all combined. 

- Splitting the movie genres into seperate columns; allows for recommendations based on a user preferences.

# Exploration

Present the data in ways that help the audience understand what is going on.

Explain what methods you used and what you rejected. (For example,
  if you clustered the data as an exploration, why did you choose
  those clustering parameters? If you present the data graphically,
  why did you choose that visualisation?)

- plotted the age distribution to visualize which users rated the most movies. 

- plotted the difference in male vs female ratings using a barh plot which is a horizontal bar graph. This type of graph cleary shows the differences between two variables.

# Learning 

What algorithms did you use? 

Why did you use them?

- Content Filtering was achieved using the dot product of two vectors (movie genres & user preferences). The higher the score the more likely it would be recommended.

Collaborative Filtering was achieved by; 
- creating a matrix of unique users to the unique movies they rated, 
- getting the similarities between movies using numpy.corrcoef that calculates the Pearson Correlation Coefficient between each item pair. 
- To find similar movies to a specific movie need to return those movies that have a high correlation coefficent with that one.
- To provide recommendations to a user need to take the list of movies that user has rated then sum the correlations of those movies with all the other ones and return a list of those movies sorted by their total correlation with the user.


# Evaluation

Report how effective your model is

- Both the content filter and colloborative filter produced good results. 
- Both recommendation systems recommended similar movies based on the users preferences.
- The results are subjective because if two different users both gave the exact same ratings for movies they would be recommended the same set of movies. Then their own opinion would judge whether they like what was recommended to them or not.
- Recommendation is a prediction and an estimate only.

Compare that model to other (less effective) models and offer reasons for this.


# Model

What do you believe are the underlying factors explaining your data?


# Presentation / Prediction

Tell an interesting story about what your data is showing, OR

Make a meaningful, falsifiable prediction based on your model, OR

Provide an explanation for something that was otherwise inexplicable in your data

- Nothing really stood out in the data that was unexplainable.
- I was happy that both of the recommendation systems (content & colloborative) worked well in my opinion.
- In order to improve the prediction model it might be possible to combine the two recommendation systems so that the output of the content filter recommendations are stored in a dataframe then that dataframe is feed into a colloborative filter as the input and see how the results look. 
- Other more sophisticated things can be done where when the recommendations are shown as output the movie posters can be shown as an image file.
- Also can create a front-end form so users could enter their age, occupation, movie genre preferences and a list of recommendations could output.


