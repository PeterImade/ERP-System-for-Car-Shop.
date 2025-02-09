# A Car Shop ERP System

![coverage](https://img.shields.io/badge/coverage-93%25-darkgreen)

This REST API serves as an ERP system for a car shop.


# Technologies Used
- **FastAPI**: Web framework for building APIs
- **Uvicorn**: ASGI server for FastAPI
- **SQLAlchemy**: ORM for database management
- **Psycopg2**: PostgreSQL adapter for Python
- **PyJWT**: JSON Web Token implementation for authentication
- **Pydantic**: Data validation and parsing
- **Starlette**: Web framework for building APIs (FastAPI dependency)
- **pytest**: Testing framework for Python
- **requests**: HTTP library for making requests
- **coverage**: Code coverage tool


## Requirements

Ensure you have the following installed:

- [Python 3.6+](https://www.python.org/downloads/)
- [Virtual Environments with Python 3.6+](https://docs.python.org/3/tutorial/venv.html)
- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)

___

## Setup Project

1. **Create a virtual environment:**
    ```bash
    python3 -m venv env
    ```

2. **Activate the virtual environment:**
    ```bash
    source env/bin/activate
    ```

3. **Install app dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
___

## Running the Application

1. **Start the database (PostgreSQL:alpine3.14):**
    ```bash
    docker-compose up
    ```

2. **Start the application:**
    ```bash
    uvicorn app.main:app --reload
    ```

### Note:
You can configure the database using an environment variable:

```bash
export DB_URL="postgresql://user-name:password@host-name/database-name"
```

## Accessing the Application Locally
- The application will be available at: [http://127.0.0.1:8000](http://127.0.0.1:8000)
- Swagger Documentation: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
- Redoc Documentation: [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc) 

If required, add the following headers for authentication on routes:
- `token`: my-jwt-token
- `x_token`: fake-super-secret-token

## Testing

- **Run tests:**
    ```bash
    pytest
    ```

- **Run tests with coverage report:**
    ```bash
    pytest --cov=app app/test/
    ```

___

## Development

To update dependencies in `requirements.txt`:

1. Remove the version constraint for `dataclasses`.
2. Run:
    ```bash
    pip freeze > requirements.txt
    ```

___

## Deploy on Heroku

### Requirements

- [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

### Install Heroku CLI

```bash
sudo snap install --classic heroku
```

### Deployment

If automatic deploy is enabled for the `master` branch, simply commit to the `master` branch. Otherwise, deploy manually
using the Heroku CLI as follows:

```bash
heroku login
heroku git:remote -a car-shop-fastapi
git add .
git commit -m "Deploy on Heroku"
git push origin master
git push heroku master
```

___

## Source Documentation

- [FastAPI](https://fastapi.tiangolo.com/)
- [Bigger Application](https://fastapi.tiangolo.com/tutorial/bigger-applications/)
- [SQL Databases](https://fastapi.tiangolo.com/tutorial/sql-databases/)
- [Testing](https://fastapi.tiangolo.com/tutorial/testing/)
- [Pydantic](https://pydantic-docs.helpmanual.io/)
- [SQLAlchemy by FastAPI](https://fastapi.tiangolo.com/tutorial/sql-databases/#sql-relational-databases)
- [SQLAlchemy 1.4](https://docs.sqlalchemy.org/en/14/tutorial/engine.html) 