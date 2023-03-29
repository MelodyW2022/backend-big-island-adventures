# backend-big-island-adventures-backend
## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Back-End Layer Setup](#setup)

## General info
Big Island Adventures is a web application built using Python, Flask, React, React-Bootstrap, React Router DOM, HTML, CSS, Javascript, and PostgreSQL. 
It uses the AccuWeather API to provide users with tour suggestions based on the weather condition of the selected location in Big Island Hawaii. 
The app features CRUD operations and registration, login, and logout functionalities for users. 
Users can book tours and view them in their dashboard. The app's highlight is its ability to provide personalized tour suggestions based on the weather condition of the user's selected location. 
The app is hosted on Heroku.
	
## Technologies
Python, Flask, React, React-Bootstrap, React Router DOM, HTML, CSS, Javascript, and PostgreSQL. 
	
## Back-End Layer Setup

Feel free to follow these steps on one machine in this order exactly.

<details>

<summary>Click here to expand back-end layer setup steps.</summary>

### Clone

Clone the forked repo. Do _not_ clone this inside of another project folder, because that will cause issues.

### Managing Dependencies

Create a virtual environment:

```bash
$ python3 -m venv venv
$ source venv/bin/activate
(venv) $ # You're in activated virtual environment!
```

Install dependencies (we've already gathered them all into a `requirements.txt` file):

```bash
(venv) $ pip install -r requirements.txt
```

### Setting Up The Database

Create a database named `touring_api_development`.

### Creating a `.env` File

Create a file named `.env`.

Add this environment variable: `FLASK_ENV=development`

Also, add the environment variable `SQLALCHEMY_DATABASE_URI` to hold the path to your development database.

Your `.env` may look like this:

```
FLASK_ENV=development
SQLALCHEMY_DATABASE_URI=postgresql+psycopg2://postgres:postgres@localhost:5432/touring_api_development
```

### Create Models

Recall that we can update our models any time. These steps are to initialize our database:

1. Run `flask db init` (Do this before making the model files.)
1. Create the model files for them
1. Update `app/__init__.py` to import the three models into `create_app`
1. Run `flask db migrate -m ""`
1. Run `flask db upgrade`

### Run `$ flask run` or `$ FLASK_ENV=development flask run`

Check that your Flask server can run with `$ flask run`.

The environment variable in the `.env` file, `FLASK_ENV`, will automatically enable development mode. This enables hot-reloading, which is a feature that refreshes the Flask server every time there is a detected change.

Alternatively, if our environment variable `FLASK_ENV` is not enabling development mode, we can manually set it with `$ FLASK_ENV=development flask run`.

**It is highly recommended to run the Flask servers in development mode**.

### Commit and Push

Commit and push your files to your repo, especially including the migration files!

</details>
