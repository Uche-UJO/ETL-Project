# ETL-Project
##### Using ETL (Extract, Transform & Load) to create a database from multiple datasets.
##### The purpose of this project is to source and extract data sets, transform these datasets, and then load the transformed datasets onto a database.


#### Extraction
##### We obtained two datasets from  Opendata.gov:
##### 1)	State Drug Utilization Data  https://catalog.data.gov/dataset/state-drug-utilization-data-2010-81ad0
###### This dataset (csv format) comprises of information reported by states for covered outpatient drugs that are paid for by state Medicaid agencies since the start of the Medicaid Drug Rebate Program. The data includes state, drug name, National Drug Code, number of prescriptions and dollars reimbursed. 

##### 2)	Hospital General Information https://catalog.data.gov/dataset/hospital-general-information
###### This is a list of all hospitals that have been registered with Medicare. The list includes addresses, phone numbers, and hospital type. This list was compiled in a csv format.

##### These 2 sets of data were downloaded, and we proceeded to take a look at them. We discussed on what relevant information to keep and decided on the what database to utilize.


#### Transformation
###### The size of the State Drug Utilization dataset was too large to be migrated into the project repository. The file had more that a million rows. We decided to manually delete about half of the total number of rows. We didn't rely on any specific criteria to determine what rows to delete.
##### Both sets of data were read and stored into pandas data frames for easy readability and manipulation.

###### Irrelevant columns were removed and the remaining ones were renamed to make it easier to understand.


#### Load
###### Postgres database was used for this project. A project database was created (ETL-Project) within Postgres and tables were created to accommodate the newly transformed sets of data.

###### These datasets were then loaded onto the ETL-Project database through pandas.



#### Problems Encountered:
###### -	We initially could not connect to the database.  We had to ‘pip install psycopg2’  to proceed.
###### -	We also found it difficult to load the cleaned ‘State Drug Utilization Data’ file. It was discovered that a column within the file had 2 rows with ‘non-integer’ values. The rows were removed by applying a filter on the column in the csv file and manually deleting the rows.The data was eventually loaded successfully. 

#### Tools used: Jupyter Notebook, Postgres, Python.

###### Refer to project report for details.
