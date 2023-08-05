[![CI Workflow](https://github.com/aimarker/titanic_app/actions/workflows/CI.yml/badge.svg)](https://github.com/aimarker/titanic_app/actions/workflows/CI.yml/badge.svg) [![CD Workflow](https://github.com/aimarker/titanic_app/actions/workflows/CD.yml/badge.svg)](https://github.com/aimarker/titanic_app/actions/workflows/CD.yml/badge.svg)

# The Great Titanic App 🛳️

Imagine, you or any of your relative were on the Titanic Ship. The project uses Random Forest Classifier model to predict if the passenger on-board on the Titanic ship will be saved or not.
The repository also contains the Passenger data to train the model. The project is logically grouped in two broad categories:
* Model training
* Prediction using API

Prediction API's are available as docker image. The docker image is currently getting pushed into DockerHub.

Project Info
------------
![Implementation](https://img.shields.io/badge/Implementation-Python-blue)      ![Python](https://img.shields.io/badge/Python-3.7|3.8|3.9|3.10-blue)

![ScikitLearn](https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white) ![AWS](https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white) ![FastAPI](https://img.shields.io/badge/fastapi-109989?style=for-the-badge&logo=FASTAPI&logoColor=white)
------------

Project Structure
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make train` or `make test`
    ├── README.md          <- The top-level README for developers using this project.
    ├── requirements       <- The requirements file for reproducing the analysis environment.
    │   ├── requirements.txt             <- Packages requirements for the project.
    │   └── test_requirements.txt        <- Packages requirements to run tests on the project.
    │
    ├── tests       <- Tests the entire project
    │   ├── __init__.py             <- Makes src a Python module
    |   ├── conftest.py             <- Validates all the configurations of the data.
    |   ├── test_features.py        <- Tests the features.
    │   └── test_predictions.py     <- Tests the predictions of the model.
    │
    ├── titanic_model       
    │   ├── __init__.py             <- Makes titanic_model a Python module
    │   ├── config          
    │   |   ├── __init__.py         <- Makes config a Python module
    |   |   └── core.py 
    |   |
    |   ├── datasets        
    │   |   ├── __init__.py         <- Makes datasets a Python module
    |   |   └── titanic.csv         <- Titanic dataset
    |   |
    |   ├── processing      
    │   |   ├── __init__.py         <- Makes processing a Python module
    │   |   ├── data_manager.py     <- Makes processing a Python module
    │   |   ├── features.py         <- Makes processing a Python module
    │   |   └── validation.py       <- Makes processing a Python module
    |   |
    |   ├── trained_models          <- Trained model path
    │   |   └── __init__.py         <- Makes trained_models a Python module
    |   |
    |   ├── VERSION                 <- VERSION of the model
    |   ├── config.yml
    |   ├── pipeline.py             <- Pipeline for entire ML Flow
    |   ├── predict.py              <- Prediction implementation
    │   └── train_pipeline.py       <- Training implementation
    |
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    |
    ├── titanic_model_api            <- Contains API's for prediction
    │   ├── app          
    │   |   ├── __init__.py          <- Makes app a Python module
    │   |   ├── schemas              <- Schema of the API
    |   |   |   ├── __init__.py      <- Makes shcemas a Python module
    |   |   |   ├── health.py        <- Model for health API
    |   |   |   └── predict.py       <- Model for predict API
    |   |   |    
    │   |   ├── api.py               <- API definition
    │   |   ├── config.py            <- Configuration
    │   |   └── main.py              <- Runner of the API
    │   └── requirements.txt         <- Separate requirement file needed for Docker image
    │
    ├── MANIFEST.in   
    ├── mypy.ini                     <- Python ini file
    ├── Dockerfile                   <- Docker image for serving API
    └── pyproject.toml


--------

# Installation

* Setup virtual environment
  ```bash
   $ mkdir venv
   $ python3 -m venv venv
   $ source venv/bin/activate
  ```
* Install dependencies
  ```bash
  $ make install
  ```
* Train model
  ```bash
  $ make train
  ```
* Test model
  ```bash
  $ make test
  ```
* Run all
  ```bash
  $ make all
  ```
