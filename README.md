# Data-Modeling-with-Cassandra<h2>Introduction</h2>
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. <strong>This project creates Apache Cassandra database which can create queries on song play data to answer the questions raised by Sparkify team.</strong>

-----------------------------------------
<h2>Database Design with Apache Cassandra</h2>
<h4>The tables are modeled for the queries/questions that need answers. The answers shown below are derived from the event_data directory</h4>
<ol>
<li> Question 1: Give me the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession = 4</li>
<ul>
<li> Data Modling: artist, song, length, sessionid, iteminsession, PRIMARY KEY (sessionid, iteminsession)</li>
<li> Answer: Faithless Music Matters (Mark Knight Dub) 495.30731201171875 </li>
</ul>
  <br/>
<li> Question 2: Give me only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182</li>
<ul>
<li> Data Modling: artist, song, firstname, lastname, userid, sessionid, iteminsession, PRIMARY KEY (userid, sessionid, iteminsession)</li>
<li> Answer: <br/>Down To The Bone Keep On Keepin' On Sylvie Cruz<br/>
Three Drives Greece 2000 Sylvie Cruz<br/>
TSebastien Tellier Kilometer Sylvie Cruz<br/>
Lonnie Gordon Catch You Baby (Steve Pitron & Max Sanna Radio Edit) Sylvie Cruz</li>
</ul>
  <br/>
<li> Question 3: Give me every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'</li>
<ul>
<li> Data Modeling:firstname, lastname, userid, song, PRIMARY KEY (song, userid)</li>
<li> Answer: <br/>Jacqueline Lynch<br/>
Tegan Levine<br/>
Sara Johnson</li>
</ul>
</ol>

---------------------------------

<h2>ETL Pipeline</h2>
The project is working with the directory event_data, which is composed by CSV files partitioned by date. The first part of the Jupyter Notebook is to iterate through each event file in event_data to process and create a new CSV file (event_datafile_new.csv). The second part of the Notebook is to model NoSQL database according to queries, create tables, and insert processed records from event_datafile_new.csv into relevant tables. 

---------------------------------

<h2>Running Instruction</h2>
Run Project_1B_ Project_Template.ipynb to see the whole process<br/>
NOTE: Please do not open any file in the event_data directory before running the notebook, otherwise the checkpoints files would be created which could result in incomplete event_datafile_new.csv
