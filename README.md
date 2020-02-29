# Selecting the best site for a Multiplex Theatre from mscraped Map data

## 1. Introduction

Indian Film Industry ranks 1st in number of films produced and admissions [1]. The number of screens for viewing films is 8 per million, which is very low as compared to western countries which are in the range of 120+ [2]. India has about only 2400 multiplex screens as compared to single screens which are 6700 [2].Pune is the second largest city in the state of Maharashtra and ranks 9th in terms of population in India with a population of 3.13 Million [3].

Even though the multiplex are just 27 percent of the total screens, these contribute to about 45 percent of the total revenue of cinema [2]. This stresses the importance of such an establishment. 

The main advantage of Multiplex is that multiple movies can be screened in at a single location and people are presented with a choice of entertainment. This also encourages the development of businesses like food court and merchandise industry which often compliment the movie industry. In this way, people not only find a getaway location for their weekends, but also all their other requirements are satisfied along with it. 

With the advancements of film making and videography, more and more movies and plays are pushed to the audience every day. People spend most of their time engaged in work. Entertainment, whether it may be outdoors or indoors can be considered to be a major form of stress release. Outdoor entertainment can be concerts, fairs, meetups and many more things. Indoor entertainments include video games, watching movies, catching up on web series etc. 

Considering movies and the whole market surrounded around it, Multiplex can serve the audience as well as develop a steady stream of income for the organization which runs such establishment.  

The primary factors for the establishment of such facilities are the location of the establishments and the funding required. Most countries have private organizations interested to take up this business venture. The following question which arises is that – what are the factors that must be considered in order to select a location for such an establishment? 

</br>

## 2. Business Problem

The main question is- If an organization is deciding to open a Multiplex establishment in Pune, which location would be the best considering all the factors?

This report aims to put forward an analysis in selection of location for a Multiplex establishment using location data obtained from foursquare API. The algorithms used can help to identify the perfect location considering proximity to nearby similar facilities and the demand for the services. 

</br>
 
## 3. People interested in the Project – Target Audience

The target audience in this scenario are normal people who want to spend their leisure time for watching movies. The main factors contributing to the demand are time of travel and location.

The report also aims to make the business decision of construction of such an establishment by providing answers to exactly where can such a facility be constructed ?. This is meant to target the private organizations which are interested in running such a business venture. 

</br>

## 4. Data required The data required to build a model to suggest a location for the establishment is as follows: 
 
> ### 4.1 Neighborhood Data: Data pertaining to neighborhoods of Pune city obtained from Wikipedia. 

> The data specifying the index and the neighborhoods of Pune city can be obtained through Wikipedia page: Neighborhoods of Pune city. This provides a table listing the neighborhoods.

> Web scraping techniques such as using the Beautiful Soup library or the Wikipedia library can be used to convert this html data into a pandas data frame. This is helpful for analysis with python in Jupyter Notebook.

</br>

> ### 4.2 Location Data: Location data of these neighborhoods obtained from geocoder library of google or location data available online. 

> The latitudes and longitudes of neighborhoods of Pune city are required in order to access the third step of the model preparation. The latitude and longitude (co-ordinates) can be obtained using the geocoder library of google.

> An alternative to the above step, if the geocoder library becomes unreliable, is obtaining a geospatial file detailing the location co-ordinates from web directly. 

</br>

> ### 4.3 Venue Data: Data of venues in these neighborhoods, obtained from Foursquare API

> Using the location data obtained in second step of model preparation, the Foursquare API is used to obtain the venue data of these neighborhoods. The data is then cleaned and the data pertaining to Multiplex establishments of each neighborhoods is obtained. The data is then used for machine learning algorithms to perform exploratory analysis in order to obtain results and make inferences. 

</br>

## 5. Methodology

The following steps were employed to obtain the required results:

> ### 5.1 Importing Necessary Libraries The first step is to import the necessary libraries and packages

> Numpy – For numerical calculations 
> Matplotlib – plotting and visualization 
> Pandas – Data manipulation 
> Geocoder – Obtaining location data 
> Folium – Creation of maps 
> Beautiful Soup – Web Scraping 
> Sklearn – Machine Learning 

</br>

> ### 5.2 Web Scarping

> Using the Beautiful Soup (bs4) package, the data from Wikipedia entry of ‘Neighbourhoods of Pune’ can be scrapped. 
The data can be cleaned to obtain the required results and then stored in the form of a dataframe using Pandas library. 

</br>

> ### 5.3 Visualization

> Using the geocoder library the co-ordinates of Pune city are obtained and using the folium library, a map denoting the neighbourhoods as markers is visualized.

</br>

> ### 5.4 Obtaining Venues

> By using the developer account of Foursquare API, venues data can be obtained. The details required to access the account are the credentials which are hidden in the code submitted.

> Then using parameters such as setting search radius at 2000m and a limit of 100 venues, a venues list is obtained. This venue list is used to create a dataframe using pandas.

> A quick check is carried out to verify if Multiplex as a category exists within it. 

</br>

> ### 5.5 One Hot Encoding

> The obtained data frame is one hot encoded using the get dummies method of pandas. Using the group by and mean, statistical information is obtained which is used to filter the dataframe to obtain only the values where “Multiplex” is positive. 

</br>

> ### 5.6 Clustering

> Using the sklearn library, K-Means clustering is applied on the data. K-Means is a clustering technique of Machine learning where depending upon the data (similarity or range), the data is divided within certain clusters.

> The number of clusters is pre-defined in order to assign the centroids along with the cluster means can be calculated. The nearest data points to these centroids are grouped together in to similar clusters. Using the values of within cluster elements, a new centroid value is calculated and the process is iterated.

> The number of clusters for this analysis was selected as 5. Obtaining the cluster labels from the results, the cluster data was merged with the dataframe and is presented as final dataframe for visualization. 

</br>

> ### 5.7 Cluster Visualization

> Using the folium library the visualization of clusters of venues in the Pune city are obtained.

</br>

## 6.Discussions and Observations

Discussions and Observations were presented in a detailed report of the analysis available here: https://github.com/SwoopGT/Selecting-the-best-site-for-a-Multiplex-Theatre-from-scraped-Map-data/blob/master/Selecting%20the%20best%20site%20for%20a%20Multiplex%20Theatre%20from%20mscraped%20Map%20data.pdf

</br>

## 7. Limitations

The following inferences can be more refined by the exact population distribution of Pune city. This will further help in discarding two of the three options provided above.

Furthermore, the information of the demographics and their spending habits does influence the decision making in this business decision. The data in hand at the moment fails to take into consideration of these criteria. Only a rough estimate can be made. But with the availability of these data elements the results can be refined and more focused answer to the business decision can be obtained.

</br>

## 9. Conclusion

Using web scraping technique, data was collected. It was manipulated to required format and machine learning was applied to reach the conclusion in order to answer the business question. The cluster label 0 was selected and further it was analyzed to reach to a conclusion that 3 locations are suitable for the construction of a Multiplex in Pune city.

</br>


