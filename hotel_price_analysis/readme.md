# Hotel Room Price Analysis

### Contents
1. [Objectives](https://github.com/SteveLewisUK/datascience_bootcamp_projects/blob/main/classifying_IMDB_movie_reviews/README.md#objectives)
2. [Data](https://github.com/SteveLewisUK/datascience_bootcamp_projects/blob/main/classifying_IMDB_movie_reviews/README.md#data)
3. [Method and Tools Used](https://github.com/SteveLewisUK/datascience_bootcamp_projects/blob/main/classifying_IMDB_movie_reviews/README.md#method-and-tools-used)
4. [Conclusions](https://github.com/SteveLewisUK/datascience_bootcamp_projects/blob/main/classifying_IMDB_movie_reviews/README.md#conclusions)<br />


### Objectives
A Product Owner at an online travel company was contemplating implementing 'urgency messages' on the website to encourage customers to complete their booking as fast as possible. Examples include:
* “Prices have been rising. Book now to lock in your rates!” 
* “Your check-in is fast approaching. Book now to lock in your rates!”

An analysis was requested of the movement of the price of hotel rooms as the day approaches the check-in date.<br />


### Data
The data was randomly sampled booking data from five different cities with check-in dates between 10/10/2016 – 12/31/2016. 

|**Field** |**Description**|
|:------------- | :----------|
|# | No of record in each dataset|
|Hotel ID | Property identification number|
|City ID | City identification number|
|Star rating | The property’s star rating|
|Accommodation Type Name | The property’s accommodation type |
|Chain Hotel | Whether the property is part of a chain or not|
|Booking date | Date of booking made|
|Check-in date | Date of check-in |
|Check-out date | Date of check-out |

There were 5 datasets which, when concatenated, had a totoal of 49,064 rows.<br />


### Method and Tools Used
***Step 1***: Processing the data; concatenating the datasets, deleting duplicates, checking for null values.\
***Step 2***: Exploratory Analysis: Gaining insights using line plots, bar charts, boxplots, histograms and pie charts.\
***Step 3***: Created new date features to explore further the relationship between price and the length of time before check-in. Created for-loop to plot multiple scatter plots with best-fit straight line.\
***Step 4***: Fitting best-fit polynomial regression models the the plots with 2,3 and 4 degrees of freedom.\
***Step 5***: Investigated the usefulness of building models (Linear and Random Forest Regression) to predict price movements. Encoded categorical variables.\


### Conclusions
It is difficult to draw general conclusions regarding the price movements of all accommodations in the dataset. The most fruitful analysis occurred at the single property level.  However, that was possible only for the most popular properties.

The main factors affecting price are the Star-rating, City, Accommodation type and  Chain/non-Chain. It is not clear if there is actually any relationship between price and the booking/ check-in date delta.  If there is, it is not consistent across properties or booking/ check-in dates.

Other will factors play an important role (not included in this analysis):
- Availability of Rooms
- Seasonality & other factors that increase demand.  Further analysis would seek to identify seasonal trends. 
- Customer Reviews could influence price levels.
