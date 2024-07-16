## Maji Ndogo Agriculture Analysis
## Project Overview
Welcome to the Maji Ndogo Agriculture Analysis project! This project focuses on analyzing various geographical, weather, soil, and farm management features to understand optimal farming conditions for different crops in the Maji Ndogo region. The goal is to provide insights and recommendations for crop cultivation based on data analysis.

## Data Description
The dataset used in this project is stored in an SQLite database named Maji_Ndogo_farm_survey.db. The data is split into four main tables:

Geographic Features: Contains data on field elevation, latitude, longitude, location, and slope.
Weather Features: Contains data on rainfall, minimum and maximum temperatures, and average temperatures.
Soil and Crop Features: Contains data on soil fertility, soil type, pH levels, and chosen crops.
Farm Management Features: Contains data on pollution levels, plot sizes, crop types, annual yields, and standard yields.

## Project Steps
1. Data Import and Merging
The first step is to import the data from the SQLite database and merge the tables into a single Pandas DataFrame using the common Field_ID key.

2. Data Cleaning
The data contains some errors that need to be addressed:

Swapped column names
Spelling errors in crop types
Negative values in the elevation column
3. Analysis
Challenge 1: Uncovering Crop Preferences
Focus on the key crop tea to determine the optimal conditions for its growth by analyzing the mean rainfall and mean elevation for tea fields.

Function Definitions
explore_crop_distribution
This function filters the DataFrame by a specified crop type and returns the mean rainfall and mean elevation for the filtered crop.

python

def explore_crop_distribution(df, crop_filter):
    """
    Filters DataFrame by a specified crop type and returns the mean Rainfall and Elevation.

    Args:
       df (DataFrame): The DataFrame containing the crop data.
       crop_filter (str): The crop type to filter by.

    Returns:
       tuple: A tuple containing the mean Rainfall and mean Elevation for the filtered crop.
    """
    filtered_df = df[df["Crop_type"] == crop_filter]
    mean_rainfall = filtered_df["Rainfall"].mean()
    mean_elevation = filtered_df["Elevation"].mean()
    
    return (mean_rainfall, mean_elevation)
    
## Installation and Setup
Prerequisites
Python 3.x
Pandas
SQLAlchemy
