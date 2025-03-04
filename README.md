#Import the required libraries
import pandas as pd
import matplotlib.pyplot as plt
#Load and read the dataset
#Use pandas function dtypes to tell the data type fromeach column in the dataset
#locating the missing values by calculating How many null values are there in dataset
data.isnull().sum()
#Install and import the missingo.matrix function to visualise the null values
missingno.matrix(data)
#import numpy library
import numpy as np
# Calculate total number of cells in dataframe and cells with missing values
total_cells = np.product(data.shape)
total_missing = data.isnull().sum()

# Calculate percentage
percentage_missing = total_missing/total_cells * 100
print(percentage_missing)
#Handlig the missing values by using the dropping method by the aid of dropna function
#perform various data exploration tasks, including describing the data and conducting statistical analysis
# Number of content types (i.e., Movies vs TV Shows)
content_type_counts = data['type'].value_counts()
display(content_type_counts)
# Duration of the content type (i.e., Minutes vs Season)
content_duration_counts = data['duration'].value_counts()
display(content_duration_counts)
# Ratings distribution
rating_counts = data['rating'].value_counts()
display(rating_counts)
#Install & importing the seaborn library
pip install seaborn
import seaborn as sns
# Plot Frequently watched Genres
plt.figure(figsize=(12,6))
sns.barplot(x=genre_counts.values, y=genre_counts.index, palette="viridis")
plt.xlabel("Number of Viewers")
plt.ylabel("Genre")
plt.title("Frequently Watched Genre on Netflix")
plt.show()
# Plot Ratings Distribution
plt.figure(figsize=(12,6))
sns.barplot(x=rating_counts.index, y=rating_counts.values, palette="magma")
plt.xticks(rotation=45)
plt.xlabel("Ratings")
plt.ylabel("Count")
plt.title("Ratings Distribution Genre on Netflix")
plt.show()
