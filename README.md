# Credit

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

### Steps
1. Define a function get_last_page(name) that takes the name of the dataset as a parameter and returns the last page number of the dataset. The function makes a GET   request to the API and retrieves the last page number.
2. Define a function pull_and_insert(name) that takes the name of the dataset as a parameter. The function loops through all pages of the dataset, makes a GET request for each page, appends the data to a list, normalizes the data into a DataFrame, drops the table in BigQuery (if it exists), loads the DataFrame into the table, and renames the columns.
3. In the main function, call pull_and_insert(name) for each dataset: 'repayment', 'disbursement', 'loan_request'.
Run the Jupyter Notebook to transfer the data from the API to BigQuery.

### Note
The script is set up to retrieve data from three tables: "loan_request", "disbursement", and "repayment". If you need to retrieve data from a different table, you'll need to update the pull_and_insert function and replace 'repayment' with the name of the desired table
