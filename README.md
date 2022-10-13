# Sparkify

Sparkify is one of the projects in the Data Engineering nanodegree program at Udacity. Sparkify is a music streaming app. The main goal of the project is to analyze data collected about songs and user activity on the app to understand what songs users are listening to. 

The role of the data engineer is to create a Postgres database schema and ETL pipeline for this analysis and then test the database and ETL pipeline by executing queries given by Sparkify's analytics team and comparing the results with the expected results.

# Database schema:

The data resides in JSON files in two major datasets:

1- Song dataset: contains metadata about a song and the artist of that song.
2- Log dataset: these simulate activity logs from a music streaming app based on specified configurations.

They are nested in subdirectories under /data/song_data and /data/log_data.

Using the song and log datasets, a star schema optimized for queries on song play analysis. This includes the following tables.

 1- Fact table called (songplays) 
 records in log data associated with song plays and records "songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent"


 2- Four dimension tables called (users, songs, artists and time.)
 2.1- users: users in the app and contains "user_id, first_name, last_name, gender, level"
 2.2 - songs: songs in music database and contains "song_id, title, artist_id, year, duration"
 2.3- artists: artists in music database and contains "artist_id, name, location, latitude, longitude"
 2.4- time:time - timestamps of records in songplays broken down into specific unitsand contains "start_time, hour, day, week, month, year, weekday"

 
 # The files in the repository:
 
1- create_tables.py: drops and creates the tablesa and to reset the tables before each time you run ETL scripts.
2- test.ipynb: displays the first few rows of each table to let you check your database.
               It has also Sanity Tests section. The cells contain some basic tests that will evaluate the code and catch any common mistakes. 
3- etl.ipynb: reads and processes a single file from song_data and log_data and loads the data into the tables. 
4- etl.py: reads and processes files from song_data and log_data and loads them into the tables. 
5- sql_queries.py: contains all the sql queries.
6- README.md: provides discussion on the project.
7- run.ipynb: to run easily the create_tables.py and etl.py

# Running Scripts:

Requirements
1- python: pandas library
2- Postgresql

Run the create_tables.py script from run.ipynb file to create the database and the tables.
Run test.ipynb to confirm the creation of the tables with the correct columns. Make sure to click "Restart kernel" to close the connection to the database after running this notebook.
Run test.ipynb tb to confirm that records were successfully inserted into each table. Remember to rerun create_tables.py to reset the tables before each time you run this notebook.
run etl.py from run.ipynb to reset the tables, but remember to run create_tables.py before it, then run test.ipynb to confirm the records were successfully inserted into each table.





























