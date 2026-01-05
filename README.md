Exploratory Data Analysis of IMDb Movies using SQL & Power BI

🔹 Project Overview
This project focuses on performing exploratory data analysis (EDA) on the IMDb movies dataset using SQL and creating an interactive 
Power BI dashboard to extract meaningful business insights.

🔹 Tools & Technologies
SQL (Data Cleaning & Analysis)
Power BI (Data Modeling & Visualization)
Power Query
DAX (Basic Measures)

🔹 Key Analysis Performed
Data cleaning and validation using SQL queries
Analysis of top movies by votes and revenue
Director-wise movie count analysis
Year-wise movie release trend
Genre-based movie insights

🔹 Power BI Dashboard Highlights
-Top 8 movies by votes
-Top 6 movies by revenue
-Director productivity analysis
-Year-wise movie release trends
-Interactive filters by year, title, and director

🔹 Files in this Repository
IMDB SQL TABLE ANALYSIS.docx – SQL queries and analysis
IMDb POWER-BI DASHBOARD.pbix – Power BI dashboard file

🔹 Key Learnings
- Practical SQL data analysis
- Power BI data cleaning using Power Query
- Creating interactive dashboards for business decision-making
- Translating raw data into actionable insights

🔹 SQL QUERIES OF PROJECT
#CHECKING REVENUE COLUMNS HAVING NULL OR EMPTY VALUES
SELECT COUNT(*) AS empty_revenue_rows FROM imdb_movie_data WHERE revenue_millions IS NULL OR TRIM(revenue_millions) = '';

#CHECKING METASCORE COLUMNS HAVING NULL OR EMPTY VALUES
SELECT COUNT(*) AS empty_metascore_rows FROM imdb_movie_data WHERE metascore IS NULL OR TRIM(metascore) = '';

#TOP 10 MOVIES BY THEIR RATINGS
SELECT title, MAX(rating) AS max_rating FROM `imdb_movie_data` GROUP BY title ORDER BY max_rating DESC LIMIT 0, 10;

#TOP 6 MOVIES BY THEIR REVENUE
SELECT title, MAX(revenue_millions) AS `revenue_millions` FROM `imdb_movie_data` GROUP BY title ORDER BY revenue_millions DESC LIMIT 0, 6;

#GENRE WISE MOVIES COUNT
SELECT TRIM(SUBSTRING_INDEX(genre, ',', 1)) AS main_genre, COUNT(*) AS total_movies FROM `imdb_movie_data` GROUP BY main_genre ORDER BY total_movies DESC;

#DIRECTOR NAME WHO RELEASES MOST
SELECT director, COUNT(director) AS director_count FROM `imdb_movie_data` GROUP BY director ORDER BY director_count DESC LIMIT 0, 10;

#TOP 10 MOVIES BY THEIR RUNTIME IN MINUTES
SELECT title, MAX(runtime_mi) AS max_runtime_mi FROM `imdb_movie_data` GROUP BY title ORDER BY max_runtime_mi DESC LIMIT 0, 10;

#TOP 10 ACTORS BY THEIR MOVIES COUNT
SELECT TRIM(SUBSTRING_INDEX(actors, ',', 1)) AS main_actors, COUNT(*) AS total_movies FROM `imdb_movie_data` GROUP BY main_actors ORDER BY total_movies DESC LIMIT 0 ,10;

#TOP 10 MOVIES WHO GOT MAX VOTES
SELECT title, MAX(votes) AS max_votes FROM `imdb_movie_data` GROUP BY title ORDER BY max_votes DESC;


🔹 Author
 Siddhartha Kulshreshtha Aspiring Data Analyst | Ex-PHP Developer
