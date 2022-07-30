# Classroom-Python-based-Artificial-Intelligence
Coursework material for [introduction-to-python-with-artificial-intelligence](https://kapoorlabs.org/product/introduction-to-python-with-artificial-intelligence/)

Dataset for this course is available at [Zenodo link](https://zenodo.org/record/6944308)

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

### Searching with regular expressions

In this notebook we discuss the usefullness of regular expressions to serach for names/integers in a bunch of text, examples include finidng numbers at the beginning or the end of the text and how we can use that to extract the name of the file without them. [Searching with regular expressions](https://github.com/Kapoorlabs-paris/goodplacepython/blob/main/Search_regular_expressions_integer.ipynb)

## Python for Deep Learning developers

This is a subset of the python for develoeprs section as in this section we focus primarily on develoipers that work with deep learning datasets and models. SInce the data is shipped in various formats, in this course we focus on how to choose the best setup given the final goal of using the codebase to obtaining well trained deep learning models.

### Cifar-10 dataset
In this part we download the Cifar-10 dataset, convert the labels to one-hot encoding, learn how to create aa subset of 10 class dataset, save thm in npz format. [Python in Cifar-10](https://github.com/Kapoorlabs-paris/goodplacepython/blob/main/download_training_data_keras.ipynb)

### Nvidia segmentation dataset
In this part we look at the dataset provided by Nvidia training academy for training a simple segmentation model with tensorlfow. We experiment with the tensorflow data structure and compare that with saving data in npz formats. We also provide the functionality to upload and downlaod data from Zenodo. [Python in daset type conversions](https://github.com/Kapoorlabs-paris/goodplacepython/blob/main/download_training_data_tensorflow_npz.ipynb)

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
