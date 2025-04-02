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

## Open it on Visual Studio Code Software
- Open your terminal and type `pip install "fastapi[standard]` and `pip install uvicorn` to initialize the package.json file:
```console
pip install "fastapi[standard]"
pip install uvicorn
```

## Virtual Environments (Recommended):

It is highly recommended to create a virtual environment for your project. This isolates the project dependencies and prevents conflicts with other Python projects.

1.  Create a virtual environment:

    ```console
    python -m venv venv
    ```

2.  Activate the virtual environment:

    * **On Windows:**

        ```console
        . venv\Scripts\activate
        ```

    * **On macOS and Linux:**

        ```console
        source venv/bin/activate
        ```

    * **Important:** Make sure your terminal prompt shows `(venv)` before proceeding.

3.  Install the required packages within the activated virtual environment:

    ```console
    pip install alembic python-dotenv psycopg2-binary asyncpg sqlalchemy pydantic pydantic-settings passlib bcrypt
    ```
    `alembic` - Alembic provides for the creation, management, and invocation of change management scripts for a relational database, using SQLAlchemy as the underlying engine.
    `python-dotenv` - For managing environment variables.
    `psycopg2-binary` or `asyncpg` - PostgreSQL database drivers.
    `sqlalchemy` - SQL toolkit and ORM.
    `pydantic` - Data validation and settings management.
    `passlib` - Password hashing.
    `bcrypt` - Password hashing algorithm.

4. Initialize Alembic - The install will add the alembic command to the virtual environment. All operations with Alembic in terms of this specific virtual environment will then proceed through the usage of this command, as in:

    ```console
    pip install alembic
    ```

5. Create a requirements file.

    ```console
    pip freeze > requirements.txt
    ```
