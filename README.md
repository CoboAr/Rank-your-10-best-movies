# Rank your 10 best movies

## Requirements  

On the integrated terminal on Pycharm run:

On Windows type:      
python -m pip install -r requirements.txt      

On MacOS type:       
pip3 install -r requirements.txt         

This will install the packages from requirements.txt for this project.

## What is Rank your 10 best movies website?

It is a website built with Flask/WTForms/SQLite/SQLAlchemy and more that allows the user to list his favourite movies of all time. As the user watches more movies it can update his list of movies and keep track of which movies to recommend people.   

## How does it work?  

First, the program should run locally, and then it can be deployed. When the program is running:   
1) The user should be able to view Movie Lists Items.    
In order to achieve this, a SQLite database with SQLAlchemy it has been created. The table contains the following fields:    

<img width="164" alt="Screenshot 2024-01-05 at 11 43 39 AM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/6c54fdad-6c38-45e5-aaff-eb9679f7bbd5">  </br>

<img width="373" alt="Screenshot 2024-01-05 at 11 46 11 AM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/4d23d770-64b2-4ada-8794-242e3da331df">    

2) The user should be Able to Edit a Movie's Rating and Review.

https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/37f7bba8-c6e0-4504-b9fe-d04644bddc9b

   
4) The user should be Able to Delete a Movie from the Database.


https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/ba2787f8-738c-4891-ad8c-6d9679831fb1


5) The user should be Able to Add New Movies Via the Add Page.

When the user types a movie title and clicks "Add Movie", the Flask server should receive the movie title. Next, the requests library is used to make a request and search The Movie Database API for all the movies that match that title.

The user needs to sign up for a free account on The Movie Database https://www.themoviedb.org/ .

Then the user will need to go to Settings -> API and get an API Key. Fill out their form, get the API key, and then copy that API key into your project.

<img width="524" alt="Screenshot 2024-01-05 at 12 32 13 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/1fe99682-3379-4cf0-a432-882b7c8c63e3">


https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/af631f4a-14d2-4641-82f1-dadc6dbbfc3b

## Deployment

To deploy this website I have used [Render](https://render.com/). It has a free tier which will be more than enough for demonstration purposes.  

<uL>
<li>
  Step 1. Setup a WSGI server with gunicorn (gunicorn is added to the requirement.txt file).    
</li>
<li>
Step 2. Create a Procfile    
Add the following into the Procfile:       
web: gunicorn main:app   
</li>
<li>
Step 3. Create a git github repository and push the local project into the remote repository.   
</li>
<li>
Step 4. Sign up to https://render.com/ and create your web service.  
</li>
  
<img width="307" alt="Screenshot 2024-01-05 at 12 52 12 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/0e7d6947-bd7a-48d3-8b8a-e097f0d89b73"> 

<img width="489" alt="Screenshot 2024-01-05 at 12 53 58 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/83aef18b-2e48-440b-8141-a05683934d71">

Choose your blog app that you've uploaded to GitHub and connect your repo.    

<img width="1355" alt="Screenshot 2024-01-05 at 12 56 55 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/2db180b1-1b2d-4d70-9d15-a5b16a322618">


Edit the Start Command to:

gunicorn main:app

<img width="1434" alt="Screenshot 2024-01-05 at 12 58 36 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/cdb616ec-6245-4198-b1e0-5db4eb2b4f05">


Add Environment variables MOVIE_DB_API_KEY, FLASK_KEY, DB_URI:

<img width="1248" alt="Screenshot 2024-01-05 at 1 00 55 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/48088540-85e2-4b71-91e4-44a48dc2cd7f"> 
<img width="1043" alt="Screenshot 2024-01-05 at 1 01 55 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/827158d9-8a3f-4479-a054-3a5d8af1d536">


Scroll to the bottom and create your web service.

<li>
Step 5. Upgrade SQLite Database to PostgreSQL
</li>
<ul>
  <li>
    Create a new Postgres Database
  </li>
  <li>
    Pick a name for the database and create it.
  </li>
  <li>
    Copy the internal database URL
  </li>
  <img width="547" alt="Screenshot 2024-01-05 at 1 08 58 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/b91129b1-ae41-4d4a-9273-52170bdc0876">
<li>
  Set your SQLALCHEMY_DATABASE_URI environment variable   
  Go back to  web service settings called "environment".  Create an environment variable that matches the name of the key you're using in the main.py.    
  
</li>
<img width="561" alt="Screenshot 2024-01-05 at 1 11 01 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/0afb11ba-eb9f-4964-b65a-104c2476a37c">
<li>
  Paste  internal database URL as the key value. It should look something like this
</li>

<img width="574" alt="Screenshot 2024-01-05 at 1 12 21 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/af2a061a-55a7-42d0-9368-2111dcfccb90">

<li>
  Change the first part from postgres to postgresql. The URI has to start with "postgresql" because this is required by SQLAlchemy:
</li>
<img width="564" alt="Screenshot 2024-01-05 at 1 13 15 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/20fefaf7-f96d-44c7-9a61-e0de620603a4">

<img width="760" alt="Screenshot 2024-01-05 at 1 32 10 PM" src="https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/ca7c107d-0752-478b-ad49-a64b857e2695">

</ul>
</uL>

## Demo
Website link: https://top-10-movies.onrender.com    
Domain can be customized upon desire.


https://github.com/CoboAr/Rank-your-10-best-movies/assets/144629565/d58bd0c9-d9c4-427b-8ac6-03c213eac6aa



Enjoy! And please do let me know if you have any comments, constructive criticism, and/or bug reports.
## Author
## Arnold Cobo











