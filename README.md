# EnergyAUS
Data Augmentation and Cleaning
## How to use:
1. Copy the main.ipynb in a working directory (jupyter notebook)

2. Copy the Transaction.csv on the working directory 


# Explanation
## 1. data Cleaning

NaN values are to be imputed

>>> df.isna().sum()
Account_ID                0
CODE                      0
Implemented Date          0
Active Indicator         15
Account Type             14
Service                   0
BU                        0
Request Date              0
Account status            9
Status Code               0
$ Amount                  0
Version                   0
Agent ID                  0
FIBRE                     0
last Updated Date         0
Property TYPE          1266
Post Code                 0

A. Filling the null values with 1 using pandas fillna function as the those values are not very important
B. Dropping column 17 and 18 because it was NaN values and no column header found

## 2. Augment the data with a hash key.

Steps:
A. Select only few columns of the dataframe which are most important
B. Add some random characters before and after the Account_ID (in this case we are hashing only Account_ID because I think this is most important information to hide)
C. Create a new DF (as d2 in the code, just to leave the original d1 intact) and create a new hash column
D. Generate hashes in hexadecimals (0–9, a-f, and A-F)
E. Create a new DF (data_final) with the clear-text column removed
F. save the hashed data into the bworking directory as data_hashed.csv

## 3. Filter out the questionable data (Negative abount)


## 4. Write the data in a JSON file one record at a time.

stpes:
... jsonArray holds the line upto 1000 line from the csv file
.... converting jsonArray to Jason file and saving them in file as per batch numbers and saving them in the working directory


## 5. List post codes based on fastest response. Response Time.

....Using pandas to_datetime and then subtracting Request date from Implementated Date gives Response time, sort by Response time.
... Please note here I could not able to maintain the data pipeline(cannot keep the same pandas dataframe with hased file) at this step because I got some error need to check did  not get time  to do that. can do it later if required 

