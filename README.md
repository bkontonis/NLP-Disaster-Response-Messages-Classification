# Disaster Response Pipeline Project

In this project I built a model for an API that classifies disaster messages. The datasets provided by [Figure Eight](https://www.figure-eight.com) contain real messages sent during disaster events and their respective categories. The task was to train the supervised ML classifier to automate categorization of the new messages so that different disaster relief agencies would receive only relevant ones.

## Instructions:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/


## Results

**Step 1: ETL Pipeline**
* Loaded the messages and categories datasets (`disaster_messages.csv`, `disaster_categories.csv`)
* Merged the two datasets
*	Cleaned the data 
*	Saved it in a SQLite database `DisasterResponse.db`
            
**Step 2: ML Pipeline**
* Loaded data from the SQLite database
*	Split the dataset into training and test sets
*	Built a text processing and ML pipeline using NLTK and scikit-learn's Pipeline 
*	Trained and tuned the model using GridSearchCV
*	Evaluated results on the test set
*	Exported the final model as a gzip pickle file `model.p.gz`
            
**Step 3: Python Scripts**
* Converted the jupyter notebooks into python scripts `process_data.py` and `train_classifier.py`
* Refactored the code to make it modular
            
**Step 4: Flask App**
* Uploaded sql database file and pkl file with the final model to a Flask app template
* Created data visualizations in the app using Plotly


## Acknowledgements
This project is part of [Udacity Data Science Nanodegree Programm](https://www.udacity.com/course/data-scientist-nanodegree--nd025). 