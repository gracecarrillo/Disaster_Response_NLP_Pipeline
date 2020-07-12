# Disaster Response Pipeline Project


## Table of Contents
1. [Description](#description)
2. [Files](#Files)
3. [Getting Started](#getting_started)
	1. [Dependencies](#dependencies)
	2. [Installation](#installation)
	3. [Run it](#execution)
4. [Author](#author)
3. [License](#license)
4. [Acknowledgement](#acknowledgement)

<a name="descripton"></a>
## Description

This Project is part of the Data Science Nanodegree Program by Udacity in collaboration with [Appen (previously known as Figure Eight)](https://appen.com/). The dataset contains a set of messages related to disaster response suitable for text categorisation and related natural language processing tasks. This dataset contains 30,000 messages drawn from events including an earthquake in Haiti in 2010, an earthquake in Chile in 2010, floods in Pakistan in 2010, super-storm Sandy in the U.S.A. in 2012, and news articles spanning a large number of years and 100s of different disasters. It can be downloaded [here](https://appen.com/datasets/combined-disaster-response-data/).

The data has been encoded with 36 different categories related to disaster response and has been stripped of messages with sensitive information in their entirety.

This project is divided in the following key sections:

1. ETL pipeline for data pre-processing and cleaning. Data is saved on SQLite DB
2. Machine Learning pipeline for text classification
3. Web based app deployment as GUI.

<a name='Files'></a>
## Files

```.
├── app     
│   ├── run.py                           # Flask file to runs app
│   └── templates   
│       ├── go.html                      # Classification result page
│       └── master.html                  # Main page    
├── data                   
│   ├── disaster_categories.csv          # Dataset including all categories  
│   ├── disaster_messages.csv            # Dataset including all messages
│   └── process_data.py                  # Data cleaning pipeline
├── models
│   └── train_classifier.py              # Train, save and store ML model           
└── README.md
```
**app/run.py**: Launch a Flask web app as GUI to classify disaster messages.

**app/templates/***: templates/html files for web app

**data/process_data.py**: ETL pipeline for data cleaning, feature extraction, and data storage SQLite DB

**models/train_classifier.py**: ML pipeline to loads, train and save the trained model as a `.pkl` file

<a name="getting_started"></a>
## Getting Started

<a name="dependencies"></a>
### Dependencies
* Python 3.5+
* Machine Learning: NumPy, SciPy, Pandas, Sciki-Learn
* Natural Language Processing: NLTK
* SQLlite Database: SQLalchemy
* Model Loading and Saving: Pickle
* Web App and Data Visualisation: Flask, Plotly

<a name="installation"></a>
### Installation
Clone the repo:
```
git clone https://github.com/gracecarrillo/Disaster_Response_NLP_Pipeline.git
```
<a name="execution"></a>
### Executing Program:
1. Run the following commands in the project's directory to set up the db, train and save the model.

    - To run ETL pipeline and store cleaned data in the db
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/disaster_response_db.db`
    - To run the ML pipeline to load data from db, train and save classifier as pickle file
        `python models/train_classifier.py data/disaster_response_db.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/

<a name="authors"></a>
## Author

* [Graciela Carrillo](https://github.com/gracecarrillo)

<a name="license"></a>
## License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

<a name="acknowledgement"></a>
## Acknowledgements

* [Udacity](https://www.udacity.com/) as hosts of the Data Science Nanodegree Program
* [Appen](https://appen.com/) for providing the relevant dataset
