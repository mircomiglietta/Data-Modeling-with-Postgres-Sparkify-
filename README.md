### Udacity Data Engineer Nanodegree project
Sparkify a music app, wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis. The task is to create a star schema for Postgres and develop an ETL pipleine which will transfer the data from local files to the database.


### Project structure explanation
```
The project conteins sql_queries.py , create_tables.py, etl.py, etl.ipynb and test.ipynb

In addition to the data files, the project workspace includes six files:

1. test.ipynb displays the first few rows of each table to let you check your database.
2. create_tables.py drops and creates your tables. You run this file to reset your tables before each time you run your ETL scripts.
3. etl.ipynb reads and processes a single file from song_data and log_data and loads the data into your tables. This notebook contains detailed instructions on the ETL process for each of the tables.
4. etl.py reads and processes files from song_data and log_data and loads them into your tables. You can fill this out based on your work in the ETL notebook.
5. sql_queries.py contains all your sql queries, and is imported into the last three files above.
6. README.md provides discussion on your project.



To run the project the firt file to run is sql_queries.py then create_tables.py anfd the last one is  etl.py. 


```

### Instructions for running locally


Run scripts
```
python ./sql_queries.py     # create and drop queries
python ./create_tables.py   # create schema
python ./etl.py             # option 1: load data one file per commit

```
### Structure of ETL
```
Fact Table

1. songplays - records in log data associated with song plays i.e. records with page NextSong
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

Dimension Tables

1. users - users in the app
user_id, first_name, last_name, gender, level

2. songs - songs in music database
song_id, title, artist_id, year, duration

3. artists - artists in music database
artist_id, name, location, latitude, longitude

4. time - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday
```

![Image of ETL](https://r766469c826263xjupyterllyjhwqkl.udacity-student-workspaces.com/lab/tree/Song_ERD.png)
