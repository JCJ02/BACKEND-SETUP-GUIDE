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
