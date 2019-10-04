# Disaster Response Pipeline Project


### Project Overview

In this project, we analyze disaster data from Figure Eight to build a model for an API 
that classifies disaster messages.

In the Project Workspace, you'll find a data set containing real messages that were sent 
during disaster events. You will be creating a machine learning pipeline to categorize 
these events so that you can send the messages to an appropriate disaster relief agency.

This project includes a web app where an emergency worker can input a new message and get 
classification results in several categories. The web app will also display 
visualizations of the data.


### Instructions:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/


## File Structure

- app
| - template
| |- master.html  # main page of web app
| |- go.html  # classification result page of web app
|- run.py  # Flask file that runs app

- data
|- disaster_categories.csv  # data to process 
|- disaster_messages.csv  # data to process
|- process_data.py
|- InsertDatabaseName.db   # database to save clean data to

- models
|- train_classifier.py
|- classifier.pkl  # saved model 

- README.md

## Test Data Results

                          precision   recall   f1-score   support

               related       0.97      0.82      0.89      4788
               request       0.46      0.89      0.61       463
                 offer       0.00      0.00      0.00         0
           aid_related       0.63      0.79      0.70      1749
          medical_help       0.05      0.77      0.10        30
      medical_products       0.07      0.78      0.14        23
     search_and_rescue       0.06      0.89      0.11         9
              security       0.00      0.00      0.00         0
              military       0.07      0.67      0.13        18
           child_alone       0.00      0.00      0.00         0
                 water       0.26      0.91      0.40        97
                  food       0.49      0.87      0.63       329
               shelter       0.24      0.82      0.37       130
              clothing       0.08      0.64      0.14        11
                 money       0.03      1.00      0.07         4
        missing_people       0.00      0.00      0.00         0
              refugees       0.01      0.75      0.03         4
                 death       0.12      0.88      0.21        33
             other_aid       0.01      0.60      0.03        15
    infrastructure_related   0.00      0.00      0.00         1
             transport       0.09      0.71      0.16        28
             buildings       0.08      0.91      0.15        22
           electricity       0.03      0.75      0.06         4
                 tools       0.00      0.00      0.00         0
             hospitals       0.00      0.00      0.00         0
                 shops       0.00      0.00      0.00         0
           aid_centers       0.00      0.00      0.00         0
    other_infrastructure     0.00      0.00      0.00         1
       weather_related       0.64      0.84      0.72      1070
                floods       0.45      0.89      0.60       198
       weather_related       0.64      0.84      0.72      1070
                 storm       0.43      0.76      0.55       262
                  fire       0.02      0.50      0.04         2
            earthquake       0.72      0.89      0.80       413
                  cold       0.05      0.71      0.10         7
         other_weather       0.01      0.50      0.03         8
         direct_report       0.37      0.86      0.52       449
             micro avg       0.51      0.82      0.63     10168
             macro avg       0.18      0.57      0.23     10168
          weighted avg       0.74      0.82      0.76     10168
           samples avg       0.48      0.70      0.52     10168

Accuracy Score: 0.9477080551846907