# Classroom-Python-based-Artificial-Intelligence
Coursework material for [introduction-to-python-with-artificial-intelligence](https://kapoorlabs.org/product/introduction-to-python-with-artificial-intelligence/)

## Python for developers
### How to make a python project with setup.py and Pipenv
Let's create a project that you want to deploy via Pypi. 

Name of the project: goodplaceintroduction 

We begin by making a github repository for it and then create a folder with the same name as the project name. [How to create a python package](https://github.com/Kapoorlabs-paris/goodplaceintroduction)

### Steps to create a skeleton of a package for deployment
Step 1) Create a setup.py file: this file contains all the required dependencies of the current python package needed for it to run, author name and contact, python interpretor and the version of the package

Step 2) Inside the goodplaceintroduction folder create a `__init__.py` and `_version.py` files. The `_version.py` contains a single line defination of the version of the code and the `__init_.py` file imports this version file allowing the setup.py file to grab the version of the library. This allows users to import your package and ask for its version using `print(goodplaceintroduction.__version__)` command.

Step 3) Install pipenv using pip command `pip install pipenv` to create dependency lock of the dependencies required by this package, pipenv takes care of dependencies of dependencies using a `.lock` file that it creates containing version specific packages that our package needs, currently our package depends on slimoneat package only which has dependencies of its own and we use `setup.py` file with pipenv to create a package.

Step 4) After pipenv has been installed, run `pipenv install -e .` It will lock the packages and the dev packages and create a Pipenv and Pipenv.lock file, the .lock file is used by other developers to reproduce your virtual environment.

### Steps for deploying the package

Now that we have a simple skeleton package with a version, requirements of its dependencies and a setup file we can with few more steps release it on the Pypi index for the whole world to pip install it.

Step 1) If you are calling a module instead of a filename (beccause you do not know or care about where the files are located) use python -m, for creating a build of your package i.e a tar file and python wheels call `python -m build` or  `python3 -m build` from the directory where setup.py file is located.  

Step 2) After this let us check if the package is built correctly by using a module called `twine` (pip installable) and then run this in terminal 
`python3 -m twine check dist/*`, if everythin sis ok you should see PASSED next to that tar and whl file.

Step 3) Now you need an account at Pypi, get one and first let us deploy the package to testPypi instead of the main index, then you can execute this command to upload your package: `python3 -m twine upload --repository testpypi dist/*` if all goes well we are ready to populate the main pypi website by changing the testpypi in the last command to pypi.

## Deep Learning for developers

### Jupyter notebooks for Cifar-10 dataset
In this part we will go over the notebooks for Cifar-10 dataset:
[Jupyter notebooks for Cifar-10 dataset](https://github.com/Kapoorlabs-paris/goodplacedeeplearning/tree/main/Cifar)

### Jupyter notebooks for ImageNet dataset
In this part we will go over the notebooks for ImageNet dataset:
[Jupyter notebooks for ImageNet dataset](https://github.com/Kapoorlabs-paris/goodplacedeeplearning/tree/main/ImageNet)

### Jupyter notebooks for Fashion-Mnist dataset
In this part we will go over the notebooks for Fashion-Mnist dataset:
[Jupyter notebooks for Fashion Mnist dataset](https://github.com/Kapoorlabs-paris/goodplacedeeplearning/tree/main/FashionMnist)


### Jupyter notebooks for Imdb dataset
In this part we will go over the notebooks for Imdb dataset:
[Jupyter notebooks for Imdb dataset](https://github.com/Kapoorlabs-paris/goodplacedeeplearning/tree/main/Imdb)


### Jupyter notebooks for Predicting House Prices dataset
In this part we will go over the notebooks for Predicting House Prices dataset:
[Jupyter notebooks for Predicting House Prices](https://github.com/Kapoorlabs-paris/goodplacedeeplearning/tree/main/PredictHousePrices)
