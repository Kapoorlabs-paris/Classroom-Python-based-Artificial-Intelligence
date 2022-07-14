# Classroom-Introduction-to-Python-based-Artificial-Intelligence
Coursework material for [introduction-to-python-with-artificial-intelligence](https://kapoorlabs.org/product/introduction-to-python-with-artificial-intelligence/)

## Python for developers
### How to make a python project with setup.py and Pipenv
Let's create a project that you want to deploy via Pypi. 

Name of the project: goodplaceintroduction 

We begin by making a github repository for it and then create a folder with the same name as the project name. [How to create a python package](https://github.com/Kapoorlabs-paris/goodplaceintroduction)

Step 1) Create a setup.py file: this file contains all the required dependencies of the current python package needed for it to run, author name and contact, python interpretor and the version of the package

Step 2) Inside the goodplaceintroduction folder create a `__init__.py` and `_version.py` files. The `_version.py` contains a single line defination of the version of the code and the `__init_.py` file imports this version file allowing the setup.py file to grab the version of the library. This allows users to import your package and ask for its version using `print(goodplaceintroduction.__version__)` command.

Step 3) Install pipenv using pip command `pip install pipenv` to create dependency lock of the dependencies required by this package, pipenv takes care of dependencies of dependencies using a `.lock` file that it creates containing version specific packages that our package needs, currently our package depends on slimoneat package only which has dependencies of its own and we use `setup.py` file with pipenv to create a package.

Step 4) After pipenv has been installed, run `pipenv install -e .` It will lock the packages and the dev packages and create a Pipenv and Pipenv.lock file, the .lock file is used by other developers to reproduce your virtual environment.

