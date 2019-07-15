# Data-Modeling-with-Cassandra<h2>Introduction</h2>
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. <strong>This project creates Apache Cassandra database which can create queries on song play data to answer the questions raised by Sparkify team.</strong>

-----------------------------------------
<h2>Database Design with Apache Cassandra</h2>
<h4>The tables are modeled for the queries/questions that need answers</h4>
<ol>
<li> Question 1: Give me the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession = 4</li>
<ul>
<li> artist, song, length, sessionid, iteminsession, PRIMARY KEY (sessionid, iteminsession)</li>
</ul>
<li> Question 2: Give me only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182</li>
<ul>
<li> artist, song, firstname, lastname, userid, sessionid, iteminsession, PRIMARY KEY (userid, sessionid, iteminsession)</li>
</ul>
<li> Question 3: Give me every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'</li>
<ul>
<li> firstname, lastname, userid, song, PRIMARY KEY (song, userid)</li>
</ul>
</ol>
