# Coffee Shop Backend

## Getting Started

### Installing Dependencies

#### Python 3.7

Follow instructions to install the latest version of python for your platform in the [python docs](https://docs.python.org/3/using/unix.html#getting-and-installing-the-latest-version-of-python)

#### Virtual Environment

We recommend working within a virtual environment whenever using Python for projects. This keeps your dependencies for each project separate and organized. Instructions for setting up a virtual environment for your platform can be found in the [python docs](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)

#### PIP Dependencies

Once you have your virtual environment setup and running, install dependencies by naviging to the `/backend` directory and running:

```bash
pip install -r requirements.txt
```

This will install all of the required packages we selected within the `requirements.txt` file.

##### Key Dependencies

- [Flask](http://flask.pocoo.org/) is a lightweight backend microservices framework. Flask is required to handle requests and responses.

- [SQLAlchemy](https://www.sqlalchemy.org/) and [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/2.x/) are libraries to handle the lightweight sqlite database. Since we want you to focus on auth, we handle the heavy lift for you in `./src/database/models.py`. We recommend skimming this code first so you know how to interface with the Drink model.

- [jose](https://python-jose.readthedocs.io/en/latest/) JavaScript Object Signing and Encryption for JWTs. Useful for encoding, decoding, and verifying JWTS.

## Running the server

From within the `./src` directory first ensure you are working using your created virtual environment.

Each time you open a new terminal session, run:

```bash
export FLASK_APP=api.py;
```

To run the server, execute:

```bash
flask run --reload
```

The `--reload` flag will detect file changes and restart the server automatically.

## Tasks

### Setup Auth0

1. Create a new Auth0 Account
2. Select a unique tenant domain
3. Create a new, single page web application
4. Create a new API
   - in API Settings:
     - Enable RBAC
     - Enable Add Permissions in the Access Token
5. Create new API permissions:
   - `get:drinks`
   - `get:drinks-detail`
   - `post:drinks`
   - `patch:drinks`
   - `delete:drinks`
6. Create new roles for:
   - Barista
     - can `get:drinks-detail`
     - can `get:drinks`
   - Manager
     - can perform all actions
7. Test your endpoints with [Postman](https://getpostman.com).
   - Register 2 users - assign the Barista role to one and Manager role to the other.
   - Sign into each account and make note of the JWT.
   - Import the postman collection `./starter_code/backend/udacity-fsnd-udaspicelatte.postman_collection.json`
   - Right-clicking the collection folder for barista and manager, navigate to the authorization tab, and including the JWT in the token field (you should have noted these JWTs).
   - Run the collection and correct any errors.
   - Export the collection overwriting the one we've included so that we have your proper JWTs during review!

### Implement The Server

There are `@TODO` comments throughout the `./backend/src`. We recommend tackling the files in order and from top to bottom:

1. `./src/auth/auth.py`
2. `./src/api.py`

https://richboi.us.auth0.com/authorize?audience=Coffee&response_type=token&client_id=&redirect_uri=https://127.0.0.1:8080

<!-- richesmetelewawon ====eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IjNqRFNWNXpNNndlMW1aZ2l0NW5DdyJ9.eyJpc3MiOiJodHRwczovL3JpY2hib2kudXMuYXV0aDAuY29tLyIsInN1YiI6ImF1dGgwfDYyYzAzNmNmNDkyYzlhNWExOTEyODI3NyIsImF1ZCI6IkNvZmZlZSIsImlhdCI6MTY1NzI4NzA1MCwiZXhwIjoxNjU3Mjk0MjUwLCJhenAiOiJGeHN3b20wNnQ2TmZpQ0RhTkw0YTIwOHZNNVN0N083RyIsInNjb3BlIjoiIiwicGVybWlzc2lvbnMiOlsiZGVsZXRlOmRyaW5rcyIsImdldDpkcmlua3MiLCJnZXQ6ZHJpbmtzLWRldGFpbCIsInBhdGNoOmRyaW5rcyIsInBvc3Q6ZHJpbmtzIl19.ePZMYs13RIcHgd1OhNW9HBsNz7HpdUCOq8AA2B1slEpE6AielgFMX4MduFKVCLL_GwutJvfatUEWnkjb6Y-iOR_PQCr4D-05nF-F9i3-qMFX6hDKAHEAKPa4CzSgzld7QKG2Acc7VV5FIFReQbZvbx8Gr9avIED6q5O9qx7vAU75Obs-bBdJ9dldesQ90QF4AIjuuu1kTvgJdV2hanTOHfMTDOMF3IMZLOdGeQ4ZzMJnpXQB0mvbm7CV3hrIMPoTqdx23LMFmFZjIjZKUbAQ1RI31zvrQQcJoSw9_7V-i9Om_DmD8HXqyRBv9CeJABlnu1SbDmQy_9h1g4_rmcdx5A

riches2cute==
