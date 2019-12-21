---
author: cljim22
comments: true
date: 2014-11-27 21:59:36+00:00
layout: page
link: https://geospatialhistorian.wordpress.com/lessons/arcgis-lesson-5-overlay-analysis/
slug: arcgis-lesson-5-overlay-analysis
title: 'ArcGIS Lesson 5: Overlay and Spatial Analysis'
wordpress_id: 926
---

[Please Leave Comments and Suggestions for Revisions]

by Geoff Cunfer with Jessica DeWitt, revised by Louis-Jean Faucher


## **Introduction**


The power of historical GIS is partly its ability to “overlay” or simultaneously display multiple layers of spatial information in a dynamic mapping environment. Beyond displaying spatial information, the software allows us to query and analyze large amounts of data in relation to each other across space and time.

[caption id="attachment_938" align="alignnone" width="300"][![A common visual example of the utility of GIS, layering spatial information.](https://geospatialhistorian.files.wordpress.com/2014/11/esri-data_themes_as_layers.gif?w=300)](https://geospatialhistorian.files.wordpress.com/2014/11/esri-data_themes_as_layers.gif) A common visual example of the utility of GIS, layering spatial information.[/caption]

This tutorial will guide you through the process of adding multiple forms of data (aerial photographs, parcel-level land use vectors, and county-level agricultural data) to a GIS and conducting spatial analysis on the data those layers contain. We will learn how to manipulate features in layers and create new feature classes based on their attributes and their spatial relationships.


The aerial photographs and matching GIS layers used in this exercise were collected, geo-referenced, and digitized by the Great Plains Population and Environment Project led by Dr. Myron Gutmann at the University of Michigan.  They represent a sample of land cover in Weld County, Colorado at five time points between 1938 and 2006.





## **I. Getting Started**





	
  * Download [the zipped file](https://drive.google.com/open?id=0ByEStot3aAG_N0ROdVFLT051M0U) and save in your **Documents\ArcGIS** folder (make sure you unzip the folder).

	
  * From your computer desktop open the **ArcMap** software.


Begin by saving a new project file

	
  * Click **File **>** Save** (or **Ctrl-S**) and save to **ArcGIS_Lesson5\ProjectFiles **called **mxd**.




## **II. Add Reference Data**





	
  * In ArcMap click the **Add Data** ![lesson5image003](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image003.png) button

	
  * Navigate to **ArcGIS_Lesson5\** **AirPhotoImages** folder and select the following 5 raster images of scanned aerial photos from Weld County, Colorado:


_![lesson5image005](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image005.png)_

Your screen should look like this:

![lesson5image007](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image007.png)



	
  * Click the **Add Data** button

	
  * Navigate to **ArcGIS_Lesson3\****gdb** geodatabase and select the following 5 polygon feature classes, digitized from the same images:




![lesson5image009](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image009.png)

The air photo and polygon layers will look like this:

![lesson5image011](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image011.jpg)

Symbolize the polygon layers so that they have no fill and red outlines.



	
  * From the** Table Of Contents** (TOC), change the symbol of the layers to the **Hollow box** symbol, making the **Outline Color** red and the **Outline Width** = 1, then click **OK**.


![lesson5image013](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image013.jpg)

Navigate to **ArcGIS_Lesson3\****Overlay1.gdb** geodatabase and select the following polygon feature classes from the county-level census of agriculture:

![lesson5image015](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image015.png)

**_III. Explore and organize your data_**

The layers may have been added to the TOC in a random order. Remember that layers at the bottom of the list are drawn first, with those on top drawn over them.



	
  * Turn layers on and off to see others hidden beneath.

	
  * Zoom in and out, and pan around to explore your data.

	
  * In the TOC, click and drag the layers to rearrange them into a chronological order.


![lesson5image017](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image017.png)



	
  * Click **File **>** Save** (or **Ctrl-S**) to save the current state of your map.


Match up aerial photo-land cover pairs and consider the photo interpretation and digitizing work. For example:

	
  * Turn off all layers, then turn on **jp2** and **Weld_1950s** only.

	
  * Zoom in to one of the parcels of land.


Evaluate the digitizing job. Would you have drawn the visible features any differently?

Use the **Identify** button ![lesson5image019](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image019.png) to check the land cover classification for a handful of parcels. Are they correct?

![lesson5image021](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image021.png)

Look at the attribute tables for the polygon layers and try to understand the information they contain.

![lesson5image023](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image023.png)

**_Note_**_: Scale is a very important concept in GIS.  Here we have datasets at 2 very different scales.  The AgCensus layers come from information reported at the county level.  They cover a huge area – more than 1000 counties – but don’t provide much detail about individual farms or fields.  They allow you to analyze land use at a relatively coarse level but for a large area (small scale).  The land cover layers come from aerial photos with information at a much finer level of detail.  They allow you to evaluate land use at a very fine level but for a small area (large scale). But imagine trying to digitize aerial photos for all portions of the entire 1000+ counties(!).  On this project we adopted a sampling strategy, randomly selecting 8 cells in each of 50 counties. The result is a GIS database of 400 cells at very fine resolution (large scale), but with a lot of blank spaces on the map. The trade-off between small vs large scale is coverage vs detail, which translates to time and cost._


## **IV. Selecting features based on their attributes**


One of the most basic analysis tool often used to explore the spatial patterns in your datasets is called **Select By Attributes**. Since your layer is linked to an attribute table, it is possible to quickly and efficiently select all features that share common values. This can help you answers questions such as:



	
  * Where is cropland?

	
  * Where is grassland?

	
  * Where is developed land?


First, turn off all layers except the 1930 photo and land cover pair.
Next you will generate a selection statement instructing the software which features to select based on the criteria provided.

	
  * Click on the menu **Selection** > **Select By Attributes…** The following box will appear:


![lesson5image025](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image025.png)

This is where you will write your selection statement; the dialog will help you generate most of it.

**_Key concept_**_: The “language” used in this dialog is called Structured Query Language (or SQL). It adheres to a strict syntax which is commonly used to query and manipulate relational databases containing many tables with millions of records. The Select By Attributes tool contains a simplified version of SQL. The first part of the selection statement is already written out as “SELECT * (meaning everything) FROM <the target layer> WHERE:”. You are only required to complete the “where” clause by providing 3 elements: a field name, an operator, and a value. For instance, you could complete the statement with “Land_use = ‘Cropland’” or “SHAPE_Area > 5000”._

In the dialog, make sure the parameters are set as follows:

Layer:  **Weld_1930s**
Method:  **Create a new selection**

Then:



	
  * Double-click on **Land_cover_1930** in the list of attributes. Note that it appears in the window below.

	
  * Click on the **=** Note that it is added in the window below.

	
  * Click the **Get Unique Values**


This shows all the Land Cover types from the attribute table.

	
  * Double-click on **21 - Cropland**. Note that it is also added in the window below.


In the bottom window of the **Select By Attributes** dialog you should now have a properly specified SQL statement that reads as follows, as illustrated:


Select * FROM Weld_1930s WHERE: **Land_cover_1930 = 21**


![lesson5image027](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image027.png)



	
  * Click **Apply** (clicking OK closes the dialog whereas clicking Apply leaves it open).


Some of the polygons on your map will be highlighted blue to show they are selected.

![lesson5image029](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image029.jpg)

Explore your maps and get a sense of where there is cropland where there is not.

Use the **Select by Attribute** dialog box to select other land covers, and then to explore the same variables in other layers.  For example, you could, one by one, select developed land in each of the 5 years, then click yearly layers on and off to follow their change through time.

**_Tip_**_: If you make an error in the dialog box code, it is better to clear the form completely (using the **Clear** button) and to start over.  Correct syntax in the code is very sensitive, and even a one letter difference can cause an error message._

**_Note_**_: __Data exploration of this sort is more an art than a science, but it often raises important research questions, reveals surprising patterns, and sometimes delivers quick answers to things you’ve been wondering about.  This is typically a very creative process, as your mind wonders about patterns, their causes and consequences, and how they’ve changed over time.  In essence, you are taking a vast amount of raw data that our brains cannot evaluate, and visualizing it in a way that our brains can understand.  After the long effort of creating or digitizing GIS data, the data exploration phase is sometimes the most fun, where you first discover answers to questions you’ve been pursuing for a long time._


## **V. Select by location**


So far you have selected features based on their attribute values.  You can also select features based on their location and how they interact with other features.  In this scenario, we’ll ask the following question:



	
  * Which polygons within 10 meters of a road are cropland?


First, you’ll select a subset of road features and then export them as a new feature class.

	
  * Repeating the instructions outlined in step IV above, use the **Select by Attribute** dialog to select all features from the **Weld_2000s** land cover layer with a **Land cover** type **equal** to **14 - Transportation**.

	
  * Right-click on the Weld_2000s layer in the TOC and select **Data** > **Export Data**.


In the dialog, make sure the parameters are set as follows:


Export:
**Selected features**




Use the same coordinate systems as:
**this layer’s source data**


Output feature class:
**..\Overlay1.gdb\Weld_2000_Transportation**

![lesson5image031](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image031.png)

By default, the Output Feature Class is called **Export_Output**, which is a generic name, and the output data type is Shapefile. You will change both.



	
  * Click on the **Browse** button ![lesson5image033](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image033.png) to specify where the output feature class will be located.

	
  * Browse to the **ArcGIS_Lesson5\Overlay1.gdb**


You may not be able to see Overlay1.gdb since the default data type is set to Shapefile.

	
  * Make sure to set the **Save as type** to **File and Personal geodatabase feature classes**.


![lesson5image035](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image035.png)



	
  * Double-click on **gdb**

	
  * Type the value for **Name** as **Weld_2000_Transportation**.

	
  * Click **Save**.


![lesson5image037](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image037.png)



	
  * Click **OK** in the **Export Data**


When asked whether you would like to add the exported data to the map as a layer click **Yes**.  You’ve now created a new feature class of only the road polygons.  Explore it on the map.

![lesson5image039](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image039.jpg)

You will now use this new layer as a reference to perform a “spatial selection”. Make sure you have the year 2000 aerial photo and land cover pair turned on, as well as the new Weld_2000_transportation layer.



	
  * Click on menu **Selection** > **Select By Location…**


In the dialog, make sure the parameters are set as follows:


Selection method:
**select features from**




Target layer(s):
**Weld_2000s**




Source layer:
**Wels_2000_transportation**




Spatial selection method:
**are within a distance of the source layer feature**




Apply a search distance
**10 Meters**


![lesson5image041](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image041.png)

You are instructing the software to select all polygons from Weld_2000s that are within 10 meters of any of the polygons in the Transportation layer.



	
  * Click **OK** and inspect the results.


You’ve now selected features of any type that are within 10 meters of a road. Now let’s say you only wanted the cropland features. To narrow down the results, we will use the **Select By Attributes** tool again.



	
  * Click on **Selection** > **Select By Attributes…**


In the dialog, make sure the parameters are set as follows:


Layer:
**Weld_1930s**




Method:**
Select from current selection.**


This will apply the new selection to the currently selected features, rather than starting over with all features.



	
  * Repeat the instructions outlined in step IV above to select features from the **Weld_2000s** land cover layer with a **Land cover** type **equal** to **21 - Cropland.**


![lesson5image043](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image043.png)

The result is a selection of all polygons that are BOTH within 10 meters of a road AND cropland.

![lesson5image045](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image045.jpg)

**_Tip_**_: GIS analysis can quickly become complex, and it is important to think through the logical order of each step in advance.  Here you started with a selection of Transportation features, then exported them as a new layer.  Next, you conducted a spatial selection to identify features near roads, and then an attribute selection to further select cropland features only.  The order of steps can become like a puzzle. I__f you ever get mixed up during your selection process and are unsure of which features have been selected, it is often best to click on the Clear Selected Features button __ and start over again.  People sometimes use flow chart diagrams to model the key steps.  For complex analyses, take notes so you can record your methodology if you ever need to repeat it or to explain it in a footnote or appendix._


## **VI. Overlay analysis**


Overlay analysis allows you to compare both attribute and location information about multiple map layers.  It is one of the most powerful components of GIS.  For historical GIS, overlay allows you to analyze two different historical sources, for example a map of land use created by a government agency with an aerial photo taken at about the same time.  Or, it allows you to analyze change over time by comparing similar sources created a different points in time.  Here we’ll do the latter, comparing digitized aerial photos from the 1930s with those from the 2000s.

**_Key concept_**_: Esri uses the term “Geoprocessing” to designate a vast collection of tools that are used to manipulate, transform and create data and feature classes. There are over a thousand such tools, some highly specialized, but you will only ever need to use a handful of the most common ones. The complete collection of tools can be found in the Catalog window (menu Windows > Catalog) under “System Toolboxes”._

![lesson5image049](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image049.png)

Some of the most commonly used tools are accessible via the **Geoprocessing** menu:



	
  * Buffer

	
  * Clip

	
  * Intersect

	
  * Union

	
  * Merge

	
  * Dissolve


To find out more about these tools, Click on the **Help** > **ArcGIS Desktop Help** menu. Type in each of the above tool’s name one by one.  For the first 4 click on the “…(Analysis)” link and read the Summary, Illustration, and Usage sections of each.  For the last two, do the same, selecting the “..(Data Management)” link.  In each case, think about what happens to the attribute information when these actions are performed.

**Question**:



	
  * Which areas have ever been used for cropland?


To answer this question we’ll use the **Union** tool.



	
  * Click on **Geoprocessing** > **Union**.

	
  * Click the **Input Features** dropdown box and select, one at a time, all five of the land cover layers. As you add each one it will appear in the list of **Features**.


**_Tip_**_: By default, the **Output Feature Class** created by geoprocessing tools is stored in a generic “Default.gdb” geodatabase and its name will be the same as one of the inputs with a suffix such as “**_Union**”. If you were to run the tool again, the suffix would become “**_Union1**” and the next time it would be “**_Union2**”, which can quickly become confusing. For this reason, it is best to pay attention to the folder location where the output is created, and to give it a meaningful name that you will easily recognize in the future._



	
  * Change the default **Output Feature Class** FROM: ..\Documents\ArcGIS\Default.gdb\Weld_1930s_Union1


![lesson5image051](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image051.png)



	
  * TO: ..\Documents\ArcGIS\ArcGIS_Lesson5\Overlay1.gdb\Weld_1930_to_2000_Union


![lesson5image053](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image053.png)



	
  * Click **OK**.


Be patient – ArcGIS is busy “cookie-cutting” all your polygons which can take a little while. It might not even look like the program is doing anything at first, but eventually a small window will pop-up at the bottom right of the screen with a green box and a check mark in it (a red X would indicate an error occurred). Your new layer will appear in the table of contents. Inspect the results. It will look a bit messy, with lots of little slivers and tiny polygons.

![lesson5image055](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image055.jpg)



	
  * Zoom in close to see some of them.

	
  * Right-click > **Open Attribute Table** on **Weld_1930_2000_Union** and inspect its content.


As you scroll across the table, you’ll see each of the attributes repeated 5 times (with unfortunate numerical suffixes generated by the software), once for each layer you input.

Now that we’ve created a single feature class with each distinct geographical space that existed in the 5 aerial photos, it is time to select every polygon that was _ever_ cropland. In GIS terms, we want to select every polygon for which the Land Use attribute was 21-Cropland in any one or more of the 5 time points. To do this we’ll use the Select by Attributes dialog box, but with a more complex selection statement than before.



	
  * Click on **Selection** > **Select by Attributes** and set the parameters as follows:


Layer: **Weld_1930_2000_Union
**Method: **Create a new selection**.



	
  * Click the **Clear** button to remove the statement in the window at the bottom, if necessary.


Scroll down in the list of attributes, and you’ll see that the Land_cover attribute we are interested in repeats, with a unique year for each.

Double-click on each **Land_cover__yyyy_** field and add **= 21**, with **OR** between each one, to create the following statement:


Select * FROM Weld_1930_2000_Union WHERE:
**Land_cover_1930 = 21 OR Land_cover_1950 = 21 OR Land_cover_1970 = 21 OR Land_cover_1990 = 21 OR Land_cover_2000 = 21**


![lesson5image057](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image057.png)

You may click **Get Unique Values** for each of the Land_cover field, or you may type the values in the window directly, at the risk of making a typo. If you make a mistake, click the **Clear** button and start over.



	
  * When you’re done, click **OK**.


You have now selected every area (in blue) that was ever plowed between the 1930s and 2000s.

![lesson5image059](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image059.jpg)

**_Note_**_:  For this query we use OR because we want each polygon that was cropland at least _once_.  If we used AND instead, we would select only polygons that were cropland in _every_ one of the 5 years.
This AND / OR type of selection is the called “boolean logic”._

Now that you’ve selected all the parcels that were in cropland at least once, you have the answer to our research question: “Which land areas have ever been used for cropland?”

You can now do some simple analysis with this query result, such as summarizing the spatial data for each variable.



	
  * If it is not still open, right-click > **Open Attribute Table** on **Weld_1930_2000_Union** and note how many rows are selected (blue).


The total number of selected features is given in parenthesis at the bottom of the attribute table.

	
  * Scroll to the far right, until you see the field named **Shape_Area**.


This attribute is generated and its value updated automatically by ArcGIS showing the area (in map units) of each parcel in your layer. We want to know the total area of all the selected (cropland) parcels.

	
  * Right-click on the field heading for **Shape_Area** and click on **Statistics**.


![lesson5image061](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image061.png)

This produces a summary and frequency distribution for the field Shape_Area. You can change the summary to any other numerical field in the first drop down box.

The **Count** is the number of features selected (this will be the same as the number in parenthesis at the bottom of the attribute table). The other statistics are the **Min**, **Max**, **Sum**, **Mean**, and **Standard Deviation** for the selected features. The answer to the question: “How much land was ever in cropland” in the study area is the **Sum** value.

![lesson5image063](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image063.png)

**_Tip_**_: This feature class’ measurement unit is metres. In this case, the area calculated by ArcGIS is in square metres, which you can divide by 1,000,000 to get square kilometres.  If you wish for the units to be in hectares or acres you will have to apply a conversion calculation such as provided by the built in Google unit converter. For your convenience: 1 sq km = 100 ha = 247.105 ac._

You may wish to explore the data further to answer a different question such as:



	
  * Which land areas have _only_ been used for cropland?


Let’s repeat some of the same steps as above but with a small change:

	
  * Open the **Select By Attributes** dialog and change the selection statement you applied to replace all **OR**s with **AND**

	
  * In the **Table** window, right-click on the field heading for **Shape_Area** and click on **Statistics**.


Notice how the values for **Count** and **Sum** have decreased significantly.

![lesson5image065](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image065.png)

Continue exploring different selection methods using against different attribute values to see how the resulting selection changes.


## **VII. Create a new Buffer feature class**


In step V above you applied a spatial selection using a distance of 10 metres. The software used that parameter in its calculation but never displayed that distance visually. Imagine you wanted to display that as a layer in your map. You will now use the **Buffer** geoprocessing tool to create a new feature class.



	
  * Click on Geoprocessing > Buffer. The tool’s dialog appears.

	
  * Click the **Input Features** dropdown box and select Weld_2000_Transportation.

	
  * Set the Output Feature Class to **gdb\Weld_2000_Transportation_buffer_10m**


![lesson5image067](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image067.png)



	
  * Click **OK**.


ArcGIS is busy generating new features that extend 10 metres from the input ones. Processing is complete when the window pops-up at the bottom right of the screen with a green box and a check mark in it. Your new layer will appear in the table of contents.

	
  * Drag and drop the **Weld_2000_Transportation_buffer_10m layer** so it displays on top of the **Weld_2000_Transportation** Change the symbology to make the layers easy to see.


Examine it to see what 10m actually looks like at your analysis scale. You now have a new buffer feature class that can be added to other maps as a layer.

![lesson5image069](https://geospatialhistorian.files.wordpress.com/2014/11/lesson5image069.png)
