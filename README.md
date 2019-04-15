# Data Modeling with Cassandra
The purpose of this project is to create a database in Apache Cassandra for maintaining songs and user activity. This will allow analysts to generate insights from user listening patterns. ETL is performed to load data from user logs into the database to enable easy querying.

## Dependencies
* Pandas
* Cassandra
* Glob
* Numpy

## Input Data
Input data in `/event_data/` is partitioned by date and contains the fields: 
```javascript
{artist,auth,firstName,lastName,gender,itemInSession,length,level,location,method,page,registration,sessionId,song}
```
## Data Queries
The design of the database is optimized to answer the following queries:
1. Given the sessionId and itemInSession, return artists name, song title and song length from the user activity data
2. Given userId and sessionId, return the name of the artist, song title (sorted by itemInSession) and user(firstName and lastName)
3. Given the song title, return each user (first and last name) in the music app history who listened to that song

## Database Design
* To view the database design and run this solution, please review the **Cassandra_DataWarehouse.ipynb** notebook
