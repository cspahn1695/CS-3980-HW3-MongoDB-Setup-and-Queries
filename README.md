# CS-3980-HW3-MongoDB-Setup-and-Queries

For this assignment, I was required to connect MongoDB atlas to MongoDB compass and run queries in compass. 

for the first query, I had to find all movies with runtime greater than 200 minutes in year 1983. The result should include a list of objects sorted by increasing runtime, and each object only has 3 fields: runtime, title, and year. The appropriate query to achieve this is as follows:

db.movies.find(
  {
    year: 1983,
    runtime: { $gt: 200 }
  },
  {
    _id: 0,
    runtime: 1,
    title: 1,
    year: 1
  }
).sort({ runtime: 1 })

The results from running this query are shown in the screenshot below.

<img width="1205" height="635" alt="image" src="https://github.com/user-attachments/assets/f6928b3a-cf1f-476c-af3f-00322fd609df" />


For the second query, I had to find all movies after year 2014 with an imdb rating greater than 9. The appropriate query to achieve this is as follows:

db.movies.find( { 'year': { $gt: 2014}, 'imdb.rating': { $gt: 9}}, {'_id': 0, 'title': 1, 'year': 1, 'imdb.rating': 1})

The results from running this query are shown in the screenshot below.

<img width="1231" height="462" alt="image" src="https://github.com/user-attachments/assets/26ceeb85-4a4d-4bd2-9d63-76d3575ee944" />


Below is the MongoDB compass sample_mflix movies database, which is the database on which queries were made for this assignment. 
<img width="1903" height="1057" alt="image" src="https://github.com/user-attachments/assets/e71e505a-72a6-4f96-93b4-6a08ad5eba33" />

Below is the MongoDB atlas sample_mflix movies database, which is the database on which queries were made for this assignment. 
<img width="1910" height="1020" alt="image" src="https://github.com/user-attachments/assets/725ddb53-3232-4911-bd90-a955f529ebea" />

Below is the project overview for this assignment. All the database collections are part of cluster0. I (the admin) am the only user, and a connection string links it to the MongoDB compass database. The sample_mflix database is part of cluster0, and sample_mflix includes comments, embedded_movies, movies, sessions, theaters, and users.
<img width="1917" height="1022" alt="image" src="https://github.com/user-attachments/assets/eec8c280-3ccd-4f57-a4d4-43de32cc319f" />

-----
