---
author: cljim22
comments: false
date: 2019-12-21 16:42:22.757100
layout: page
link: https://geospatialhistorian.wordpress.com/?page_id=1196
published: false
slug: No Content Found
title: No Content Found
wordpress_id: 1196
---





	
  1. **_ Introduction_**


This lesson has two goals.  First, it will introduce you to basic GIS methods and concepts, and provide initial exposure to ArcGIS software.  Second, it will introduce students to HGIS methods and concepts by exploring the spatial distribution of population in the Great Plains in the past.

The map and attribute data employed here are publicly available from the National Historical GIS project based at the University of Minnesota.  That project created map layers at various scales (nation, state, county, census tract, etc.) to correspond with the decennial U.S. censuses for years ending in 0 from 1790 until 2000.  You can download census statistics and corresponding maps, designed for use in a GIS or in statistical software, from [**http://www.nhgis.org**](http://www.nhgis.org/).

This project will walk you through the process of loading GIS data, joining attributes to maps, and symbolizing maps based on those attribute data.  It will enable you to explore historical questions about the spatial distribution of people of different ethnic backgrounds in the past.  You will learn how to create printable maps that answer descriptive historical questions.



	
  * **Download ****zip ****and save **in your **Documents\ArcGIS **folder (make sure you unzip the folder). The final file path should be** C:\Users\<username>\ArcGIS\ArcGIS_Lesson1**.


![](http://www.nhgis.org.” Drag the box to the bottom of the page so that it doesn’t overlap with any other map elements.When the layout is arranged to your satisfaction, you are ready to export your map.  You could, at this point, print a paper copy.  Instead, for today, we will export the map as a .jpg image that could be imbedded into a Word document, uploaded to a web site, or used in a PowerPoint presentation. From the menu bar, select File > Export Map. Navigate to ArcGIS_Lesson1\OutputMaps and name your file Norwegian1930.jpg. Set Save as type: to JPEG (*.jpg)



	
  1. **_ Open ArcMap_**



	
  * From your computer desktop (or **Start Menu **> **ArcGIS**), open the **ArcMap** software


Note there are a number of programs in the ESRI GIS package, including ArcCatalog and ArcGlobe, but you will mostly use ArcMap. Begin by saving a new map document.

	
  * Click **File **>** Save** (or **Ctrl-S**) and save to **ArcGIS_Lesson1\ProjectFiles **and call it**mxd**.


**_Key concept: _**_In GIS work it is important to pay close attention to where on the computer you save files.  The program you see on your screen does not read just a single file, like a Microsoft Word document or a PowerPoint presentation does.  Instead, it refers to multiple underlying files, sometimes dozens or even hundreds of files.  The software has to know where to find those files by means of their **path**.  Moving files after the fact or changing the names of directories can cripple a GIS project, although it can be mended.  It is preferable to set up a directory structure before you start a GIS project, then stick with it.  For this exercise, a directory structure is already in place for you._

**_Note:_** _The ArcGIS software has a tendency to crash now and again; you will save yourself a lot of frustration if you get into the habit of saving your work periodically.  Click the **Save** button (or Ctrl-S) to save your work about every 5 minutes throughout the exercise.  If you do not remember this advice now, you may be reminded the hard way later…_**_
_**



	
  1. **_ Load map data_**


**_Key concept: _**__Spatial data___ represent geographic features in a similar way to familiar paper maps.  We will start with vector map data, which come in three different forms:  points, lines, and polygons.  This exercise makes use of polygon map data in a vector format. You could use graphics software to draw maps with lines, points and polygons. What distinguishes vectors features in a GIS is they represent places on the earth with known coordinates. Each point is a pair of coordinates (latitude and longitude, or X and Y). Lines and polygons are created by stringing together points, so they are also grounded with known coordinates. This makes it possible to automatically add vector data as layers and have them all line up to create maps._



	
  * In ArcMap click the **Add Data** button  .

	
  * Browse to the **Documents\ArcGIS\ArcGISLesson1** folder you created earlier, making sure to highlight the “ArcGIS_Lesson1” folder (single click) rather than expanding it (or double-clicking on the “GIS_Demo1.gdb” folder.

	
  * Double-click on the geodatabase called **gdb**.



	
  * Select the datasets (or Feature Classes) called **GP_county_1930** and **GP_states_1930**.  Hold down the **Ctrl** key to select both at the same time, then click the **Add** button.


![GISdemo1](https://geospatialhistorian.files.wordpress.com/2014/11/gisdemo1.png)

On the left side of your screen in the **Table Of Contents** (TOC) two new layers appear with check marks next to them.  One is **GP_county_1930** and the other is **GP_states_1930**.  Each has a coloured box below it.  On the right side of your screen, in the map view, appears a corresponding map of all of the counties and the 12 Great Plains states as they existed in 1930.

![GISlesson1_tableofcontents](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_tableofcontents.png)

You can’t see the the Great Plains states layer because the county layer is covering it up.



	
  * Uncheck the box next to **GP_county_1930**.


Now you can see the **GP_states_1930** map layer.

**_Key concept: _**_in ArcMap, __GIS data is referred to as a _Feature Class_, meaning a collection of similar features, that share similar attributes, and that have a similar geometry type (point, line, polygon). The data is stored independently from the map. When added to the map, GIS data appear as _layers_ of map features that can each be manipulated and symbolized independently. When saving your map document (*.mxd file), it does NOT contain any data; it merely remembers where the source data is located and how to display it on the screen._

**_III. Symbolize and arrange map layers_**



	
  * Check and uncheck the boxes next to the two layers to turn them on and off.

	
  * Check both to turn both layers on.  Click the icon in the top left corner of the **TOC** to **List By Drawing Order **.  Then click and hold on the **GP_states_1930**layer and drag it above the **GP_county_1930**  When you release the mouse button it moves to the top of the list.


Now you will “symbolize” (change the graphic representation) of the **GP_states_1930** layer so that it complements the **GP_county_1930** layer, rather than obscuring it.



	
  * Click on the coloured box beneath **GP_states_1930**. The **Symbol Selector** dialog appears.

	
  * Select the **Hollow box** Make the **Outline Color** black and the **Outline Width** = 2.

	
  * Click **OK**.


Notice how the symbol box has changed.

![GISlesson1_symbol_selector](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_symbol_selector.png)

Now you can see both map layers at the same time.  **GP_states_1930** appears as an outline only, without any fill colour, while **GP_county_1930** retains its fill colour. The state boundaries make it easier to distinguish which counties are within which state.



	
  1. **_ Load attribute data_**


**_Key concept: _**__Attribute data___ are digitized descriptions of geographic places.  Examples of attributes include things like the total population of a county (polygon), the speed limit along a section of road (line), or the temperature at a given time at a weather station (point).  Attribute data can be numeric or text. The list of possible attributes about the world is infinite.  In this exercise we employ attribute data taken from the U.S. Census of Population about all counties in the Great Plains states._

Click the **Add Data** button again ![add_data](https://geospatialhistorian.files.wordpress.com/2014/11/add_data.png)
