# Google Play Store Apps Analysis

## Project objective
The objective of this project is to highlight the specific characteristics of the most popular apps by rating at Google Play Store. 

I aim to answer the following questions:

- What categories have better ratings?
- Are there differences in ratings between paid and free apps?
- Do other features such as number of reviews and content rating have any influece on rating?

The complete analysis is conducted in this Jupyter notebook. Annotations are done after each section and conclusions are summarized at the end of the notebook.  

## Dataset
The dataset contains information for 9660 apps on the Google-Play store. 
The thirteen features in the dataset are: 
- App: application name
- Category:  
- Rating: 1 to 5 star  
- Reviews: number of user reviews
- Size: in Mbs
- Installs: number of downloads
- Type: paid or free
- Price: $ for paid apps
- Content rating: targeted age group
- Genres: a subdivision of category
- Last updated: date of last update
- Current version: latest version on Play Store
- Android version: latest android version

The original database is published on Kaggle and can be found at: 
https://www.kaggle.com/datasets/lava18/google-play-store-apps

## Initial data cleaning
The dataset has been scraped from the Play Store. At first view, several anomalies are spotted. 
- Several columns have data corresponding to the previous column
- The category feature has unexpected values
- Some categorical features have unexpected non-letter characters
- Some features have duplicated values in the same observation

The Category feature was in all caps. Sorted every column alphabetically and displaced the data back to the corresponding column. 
Sort each column. check no weird values. extract or replace. 
Fill Nan. Missing Genres are given the same as Category and vice versa. 

Most of these problems are easily fixable using Excel, as the filter function allows to find outlier/wrong values pretty easily, especially for categorical values. I've conducted the initial data cleaning in excel and uploaded the final clean dataset as a csv to this repository. 
