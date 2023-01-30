# Helium-Credit

### Overview
This script is used to move data from a PostgreSQL database to BigQuery using a Jupyter notebook.

### Requirements
1. Install the following libraries:
   - json
   - requests
   - config
   - pandas
   - os
   - google.cloud.bigquery
2. Obtain an API key for accessing the PostgreSQL database.
3. Authenticate the token using the config file and set up a header parameter for the API GET request.
4. Connect to BigQuery using a keyfile.


Step 2
The script uses an API to access the PostgreSQL database, so an API key is required.
Authenticate the token from the config file and create a header parameter for the API get request
Connect to BigQuery using the keyfile


Step 3
Create a function called get_last_page(name) that takes in the name of the dataset as a parameter and returns the last 
page number of the dataset. This function makes a GET request to the API using the name passed in as a parameter, gets 
the last page number and returns it.


Step 4
Create a function called pull_and_insert(name) that takes in the name of the dataset as a parameter. This function loops 
through all the pages of the dataset, makes a GET request to the API for each page, appends the data from each page to a list, 
and normalizes the data into a DataFrame. The function then drops the table in BigQuery if it already exists, loads the 
DataFrame into the table, and renames the columns.



Step 5
In the main function, call the pull_and_insert(name) function for each dataset: 'repayment', 'disbursement', 'loan_request'.


Step 6
Run the notebook to move the data from the API to BigQuery.

Note
The script is currently set up to retrieve data from 3 tables "loan_request", "disbursement" and "repayment". 
If you want to pull data from a different table, you need to update the pull_and_insert function and replace 'repayment' 
with the name of the table you want to pull data from.
