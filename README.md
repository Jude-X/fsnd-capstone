# Solution to Code Test from Savvyng for the role of a FullStack Developer

This project is a basic Flask RESTful API Application that can verify JWT Tokens for user authentication and interacts with a PostgreSQL database using SQLAlchemy ORM.

## Application Heroku Link

**https://savvyng-test.herokuapp.com/**

## Application Stack

The Application Tech Stack includes:
- **Python3**: The [server language](https://www.python.org/downloads/)
- **Flask**: [Server Framework](https://flask.palletsprojects.com/en/1.1.x/)
- **PostgreSQL**: [Database](https://www.postgresql.org/) of choice
- **SQLAlchemy**: [ORM of choice](https://www.sqlalchemy.org/) to communicate between the python server and the Postgres Database. [Flask SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/2.x/) is directly used.
- **Heroku**: [Deployment Platform](https://www.heroku.com/)

## Working with the application locally
Make sure you have [Python](https://www.python.org/downloads/) installed.

1. **Clone the Repository**
    ```bash
    git clone -b master https://github.com/cynepton/savvyng-test.git
    ```

2. **Set up a virtual environment**:
    ```bash
    virtualenv env
    source env/Scripts/activate # for windows
    source env/bin/activate # for MacOs
    ```

3. **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Export Environment Variables**
    Refer to the `setup.sh` shell file and export the environment variables for the project.

5. **Create Local Database**:
    Create a local database and export the database URI as an environment variable with the key `DATABASE_PATH`.

6. **Run Database Migrations**:
    ```bash
    python manage.py db migrate
    python manage.py db upgrade
    ```

7. **Run the Flask Application locally**:
    ```bash
    export FLASK_APP=myapp
    export FLASK_ENV=development
    flask run
    ```

## Endpoints
The Host for the endpoints is:
`https://savvyng-test.herokuapp.com/`

OR
`https://localhost:5000/` if the flask app is being run locally.

### Index `/`

The index endpoint that indicates the Flask Application is running normally.<br>
**Response**:<br>
- Type: String
- Body:
    `SavvyNg Code Test by Isaac Aderonmu`

### Auth `/auth`

Returns the authorize URL that redirects to the Auth0 login page.<br>
**Response**:<br>
- Type: JSON
- Body:
    ```json
    {
        "url":"https://udacity-fsnd-capstone.us.auth0.com/authorize?audience=casting_agency&response_type=token&client_id=eDxU1gLQJog9fqRGBY7kR3dO7L23QZYB&redirect_uri=https://fsnd-capstone-cynepton.herokuapp.com/"
    }
    ```
