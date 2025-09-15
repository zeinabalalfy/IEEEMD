IEEEMDB Project
What is this?
IEEEMDB is a movie app where users can find movies, add reviews, make lists, and get notifications. This repo has the design and a simple code to show how it works. It’s made for a contest.
Features

Users can sign up and log in.
Search movies by name or type.
Add ratings and reviews to movies.
Make lists like "Best Action Movies".
Get movie recommendations.
Get notifications for new movies.

Data Model
We use two databases:

PostgreSQL for users, reviews, lists, notifications (keeps things safe).
MongoDB for movies and recommendations (easy to add stuff).

Tables:

Users: id, username, email, password, watch_history (json), created_at.
Movies: id, title, description, cast, genre, tags, rating_avg, created_at.
Reviews: id, user_id, movie_id, rating, comment, likes (json), created_at.
Recommendations: id, user_id, movies (json with movie_id and score), created_at.
Notifications: id, user_id, message, type, is_read, sent_at.

Diagram is in docs/ieee.excalidraw (shows users, movies, and some links like "write").

How it Works

Users box (rectangle) connects to Reviews and Lists (1 to many).
Movies box connects to Reviews (many to one).
Recommendations and Notifications are boxes too, linked to Users.
Diagram has circles for fields like id and lines for links.


Setup

Clone repo.
Run pip install flask.
Start: python src/app.py.
Try APIs in Postman.

No caching (should use Redis).

This is a basic design, needs more work for big users.
