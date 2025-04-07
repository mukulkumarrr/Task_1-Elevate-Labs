# Task 1: Customer Personality Analysis- Data cleaning
# Step 1: Importing libraries
import pandas as pd

# Step 2 : Reading file, first row as header and seperator as tab
df = pd.read_csv("marketing.csv",header=0,sep='\t')

 
# Step 3: Looking the table Structure
df.info()

 
# Step 4 : Checking of missing values within each column in the data frame.
df.isnull().sum()

 
# Step 5 : Removing empty cells
df.dropna(inplace = True) #this will change the dataset itself does not make a new dataset

print(df.to_string()) # View the content

 
# Step 6 : Checking duplicate Values
df.duplicated().sum()

 
# Step 7 : Changing data formats
#change the data type to date with given format

df['Dt_Customer'] = pd.to_datetime(df['Dt_Customer'],format='%d-%m-%Y', errors='coerce')

print(df.to_string())

 
# Step 8: Saving the cleaned csv file
df.info()
df.to_csv("cleaned.csv")


