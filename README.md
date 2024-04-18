# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
This project aims to investigate the correlation between the availability of free bikes at bike stations in Vancouver city and the characteristics of nearby bars located within a 1000m radius of each bike station. 

The objective is to ascertain whether the presence of bars impacts the availability of bikes and to identify the key features that most accurately describe this relationship and to what degree the impact can be found.

## Process
**CityBikes API** : Retrieving the bike stations around Vancouver city using the CityBikes API. There were 251 bike stations that were found around the city listed on this API.

**Foursquare API and Yelp API** : Fetched the different Bars within 1000m of each bike station based on the longitude and latitude of each bike station retrieved from CityBikes.
    
**Joining Data and EDA** : This step involved joining the data retrieved from CityBikes, Yelp and Foursquare API. Following the merge, explonatory data analysis was performed to observe the interconnection of different variables with each other.


**Feature Engeering** : To create average of the features of each bike station and comparing them on station level as there were numerous bars which were common within stations and thus creating a duplication information.

**Regression Model** :  Creating a regression model to determine if number of free bikes at the bike station are related to the point of Interests’(Bars) features and what are the prominent features that do affect the number of bikes.

## Results

### Comparison between YELP and FOURSQUARE API's
<ul>
<li>
There were pros and cons with both the API but Yelp definitely did provide a broader search and large number of results around each bike stations. 
</li>
<li> The Yelp API only allowed 300 API calls per day so it would not work for a city with 300+ stations.
</li>
<li>
As compared to Yelp, I had to do a second API call in foursquare to get more details about a 
business place. So 2 foursquare calls were equal to 1 Yelp API call to retreive the same set of data.
</li>
<li>
The Foursquare API had more interesting features such as payments types accepted, if bar offered outdoor seating and if bar offered street parking as compared to Yelp.
</li>
<li>
I did noticed during overlapping that categories ditribution over both the API differ such as Cactus Club Cafe ( one of the POIs) yielded 164 rows in YELP and none in Foursquare. There might be a reason that it is not listed under 'Bars' in foursquare.
</li>
<li>
Both the API results even with a radius provided with value of 1000m yielded rows with maximum distance of bar from the station with 1973m (Foursquare) and 2626m (Yelp).
</li>
</ul>

### Regression Model Results
<ul>
<li>
The model explains the dependency of bikes count by 14.70% and the prominent features found were Yelp Average rating, Yelp review count and outdoor seating feature from foursquare.
<li>
Yelp Average rating, Yelp review count and Foursquare outdoor seating features are significant features. 
</li>
<li>
With every 1 unit increase in yelp rating and outdoor seating feature, number of bikes will increase by 5.4052 and 3.8005 respectively.
</li>
<li>
With every 1 unit increase in yelp review count, number of bikes will decrease by -0.0080.
</li>
</ul>

## Challenges 
<ul>
  <li>Merging data from Yelp and Foursquare was a big challenge as overlapping resulted in loss of data as the POIs which were covered by Yelp were nt covered by Foursquare and Vice Versa,
  
  ***Example*** : Yelp retrieved 167 rows for Cactus Club Café near multiple stations whereas Foursquare none. One possible reason could be that Yelp lists the POI under 'Bars' category as well but Foursquare does not.
</li>
<li>
Yelp API coverage limited to 300 calls per day.
</li>
<li>
Performing regression with Yelp and CityBikes API merged data resulted in a poor model. It did enhanced with the introduction of features from Foursquare API.
</li>
</ul>

## Future Goals
- Exploring other impacting features such as data during certain times of the day.
- How dense is the POI and bike station in regards to population, buildings, traffic etc.
- One scope of the project could be focusing on one bike station and gather n number of unique POIs to see how those affect the station.


