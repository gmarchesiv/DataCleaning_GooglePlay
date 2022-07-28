# Google Play Store Apps Analysis

## Project objective
The objective of this project is to highlight the specific characteristics of the most popular apps by rating at Google Play Store. 

I aim to answer the following questions:

- What categories have better ratings?
- Are there differences in ratings between paid and free apps?
- Do other features such as number of reviews and content rating have any influece on rating?

The complete analysis is conducted in this Jupyter notebook. Annotations are done after each section and conclusions are summarized at the end of the notebook.  

## Dataset
The dataset contains information for 10,000+ apps on the Google-Play store. 
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
The dataset has been scraped from Google Play Store. 

At first view in Excel, several anomalies are spotted: 
- Several columns have data corresponding to the previous column
- The category feature has unexpected values
- Some features have duplicated values in the same observation

Most of these problems are easily fixable using Excel using the filter function and copying and pasting where necessary. 
I've conducted the initial data cleaning in Excel and uploaded the final clean dataset as a csv file. 

I followed this process:  
-  I sorted every column alphabetically to find inconsistencies. Several columns had additional information that did not belong to the category.  
-  I moved the data back to its correct column and sorted again until no incoherent values could be found.  
-  I proceedeed with the next column and repeated the process
-  When missing  `Genres` were found, I gave them the same value as `Category` and vice-versa
-  Missing values where filled as NaN.

## Conclusions
On average, users tend to give positive ratings. The distribution of ratings shows a left skew, with only 25% of the distribution below 4. The average rating is 4.20 and the median 4.30. Hence, any detailed analysis of differences among categories or among particular apps within a category will happen in the 4 to 5 range.
The top-rated categories in the Google Play Store are Education, Books and Reference, and Art and Design. These are among the top five categories even when we control for number of ratings (more than 162).
Education has the most consistent ratings . The range is smaller than other categories and has only one outlier at the bottom with a rating of 3.5. Nevertheless, it does not have any 5 ratings.
Dating is the worst performing category in terms of ratings. Although its range is compact, top performers are few and it has a long left tail with a few very poorly-rated apps.
Paid apps are better rated than free apps. Free apps show a longer left tail. This could be because developers spend less time and effort on the product since its free. The opposite argument could be made for paid apps.
It's important to caveat that only 7% of the apps in this sample are paid. A quick Google search shows that paid apps are 3% of total apps for 2022. So the averages and medians discussed above are probably more favorable than what they are currently, since this dataset's most current information is for August of 2018.
Apps with less than 162 reviews have a much wider distribution for ratings than those with more than 4700 reviews. As expected, the law of large numbers draws the variance down. This was to reason to exclude the former group from the Category analysis.
Median values for ratings tend to be consistent across Content categories (Everyone, Teen, Adult). Apps for Everyone do have a longer left tail, but this is probably due to representing more than 90% of the total observations in the sample.
