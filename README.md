# EE_3.07-Geodata-Management-Systems-WS2023-2---Final-Assignment
# EE_3.07 Geodata Management Systems WS2023/24 -  Final Assignment

## 1. Warming Stripes

I am tasked with creating a plot that visually represents the annual temperature data of 45 weather stations in BY, Germany in a warming stripes format. This task requires the use of various Python libraries and techniques such as Pandas, geopandas, seaborn, and data retrieval techniques like FTP.

The first sub-task I need to tackle is selecting weather stations in BY that are still active and started before 1950. To do this, I read the station description file from the historical KL data collection using Pandas. I use the information in this file to filter out the stations that meet my criteria. I ensure that the stations are still active so that I can retrieve the most recent data. Additionally, I make sure that the stations have been operational since before 1950, so I have enough data to analyze.

The second sub-task involves using geopandas to create a geopackage layer with the stations and loading it into QGIS to create a map with Bayern WMS service as the background map. This allows me to locate the stations and see their relative positions on a map. The geopackage layer I create contains the necessary information about the stations such as their IDs and names. I use this information to label the stations on the map and make it easier to identify each station.

The third sub-task involves downloading the annual temperature data for the selected stations automatically from the KL data collection using FTP. This involves writing a Python script that automatically downloads the necessary data based on the station IDs from the station info dataframe. This is an essential step as I need to collect the annual temperature data for the selected stations to analyze and plot them in a warming stripes format.

The fourth sub-task requires using the temperature data from the selected stations to create a warming stripes plot. I can use seaborn, a Python data visualization library, to create the plot. The warming stripes plot visually represents the annual temperature changes at each station over time. The plot displays the temperature data as a series of colored stripes, with each stripe representing a year. The color of each stripe is based on the temperature difference from a reference temperature, with red indicating above-average temperatures, and blue indicating below-average temperatures.

I can copy the relevant code from the notebook [gdms0155_DWD_NRW_5_Warming_Stripes/gdms155_DWD_NRW_5_Warming_Stripes.ipynb] and modify it to suit my needs. This involves adjusting the code to include the 45 selected stations and plotting the annual temperature data from 1950 to 2022. The resulting plot will provide insights into the annual temperature changes at each station, making it easier to compare and contrast the temperature trends.

In summary, the task involves analyzing and visualizing annual temperature changes at weather stations in Bayern, Germany, using warming stripes plots. This requires selecting the appropriate stations, creating a geopackage layer, retrieving the annual temperature data, and using Python libraries such as seaborn to create the plots. This task is essential for understanding the impact of global warming on our climate and for developing strategies to mitigate its effects.

More than that i also improved my warming stripes. With adjusting my code I selected stations omiting stations which are missing more than 95% of the dates that I was interested in analysing.

I ploted new list of stations to QGIS as I did it before.

Then with the use of mathplotlib and seaborn I created new heatmaps and heatmap with inerpolation.

## 2. Digitization: Burial Mounds in Uedemer Hochwald (20 Points)

For Task 2.1, I was required to georeference the picture of the map above. I started with the QGIS project gdms0000_Burial_Mounds_Uedem_V001.qgz in the assignment folder and used the QGIS Georeferencer tool. I combined this with the layer DTK10, which is the NRW topographic map in a 1:10000 scale, already imported from the NRW WMS server and added in the QGIS project. To complete this task, I used crossing forest trails, crossroads, road junctions, and other features I could identify on DTK10 as landmarks (also known as ground control points, GCP) with known coordinates that could be read from the QGIS map canvas. I used EPSG:25832 and added the georeferenced map to the QGIS project.

For Task 2.2, I created a hillshade model from the DTM layer and plotted my georeferenced map partly transparent on top of the hillshade model. By comparing the two, I observed that the burial mounds on the georeferenced map were quite visible.

In Task 2.3, I was asked to use the DTM (not the hillshade model) to measure the typical mound heights relative to their direct environment or neighborhood, rather than the absolute height above sea level. I found that the typical elevation of the burial mounds in the landscape was 0,9m.

Task 2.4 required me to study the hillshade model in the direction of East-North-East of the burial mounds area and search for weakly visible rectangular structures that were not paths. I observed some patterns that seemed to fit this description, and I had a few guesses about their origin. I chose at least one of the structures, digitized it with a polygon, and saved it as a geopackage.

## 3. OpenHygrisC Nitrate Data: Create a Movie with the QGIS Temporal Controller Connected to PostgreSQL / PostGIS (20 Points)

Database creation: With the use of Anaconda i created database and users

Data Preparation: I downloaded and engineered the OpenHygrisC groundwater quality data. I loaded station information and measurement data into the geodatabase, which is stored in PostgreSQL/PostGIS. This data was utilized to create a catalog of substances, which is also stored in the database.

Database Optimization: In the course of the project, I employed several database optimization techniques to improve data retrieval performance. These included creating several indexes, which are used to quickly find data that matches a certain set of criteria. Additionally, I created views in the database, which are stored queries that generally join and project relations. These views are used to simplify and streamline data retrieval.

System Execution: To execute the OpenHypE system, I began by accessing the OpenHyPE git repo, where the relevant code is stored. I read and executed the code to get the system up and running. I added layer of nitrate measurments to QGIS from my SQL database.I utilized the QGIS Temporal Controller to produce a video of Nitrate concentration from the earliest available Nitrate measurement in the early 1960s up to the latest measurement.

## 4. FREE EXERCISE (20 Points)

I created info map of Rheinland area. Added to QGIS map of the NRW. Then I found data about railways, ports, waterways. And implemented this data as to QGIS layers, so it would be visible. In Lables i set names for some of this layers. I tryed to use QGIS Buffer function to analyze, but the circles were to big.

## 5. Video with Explanations. (20 Points) 

https://drive.google.com/file/d/12h1UMGG-G9YWf9gBFq8mpdl7674PaF03/view?usp=sharing
