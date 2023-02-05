# Fire Region Data Creation Project

## Introduction

The California Fire Science Consortium established fire regions across the state of California to aid in managing and responding to wildfires. This project aims to use metadata of weather stations within these established fire regions in order to provide relevant weather information during a wildfire event. Code in this project was used in a larger project for the National Science Foundation, where machine learning models were used on the created dataset to identify potential risk factors that are currently ignored by regulatory bodies.  

## Data Source

The data for this project was obtained from the NOAA National Centers for Environmental Information (NCEI) Climate Data Record of Hourly Surface Meteorological and Upper-Air Observations.

## Data Processing

The data was processed using Python and the following libraries:

- Requests
- Pandas
- Shapely
- Regular Expressions (re)

The steps involved in the data processing are as follows:

1. The fire regions were established using the coordinates provided by the California Fire Science Consortium and stored as Shapely Polygons.
2. A list of weather stations and their coordinates were extracted from the data file obtained from NCEI.
3. For each weather station, the program checks if it is located within one of the established fire regions and appends it to a list of stations within that region.
4. The function `lat_lon_to_shapely` was created to convert latitude and longitude into Shapely Point objects.
5. The function `find_region` takes a fire location and returns the fire region it is located in.
6. The function `region_station_list` takes a fire region and returns a list of weather stations and their coordinates within that region.
7. The function `closest_to_fire_center` takes a list of weather stations and a fire location and returns a list of the closest weather stations to the fire center.

- All of these combine to ultimately be used towards adding to initial dataset

## Data Output

The data output from this project adds the climate data acquired in the form of columns representing different variables for each row representing a fire in the dataset.

## Conclusion

This project provides a useful tool for analyzing wildfire risk factors by providing relevant weather information from weather stations within established fire regions.
