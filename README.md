## The movie industry is playing a significant rule in the econmy in the last decade, So in this project I aimed to analyze movies of the last 100 years and make a movie recommender system with the same dataset.

## This project has went throgh 5 phases:-

#### 1)Data collection

#### 2)Data cleaning

#### 3)Exploratory data analysis (EDA)

#### 4)Data visualization (using power bi)

#### 5)building a machine learning model

##now I'll talk about each phase in details...

### 1) Data collection:

* For this project I used "IMDb movies extensive dataset" by Stefano Leone from kaggle (link: https://www.kaggle.com/stefanoleone992/imdb-extensive-dataset).
* The dataset had 4 csv files but I decided that the "IMDB novies.csv" file will be enough for this project.

### 2) Data cleaning:

-The code of this part is in "Data Cleaning.ipynb", I used pandas library to clean the data.
-Tere were too many null value in the dataframe, but I decided to only drop the records with null values in the budget, USA income, and world wide income as I think that these columns
are the most important for the analysis.
-The columns related to money (like budget, USA income, World wide income) has values in diffrent currencies, so I made a function to remove currency code and convert the values to us
dollars using https://www.xe.com/ to get the us values for each currency.
-I made two columns to calculate the usa revenue and world wide revenue by subtracting gross income from budget.
-There were some columns with many values (like actors, directors, genres...) so I made a corresponding for each one only storing the first value as the main value, that will make the
analysis and visualization alot more easier.
-Some columns with numerical values didn't have an int/float datatype so I cahnged their datatypes.
-I saved the dataframe as a csv file to the current directory.
-I then made a function to slice the dataframe by the production comapny, and then save it as a csv file to the current directory. That will be usefu if we want to analyze a specific
production company.

### 3)Exploratory data analysis (EDA):

* The code of this part is in "Exploratory Data Analysis.ipynb", I used pandas library to analyze the data, matplotlib and seaborn for visualizations.

### 4) Data visulaiztaion (using power bi):

* The dashboards are in "Data Visualization" file.
* In this dashboard I made 7 pages about (countries, actors, movies, gneres, production comapnies, writers and directors, time and revenue) plus two additional pages about production 
comapnies (Disney, Universal pictures).

### 5) Machine learning model:

-The code of this part is in "Movie Recommendation System.ipynb", I used pandas library for data cleaning, and sklearn for ML models.
-I made a movie recommendation system using sklearn by storing some important features of each row as a string and then used cosine similarity to make a matric with m*m shape, as m 
is the length of the dataset, each cell holding the degree of similarity between its row and its column.
-I then sliced the dataset into a 10,000 rows since my laptop won't handle a 85,000 * 85,000 matric.
-But before slicing the data I re-sorted the dataset in a descending order, so that the model will recommend new movies.
-I made a function that take a movie name and pass the movie name in the dataset with the right synatx to use it in the model.
-I then made a model that takes a movie name as return the most 10 similar movies to it.
