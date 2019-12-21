---
author: cljim22
comments: true
date: 2013-02-04 16:45:21+00:00
layout: post
link: https://geospatialhistorian.wordpress.com/2013/02/04/gis-and-time/
slug: gis-and-time
title: GIS and Time
wordpress_id: 183
---

_By Jim Clifford_

[From the Otter.](http://niche-canada.org/node/10552)

One of the major weaknesses in using GIS for historical research are the limitations in showing change over time. GIS was designed with geography in mind and until recently historians needed to adapt the technology to meet our needs.

Generally this meant creating a series of maps to show change overtime or as Dan MacFarlane did [last week](http://niche-canada.org/node/10547), include labels identifying how different layers represent different time periods ([see MacFarlane Map2](http://niche-canada.org/files/images/Map2-ModificationsOfHorseshoeFalls.jpg)). More recently, ArcGIS and Quantum GIS introduced features to recognize a time field in data and make it possible to include a time-line slider bar or animate the time series data in a video.

[vimeo http://www.vimeo.com/55720524 w=450&h;=349]

[UK Tallow Imports, 1865-1904](http://vimeo.com/55720524) from [Jim Clifford](http://vimeo.com/user15310735) on [Vimeo](http://vimeo.com).

I am currently studying the sources of raw material imported into Britain during the nineteenth century as a way to connect the environmental consequences of manufacturing in London with the ecological transformations taking place in other parts of the world. One of the first industries I'm studying is soap making. These factories relied on an increasingly global supply of fat (tallow, palm oil, coconut oil, and cottonseed oil), potash, essential (i.e. fragrant) oils, and pine resin. As a part of this research I've started a small database tracing the source of some of these products. Tallow is particularly interesting, as the Russians dominated the trade through to the 1860s, when large herds of cattle and sheep raised on American and Australasia grasslands drove down the price of tallow and led to the collapse of Russian exports to the UK. The most obvious way to visualize this data is to make a graph using the features included in Excel.

[![neoeuropevsrussia](http://www.jimclifford.ca/wp-content/uploads/2012/11/neoeuropevsrussia-1024x513.png)](http://www.jimclifford.ca/wp-content/uploads/2012/11/neoeuropevsrussia-1024x513.png)

I also experimented, using a slightly different dataset, with the [Source Map platform](http://sourcemap.com/), to create a series of maps showing change over time. These maps visualize the changing geography of Britain's tallow supply, but it would be impractical to create or present fifty maps, so they only work to show the general trend using averaged data from three years in the middle of the decades:

**British Tallow Imports 1864-1866(Total imports: £2,737,000)**



**British Tallow Imports 1874-1876 (Total imports: £2,407,000)**



I wanted to see how I could best represent this data in GIS and I also wanted to learn the new [time functions in ArcGIS](http://blogs.esri.com/esri/esritrainingmatters/2010/09/08/mapping-time-in-arcgis-10/). The result is the video (above), showing the changing source of tallow, based on quantity, from 1865 through to 1904. The advantage of this time series video is that it shows the volatility of Britain's tallow supply, with significant booms and busts from each of the regions. Whether this particular animated map provides any insight not available from the Excel graph is up for debate, but the method might become essential as we create significantly larger text mined datasets in the [Trading Consequence](http://tradingconsequences.blogs.edina.ac.uk/) project.

For readers familiar with ArcGIS and who have a copy of version 10, I've include the [Data File](http://www.jimclifford.ca/?attachment_id=567). QGIS has an experimental add-on called [Time Manager](Time Manager), but it might not function properly for the nineteenth century yet. We will try and develop a lesson for this feature in the future, but for now I'll provide instructions for people with copies of ArcGIS. The hardest part of the process was rearranging my data into a format that would work with the ArcGIS time function. First of all, the dates need to be listed in a column, not across the top row. It is possible to cut and past using Excel and switch your rows with your columns, by right clicking and using the "Special Paste" options. Don't use "Date" as the field name as this might confuse the database. I've used "t" instead and included a simple list of years from 1865-1904 (the dates repeat for each location). The other fields I include are the quantity of tallow, a code for the geographic location and the latitude and longitude of where I want the quantities represented on the map.

[![Screenshot from 2012-12-17 11:45:49](http://www.jimclifford.ca/wp-content/uploads/2012/12/Screenshot-from-2012-12-17-114549.png)](http://www.jimclifford.ca/?attachment_id=579)

You can use a spreadsheet program, like Excel, to manipulate this data, but I generally find it is best to save it as a CSV file before importing it into ArcGIS. Once you have a CSV file (or once you've downloaded my tallow_xy.csv file below), you can launch ArcGIS. It would be possible, and perhaps preferable, to create a database table for each location and avoid repeating the dates over and over again for each location, but that would make it more complicated.

Once you launch ArcGIS 10 you can import the CSV using the import XY data option. It should automatically identify the fields called x and y as the spatial data. It will then instruct you to export the data so the program will add a unique identifier number (making it a part of your database). Right click on the layer and chose Export Data. It will then give you the option to add this new layer to the map. If you are using my sample data, I would suggest choosing a simple world map as the base layer. The next step is to tell ArcGIS which field includes the time data. Double click on the layer and find the Time tab in the preferences menu. Choose "t" as the time field and if you click "calculate" it should give you the time range of 1865 to 1904. Do not click the "Display data cumulatively" check box. Next you will need to change the [symbology](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//00s500000034000000) of the layer to display the points as circles that represent the quantity of tallow from each place. I used proportional symbols, but you could also choose graduated symbols. Finally, you need to find the time slider menu button (it has a little clock face). Enable the time slider and it should allow you to slide through the years or click play to see an animation similar to the video above (play with the setting to slow down the animation).

[Data File](http://www.jimclifford.ca/?attachment_id=567)
