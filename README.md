# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The goal of the project was to build a statistical model to determine whether there was a relationship between the En la Bici bike network in Mendoza, Argentina and restaurants in the area.

## Process
Step 1: 
* Connected to the CityBikes API and retrieved data on the bike station names, locations (latitude, longitude), and bike availabilities in Mendoza, ARG. 
* Data was as of Dec. 4, 2023.
* Notebook: city_bikes.ipynb
* csv file: 
    * enlabici-mend.csv 

Step 2: 
* Connected to Foursquare and Yelp APIs to retrieve information about restaurants in the vicinity of the bike stations from step 1.
* Parsed json response and created dataframes. 
* Compared the quality of the data and found top 10 restaurants according to each API result.
* Notebook: yelp_foursquare_EDA.ipynb
* csv files:
    * foursquare_df_orig.csv
    * yelp_df_orig.csv

Step 3: 
* Cleaned and transformed data from steps 1 and 2 (evaluated data, fixed nulls etc.)
* Notebook: EDA_part1_part2.ipynb
* csv files:
    * bikes_df_eda.csv
    * fs_df_eda.csv
    * yp_df_eda.csv

Step 4: 
* Combined cleaned bike statation data with Foursquare and Yelp data. 
* Created visualizations (pairplots and correlation heatmaps) to gauge correlation relationships.
* Created a SQLite database to store the data
* Notebook: joining_data.ipynb
* Images:
    * pairplotfs.png
    * pairplotyp.png
    * fs_heatmap.jpg
    * yp_heatmap.jpg
    * combo_heatmap.jpg
* csv files:
    * yp_correlation_matrix.csv
    * fs_correlation_matrix.csv
    * combo_correlation_matrix.csv
    * model_df.csv
* sqlite file:
    * bikes_resto.sqlite

Step 5:
* Used results from step 4 to build a regression model.
* Notebook: model_building.ipynb

## Results
* Data quality was better for Foursquare results in terms of quantity and quality
* There was no relationship between bike numbers or their use and the restaurants in the area.
* There was a relationship between distance from a bike station and restaurant rating (as restaurant rating increases, distance from bike station to restaurant decreases). This is not all that meaningful as discussed in 'model_building.ipynb' notebook.

Overall, there is not a robust connection between the bike stations and restaurants in their vicinity.

## Challenges 
* A small size of data as there were only 22 stations in the city.
* API usage limits meant being mindful of requests.

## Future Goals
* Analyze other attributes included in API response
* Create a classification model
* Determine if there's a better relationship between bike stations and park locations, instead of restaurants
* Pick a city with more bike stations to analyze relationships
