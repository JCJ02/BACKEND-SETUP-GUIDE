# How to Setup Backend - Python (FastAPI)

Learn more about the following technologies:
- [Python](https://www.python.org/)
- [FastAPI](https://fastapi.tiangolo.com/)

## Get Started:
### Step 1: You have to download the latest version of Python!
- [Download the Latest Version of Python](https://www.python.org/downloads/)

### Step 2: Install it!

### Step 3: On Windows:
- Open the Start Menu and search for Environment Variables.
- Click on <strong>Edit the system environment variables</strong>.
- In the System Properties window, click on the <strong>Environment variables</strong> button.
- Under <strong>System Variables</strong>, find the `Path` variable and click <strong>Edit</strong>.
- Add the following path (replace `PhthonXX` with your Python version, e.g., `Python313`):

```console
C:\Users\<YourUsername>\AppData\Roaming\Python\PythonXX\Scripts\
```

- Click <strong>OK</strong> to save the changes.

## Create Project Directory
- Name it whatever you want, for ex. `fastapi`.
Organizing your project into a dedicated folder ensures all related files and configurations are in one place, making it easier to manage.

## Virtual Environments (Recommended):

It is highly recommended to create a virtual environment for your project. This isolates the project dependencies and prevents conflicts with other Python projects.

1.  Create a virtual environment:

    ```console
    python -m venv venv
    ```

2.  Activate the virtual environment:

    * **On Windows:**

        ```console
        . venv/Scripts/activate
        ```

    * **On macOS and Linux:**

        ```console
        source venv/bin/activate
        ```

    * **Important:** Make sure your terminal prompt shows `(venv)` before proceeding.

3.  Install the required packages within the activated virtual environment:

    ```console
    pip install "fastapi[standard]" uvicorn alembic python-dotenv psycopg-binary psycopg sqlalchemy pydantic pydantic-settings passlib bcrypt python-jose[cryptography] python-multipart
    ```
    - `fastapi[standard]` - FastAPI is a modern, fast (high-performance) web framework for building APIs with Python. It's built on top of Starlette and Pydantic. The [standard] part installs FastAPI along with some useful dependencies like uvicorn (ASGI server) and python-multipart (for handling file uploads).
    - `uvicorn` - Uvicorn is an ASGI server implementation used to serve FastAPI applications. It is known for its speed and asynchronous nature, making it well-suited for handling multiple requests concurrently.
    - `alembic` - Alembic provides for the creation, management, and invocation of change management scripts for a relational database, using SQLAlchemy as the underlying engine.
    - `python-dotenv` - For managing environment variables.
    - `psycopg-binary` or `asyncpg` - PostgreSQL database drivers.
    - `psycopg` - psycopg is a PostgreSQL database adapter for Python, similar to psycopg-binary.
    - `sqlalchemy` - SQL toolkit and ORM.
    - `pydantic` - Data validation and settings management.
    - `pydantic-settings` - pydantic-settings is an extension of Pydantic that provides support for managing application settings.
    - `passlib` - Password hashing.
    - `bcrypt` - Password hashing algorithm.
    - `pyjwt` - Refers to the PyJWT library — a module that lets you create, decode, and verify JSON Web Tokens (JWTs).
    - `python-multipart` - is a library used to parse multipart/form-data in Python web frameworks like FastAPI and Starlette.

4. Initialize Alembic - The install will add the alembic command to the virtual environment. All operations with Alembic in terms of this specific virtual environment will then proceed through the usage of this command, as in:

    ```console
    alembic init alembic
    ```
    - You can now generate tables in the alembic by typing this command:
    ```console
    alembic revision --autogenerate -m "Added tables"
    ```
    and then,
    ```console
    alembic upgrade head
    ```

5. Create a requirements file.

    ```console
    pip freeze > requirements.txt
    ```
    or
    ```console
    pip install -r requirements.txt # If you want to auto reinstall the requirements.txt
    ```
