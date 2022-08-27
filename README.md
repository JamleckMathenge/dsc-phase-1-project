# PHASE1 PROJECT.
# MICROSOFT STUDIO MOVIE ANALYSIS.
# PROJECT OVERVIEW.
# In the conceptualization of this project, I assumed the role of a Data Scientist at Microsoft. This project entails a comprehensive understanding and analysis of movies from (“zippedData”) to come up with business-related recommendations for the head of Microsoft on the creation of a new movie studio. The main purpose of this project is to make use of exploratory data analysis to acquire information required to recommend appropriate actions by Microsoft on the creation of the new movie studio. This project is supplemented by visualizations to assist in the conceptualization of the findings.
# 1.2: BUSINESS UNDERSTANDING.
# The key objective of this project is to formulate data-backed recommendations for Microsoft in the creation of the new movie studio. Throughout this project, as a Data Scientist, I intend to formulate three key recommendations that will answer the following business questions.
# 1.Which directors should Microsoft Studio employ in creation of movies?
# 2.Which writers should Microsoft Studio employ in creation of movies?
# 3.What is the best runtime range for movies?
# 4.Which are the most preferred movie genres among movie fans?
# 5.In which regions should Microsoft studio focus its movie marketing efforts?
# 6.How does the movie ordering affect the number of movies watched?

# Using the data sets given, I intend to use data understanding and analysis to answer the questions above which will form the foundation of my recommendations to Microsoft. I have formulated the questions above to be a guide to the data sets I require and to make judgments on the type of analysis I would need to do.
# DATA DESCRIPTION.
# The ("zippedData/im.db")database contains 8 tables including: movie_basics, directors, known_for, movie_akas, movie_ratings, persons, principals and writers.The tables contain numerous data from various sources in the following shapes;
# 1. Principals - It has 1028186 rows and 6 columns.
#  The columns are: 
# a.movie_id -  This is a unique identifier for each movie.                 
# b. ordering - This is the studio requesting a level of production in a movie.
# c.person_id - This is a unique identifier for each person.
# d. category - This shows the occupation of each person.
# e. job - This shows the current job for each person.
# f. characters- This shows the various characters played by each person.
# 2. Persons - It has 606648rows and 5 columns.
# The columns are: 
# a.person_id -  This is a unique identifier for each person.                 
# b.primary_name - This is the  name associated with the person_id
# c.birth_year - This is the year of birth for each person.
# d.death_year - This is the year of death for each person(if deceased).
# e.primary_profession - This shows the main occupation of each person.
# 3. Known_for - It has 1638260 rows and 2 columns
# The columns are: 
# a.person_id - This is the unique identifier for each person.
# b.movie_id - This is the unique identifier for each movie.
# 4. Directors - It has 291174 rows and 2 columns.
# The columns are: 
# a.person_id - This is the unique identifier for each person.
# b.movie_id - This is the unique identifier for each movie.
# 5. Writers  - It has 255873 rows and 2 columns.
# The columns are: 
# a.person_id - This is the unique identifier for each person.
# b.movie_id - This is the unique identifier for each movie.
# 6. Movie_basics - It has 146144 rows and 6 columns.
# The columns are: 
# a.movie_id -  This is a unique identifier for each movie.                 
# b.primary_title - This is the main title related to the movie_id.
# c.original_title- This is the initial title related to the movie_id.
# d.start_year - This is the year of conception of the movie.
# e.runtime_minutes- This is the duration of the movie in minutes.
# f.genres- This is the type of movie.
# 7. Movie_ratings  - It has 73856 rows and 3 columns.
# The columns are: 
# a.movie_id - This is the unique identifier for each movie.
# b.averagerating - This is the rating of each movie out of 10 as per feedback.
# c.numvotes - This is the number of feedbacks for each movie’s averagerating
# 8. Movie_basics - It has 331703 rows and 8 columns.
# The columns are: 
# a.movie_id -  This is a unique identifier for each movie.                 
# b. ordering - This is the studio requesting a level of production in a movie.        
# c. title- This is the title related to the movie_id.
# d. region - This is the geographical area where the movie is popular.
# e. language- This is the audio language of the movie.
# f. types- This is the version of the movie.
# g. attributes - This shows the unique features of each movie.
# h.is_original_title - This shows if the current title is the original title.

# The ("zippedData/bom.movie_gross.csv.gz") CSV file contains a table with data about movies.The table has 3387 rows and 5 columns.
# The columns are:
# a.title-This is the title of a movie.               
# b. studio- This shows which studio conceptualized the movie.      
# c.domestic_gross- This is the revenue earned by a movie in the country of  conception.
# d.foreign_gross- This is the revenue earned by a movie outside the country of conception.
# e. year -This shows the year in which the movie gained the revenue streams.
# The ("zippedData/tmdb.movies.csv.gz") CSV file contains a table with data about movies.
# The table has 26517 rows and  10 columns.
# The columns are:
# a. Unnamed:0- This is a repetition of the index.               
# b. genre_ids- This is the unique identifier for each genre.   
# c. ids- This is a unique identifier for each movie.
# d. Original language- This is the initial language of a movie in its conception.                                       
# e. Original_title - This is the initial title for the movie when it was created
# f. popularity-This is the count of the number of times a movie is watched.
# g. Release_date- This is the date when a movie was released from a studio.
# h. Title- This is the name that a movie goes by currently.
# i. vote_average-This is the average rating of the votes by fans on a specific movie.
# j. Vote_count- This is the number of votes cast by fans on a movie.
# The ("zippedData/tn.movie_budgets.csv.gz") CSV file contains a table with data about movies.
# The table has 5782 rows and 6 columns.The columns are:
# a.id -  This is a unique identifier for each movie.              
# b.Release_date- This is the date when a movie was released from a studio.      
# c. movie -This is the name of a movie.
# d. production_budget-This is the cost of creating a movie.
# e. domestic_gross-This is the amount of revenue earned by a movie in its origin country.
# f. worldwide_gross-This is the amount of revenue earned by a movie globally.
# DATA CLEANING.
# The main purpose of data cleaning is to prepare the data for analysis which will then be useable to answer our project questions. Data cleaning was also done to ensure the validity, accuracy, completeness, consistency, and uniformity of the data.I then selected the tables that I would use as the basis for my recommendations. I then cleaned the tables selected using the following steps:
# TASK1:The first task was to check if the column names were uniform and readable. 
# TASK2: The second task was to check for duplicated rows. 
# TASK3:The next task was to check if there were missing values. 
# TASK4:The next task was to decide how to deal with the missing values. (Either drop if they are unnecessary or replace the missing values with the best fit.
# TASK5: The last task was to check if the data types of the columns were correct.(If the data type was wrong I corrected it.
# After I had cleaned all the data that I needed.  The resultant data frames were ready for analysis.
# EXPLORATORY DATA ANALYSIS.
# In this section, I investigated the data sets I intended to use in order to create visualizations that would act as the base of my recommendations.
# VISUALIZATION 1:
# ![image](https://user-images.githubusercontent.com/110511316/187023053-ba2631bc-8fc5-444b-9ccd-1e062120e9d9.png)
# This bar chart shows the best directors in the movie industry. I only took into consideration movies that had above 1000 votes so as to ensure that the average rating was a clear indication of what movie fans think about a certain movie.
# VISUALIZATION 2:
# ![image](https://user-images.githubusercontent.com/110511316/187023131-b4d400f7-e318-4521-a485-7f13555e49b9.png)
# This bar chart shows the best writers in the movie industry. I only took into consideration movies that had above 1000 votes so as to ensure that the average rating was a clear indication of what movie fans think about a certain movie.
# VISUALIZATION 3:
# ![image](https://user-images.githubusercontent.com/110511316/187023215-5821f317-a8c4-4198-a03f-e065bc6e16e6.png)
# The histogram above shows the runtime in minutes of the movies that had an average rating of above 7 and had a minimum of 1001 votes. This was to show what is the best runtime of a movie especially movies that have a high rating.
# VISUALIZATION 4:
# ![image](https://user-images.githubusercontent.com/110511316/187023256-3f8402c8-4d79-44be-a40b-7ec2b78ba6c2.png)
# In the bar chart above, I have shown the relationship between the Top rated genres against the number of movies that had an average rating of above 7 and at least 1001 votes. I did this to show which are the most watched among the top-rated genres.
# VISUALIZATION 5:
# ![image](https://user-images.githubusercontent.com/110511316/187023289-96d1eb1a-488d-4132-ab9b-7d9310ade10a.png)
# The bar chart above shows the regions with the most movie fans based on the number of movies watched per region. I did this visualization to show the relationship between each region and the popularity of movies in the regions.
# VISUALIZATION 6:
# ![image](https://user-images.githubusercontent.com/110511316/187023363-82e18424-ded5-401c-aa4c-887f03543404.png)
# The bar chart above shows the relationship between movie ordering and the number of movies watched. It shows that the number of movies watched reduces as the ordering increases.
# RECOMENDATIONS.
# From VISUALIZATION 1, I recommend that Microsoft Studio employ directors who feature in the figure based on their availability and rating showed by the figure. This is because they have directed the movies with the best rating among movie fans. 
# From VISUALIZATION 2, I recommend that Microsoft Studio employ writers who feature in the figure based on their availability and rating showed by the figure. This is because they have helped create the movies with the best rating among movie fans. 
# From VISUALIZATION 3, I recommend that Microsoft Studio should create movies that have a runtime in the range of (100-125 minutes) . This is because my analysis has concluded that most of the top rated movies have a runtime in this range.
# From VISUALIZATION 4, I recommend that Microsoft Studio should focus on the following movie genres (Drama, Documentary, Comedy-Drama, Drama-Romance, Comedy-Drama-Romance). This is because among the top rated movies this genres feature the most.
# From VISUALIZATION 5, I  recommend that Microsoft Studio should focus their movie marketing in the following regions (US,  XWW, RU, DE, FR). This is because they are the regions with the most movie fans.
# From VISUALIZATION 6, I recommend that Microsoft Studio should create movies with as little ordering as possible. This is because I found out in my analysis that the number of movies watched is inversely proportional to increase in ordering.





























                                   




