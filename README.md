# Olympic-Games-Database-SQL-vs-NoSQL
In this GitHub repo, you find my work to one of my Data Science Master's Courses, **Data Management for Data Science**. I did a deep analaysis through answering 5 questions (Easy to complicated) of the Olympic events and competitors database. This work is composed of three main parts to showcase the pros and cons of SQL Vs. NoSQL on the same database:
1. Answering the five question using SQL (MySQL).
2. Optimizing the implementation of MySQL queries to boost the performance of execution time.
3. Converting the database into **NoSQL** (MongoDB), answering the same questions, and comparing the execution time of SQL vs NoSQL implementations.

## Database Intro
It contains about 260,000 separate results for competitors at all events since 1896 until 2016, including both summer and winter Olympics. It has all the results: not only the medals but those who competed and did not win a medal. All events for each sport are included. 

Here's the original [database](https://dbshostedfiles.s3-us-west-2.amazonaws.com/dbs/sampledata/olympics/sample_data_olympics_mysql.sql) sql file, and here's the original ERD of the database.

<p align="center">
  <img src="https://www.databasestar.com/wp-content/uploads/2019/12/olympics_erd.png"
       alt="ERD from the Original Source" width="800" height = "400" />
</p>

## Table Explanations
1. Sport
    * This table contains a list of all sports in the Olympics: both summer sports and winter sports.

2. Event
    * The event table contains all of the different events for each sport. For example, if a sport is “Alpine Skiing”, then an event is “1KM Men’s Alpine Skiing”. There are multiple events per sport, and events are split into Men, Women, and Mixed.

3. City
    * This represents a list of many of the cities in the world.

4. Games
    * The games table lists all of the Olympic Games since 1896m, the year they were held, and whether they were Summer or Olympic games.

5. Games City
    * This table shows all of the cities for each Olympic games. This is a joining table between games and city.

6. NOC Region
    * This contains a list of NOC (National Olympic Committee) codes and their names. This translates roughly to a country that competes in the Olympics.

7. Person
    * This table lists all people that have competed in an Olympic games. It has their name, gender, height (in CM) and weight (in KG). The height and weight did not differ between Olympic games. If it did, it would have been stored in a different table.

8. Person Region
    * This is a joining table that lists all people and the NOC regions (countries) they competed for. This captures the fact that some people competed for more than one country, which is another scenario I didn’t realise until I looked at the data.

9. Games Competitor
    * This table is a joining table that relates a person to an Olympic games, which shows who competed what each Olympic games.

10. Medal
    * This small table lists the different medals available: Gold, Silver, Bronze, and N/A.

11. Competitor Event
    * This table lists the combination of competitors (the people and the games they competed in), the event they competed in, and the medal (if any) they received. This is the largest table.
