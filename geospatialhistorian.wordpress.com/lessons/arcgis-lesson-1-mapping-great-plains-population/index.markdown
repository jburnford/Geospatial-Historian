---
author: cljim22
comments: true
date: 2014-11-27 21:53:11+00:00
layout: page
link: https://geospatialhistorian.wordpress.com/lessons/arcgis-lesson-1-mapping-great-plains-population/
slug: arcgis-lesson-1-mapping-great-plains-population
title: 'ArcGIS Lesson 1: Mapping Great Plains Population'
wordpress_id: 915
---

[Please Leave Comments and Suggestions for Revisions]

Created by Geoff Cunfer, revised by Louis-Jean Faucher


## **Introduction**


This lesson has two goals.  First, it will introduce you to basic GIS methods and concepts, and provide initial exposure to ArcGIS software.  Second, it will introduce students to HGIS methods and concepts by exploring the spatial distribution of population in the Great Plains in the past.

The map and attribute data employed here are publicly available from the National Historical GIS project based at the University of Minnesota.  That project created map layers at various scales (nation, state, county, census tract, etc.) to correspond with the decennial U.S. censuses for years ending in 0 from 1790 until 2000.  You can download census statistics and corresponding maps, designed for use in a GIS or in statistical software, from [**http://www.nhgis.org**](http://www.nhgis.org/).

This project will walk you through the process of loading GIS data, joining attributes to maps, and symbolizing maps based on those attribute data.  It will enable you to explore historical questions about the spatial distribution of people of different ethnic backgrounds in the past.  You will learn how to create printable maps that answer descriptive historical questions.



	
  * **Download ****[zip](https://drive.google.com/open?id=0ByEStot3aAG_cFVIcFJsM3p1TTg) ****and save **in your **Documents\ArcGIS **folder (make sure you unzip the folder). The final file path should be** C:\Users\<username>\ArcGIS\ArcGIS_Lesson1**.





## I. Open ArcMap





	
  * From your computer desktop (or **Start Menu **> **ArcGIS**), open the **ArcMap** software


Note there are a number of programs in the ESRI GIS package, including ArcCatalog and ArcGlobe, but you will mostly use ArcMap. Begin by saving a new map document.

	
  * Click **File **>** Save** (or **Ctrl-S**) and save to **ArcGIS_Lesson1\ProjectFiles **and call it**mxd**.


**_Key concept: _**_In GIS work it is important to pay close attention to where on the computer you save files.  The program you see on your screen does not read just a single file, like a Microsoft Word document or a PowerPoint presentation does.  Instead, it refers to multiple underlying files, sometimes dozens or even hundreds of files.  The software has to know where to find those files by means of their **path**.  Moving files after the fact or changing the names of directories can cripple a GIS project, although it can be mended.  It is preferable to set up a directory structure before you start a GIS project, then stick with it.  For this exercise, a directory structure is already in place for you._

**_Note:_** _The ArcGIS software has a tendency to crash now and again; you will save yourself a lot of frustration if you get into the habit of saving your work periodically.  Click the **Save** button (or Ctrl-S) to save your work about every 5 minutes throughout the exercise.  If you do not remember this advice now, you may be reminded the hard way later…_


## **II. Load map data**


**_Key concept: _**__Spatial data___ represent geographic features in a similar way to familiar paper maps.  We will start with vector map data, which come in three different forms:  points, lines, and polygons.  This exercise makes use of polygon map data in a vector format. You could use graphics software to draw maps with lines, points and polygons. What distinguishes vectors features in a GIS is they represent places on the earth with known coordinates. Each point is a pair of coordinates (latitude and longitude, or X and Y). Lines and polygons are created by stringing together points, so they are also grounded with known coordinates. This makes it possible to automatically add vector data as layers and have them all line up to create maps._



	
  * In ArcMap click the **Add Data** button  [![add_data](https://geospatialhistorian.files.wordpress.com/2014/11/add_data.png)](https://geospatialhistorian.files.wordpress.com/2014/11/add_data.png).

	
  * Browse to the **Documents\ArcGIS\ArcGISLesson1** folder you created earlier, making sure to highlight the “ArcGIS_Lesson1” folder (single click) rather than expanding it (or double-clicking on the “GIS_Demo1.gdb” folder.

	
  * Double-click on the geodatabase called **gdb**.

	
  * Select the datasets (or Feature Classes) called **GP_county_1930** and **GP_states_1930**.  Hold down the **Ctrl** key to select both at the same time, then click the **Add** button.


[![GISdemo1](https://geospatialhistorian.files.wordpress.com/2014/11/gisdemo1.png)](https://geospatialhistorian.files.wordpress.com/2014/11/gisdemo1.png)

On the left side of your screen in the **Table Of Contents** (TOC) two new layers appear with check marks next to them.  One is **GP_county_1930** and the other is **GP_states_1930**.  Each has a coloured box below it.  On the right side of your screen, in the map view, appears a corresponding map of all of the counties and the 12 Great Plains states as they existed in 1930.

[![GISlesson1_tableofcontents](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_tableofcontents.png)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_tableofcontents.png)

You can’t see the the Great Plains states layer because the county layer is covering it up.



	
  * Uncheck the box next to **GP_county_1930**.


Now you can see the **GP_states_1930** map layer.

**_Key concept: _**_in ArcMap, __GIS data is referred to as a _Feature Class_, meaning a collection of similar features, that share similar attributes, and that have a similar geometry type (point, line, polygon). The data is stored independently from the map. When added to the map, GIS data appear as _layers_ of map features that can each be manipulated and symbolized independently. When saving your map document (*.mxd file), it does NOT contain any data; it merely remembers where the source data is located and how to display it on the screen._


## **III. Symbolize and arrange map layers**





	
  * Check and uncheck the boxes next to the two layers to turn them on and off.[![GISlesson1_listbydrawingorder](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_listbydrawingorder.png)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_listbydrawingorder.png)

	
  * Check both to turn both layers on.  Click the icon in the top left corner of the **TOC** to **List By Drawing Order **.  Then click and hold on the **GP_states_1930** layer and drag it above the **GP_county_1930** layer.  When you release the mouse button it moves to the top of the list.


Now you will “symbolize” (change the graphic representation) of the **GP_states_1930** layer so that it complements the **GP_county_1930** layer, rather than obscuring it.



	
  * Click on the coloured box beneath **GP_states_1930**. The **Symbol Selector** dialog appears.

	
  * Select the **Hollow box** Make the **Outline Color** black and the **Outline Width** = 2.

	
  * Click **OK**.


Notice how the symbol box has changed.

[![GISlesson1_symbol_selector](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_symbol_selector.png?w=625)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_symbol_selector.png)

Now you can see both map layers at the same time.  **GP_states_1930** appears as an outline only, without any fill colour, while **GP_county_1930** retains its fill colour. The state boundaries make it easier to distinguish which counties are within which state.


## **IV. Load attribute data**


**_Key concept: _**__Attribute data___ are digitized descriptions of geographic places.  Examples of attributes include things like the total population of a county (polygon), the speed limit along a section of road (line), or the temperature at a given time at a weather station (point).  Attribute data can be numeric or text. The list of possible attributes about the world is infinite.  In this exercise we employ attribute data taken from the U.S. Census of Population about all counties in the Great Plains states._



	
  * Click the **Add Data** button again [![add_data](https://geospatialhistorian.files.wordpress.com/2014/11/add_data.png)](https://geospatialhistorian.files.wordpress.com/2014/11/add_data.png). Inside **GIS_Demo1.gdb** select the dataset called **GP1930pop**.

	
  * Click the **Add**


A new data table appears in the TOC, but this time there is no layer corresponding to it in the map display.

[![GISlesson1_GPpop1930](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_gppop1930.png)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_gppop1930.png)



	
  * Right-click on the table called **GP1930pop**and select **Open**.


A table called **GP1930pop** opens in the **Table** view; it looks much like a spreadsheet.  Each row (or record) represents one county in the 12 Great Plains states.  Each column (or attribute / variable) represents one type of information about those counties.

[![GISlesson1_1930pop_attributetable](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_1930pop_attributetable.png?w=625)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_1930pop_attributetable.png)



	
  * Explore the data table by scrolling up and down and left and right.


The State and County attributes correspond to the location that each row represents.  The column headings (or variable names) across the top indicate what information about those places is available in this dataset. Individual cells contain numerical or textual data.  This selection of data from the 1930 US Census includes information about

	
  * total population

	
  * sex

	
  * race

	
  * age

	
  * rural or urban residence

	
  * tenure of farms

	
  * country of birth for the foreign-born population


This data table will help us characterize the population of each county and understand the demographic structures of different places in the Great Plains.


## **V. Join map data and attribute data**


At the moment, ArcMap represents the location of all of the counties in the Great Plains states.  And the map contains a table of information (attributes) about all of those counties.  But the program does not yet know those two sets of information are related.

**_Key concept: _**_One significant power of GIS stems from the ability to connect map data and attribute data.  This _connection_ process is what separates GIS as an analytical tool from database and graphics software.  A database program can manipulate attribute data in sophisticated ways.  A graphics program can make beautiful maps.  But only a GIS can bring together the maps with the attributes so that researchers can analyze the spatial relationships of attribute data._

The map layers do have some attributes already built in.



	
  * Right-click on the **GP_county_1930** layer and select **Open Attribute Table**.


A similar data table called **GP_county_1930** appears in the **Table** window.  This table looks a lot like the other one, with several columns of attribute data and a row for every county feature.  There are 17 attribute columns, all with different kinds of identification information.



	
  * Scroll right and left through the columns


This table doesn’t contain much information of substance about the characteristics of each county. The crucial difference between the two tables is that **GP_county_1930** is displayed in the map while **GP1930pop** one is not.



	
  * Resize and drag the **Table** window so that it doesn’t obscure the map.

	
  * In **GP_county_1930, **click on one of the small gray boxes to the far left of the table window.


Doing so highlights a row in the table that represents a single county _and_ highlights the corresponding county feature on the map.  If you want to know where any given county is, click on the adjacent gray box in the table to select it.

[![GISlesson1_1930county_attributetable](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_1930county_attributetable.png?w=625)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_1930county_attributetable.png)



	
  * Before going to the next step, click on the **Clear Selection** button ![GISlesson1_clear_selection](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_clear_selection.png) located below the **Add Data**


Note that you can toggle between the two tables you have open by clicking on the tabs in the bottom left of the **Table** window.  [![GISlesson1_1930county_attributetable2](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_1930county_attributetable2.png)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_1930county_attributetable2.png).

Notice that one column is identical in both tables: **GISJOIN**. This variable presents a unique ID code for each county.  Custer County, Colorado has the code 800270 in both tables, for example.  These unique IDs will allow ArcMap to join the data table with census information to the layer attribute table so that the program can connect locations on earth with attributes describing those locations. Note that the matching attributes in the two tables do NOT need to have the same name, but they DO need to contain equal values of similar type (number to number, text to text) for the connection to work.



	
  * In the TOC, right-click on **GP_county_1930**and select **Joins and Relates** > **Join**.


The **Join Data** dialog appears, which will allow you to connect the Census data to the map layer.



	
  * Make the following selections in the dialog box and click **OK**.


[![GISlesson1_join_data](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_join_data.png)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_join_data.png)

The table called **GP1930pop** has not changed.  Close it.  Inspect the table called **GP_county_1930**.  All of the 17 original columns are still there.  Scroll to the right in the table.  All of the census data are now also present in the layer’s attribute table.  Now when you click on a gray box on the left side of the table, selecting both the row and a county on the map, you can determine how many people lived in that county in 1930, how many were male and female, what their age and racial structures were, etc.  The join procedure has connected the map data with attribute data about the map features, in this case counties. Note that this connection is ephemeral and is only temporarily stored in your map document.

To make this join permanent, you need to export the map layer as a new feature class.



	
  * In the TOC Right-click on the **GP_county_1930**layer and select **Data** > **Export Data.**

	
  * In the **Export Data** dialog select the following settings:


[![GISlesson1_join_data3](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_join_data3.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_join_data3.png)

For **Output feature class**:



	
  * Click on the Folder icon and navigate to **ArcGIS_Lesson1****\GIS_Demo1.gdb**.

	
  * Name the new map file **GP_county_1930_join_census**


[![GISlesson1_join_data2](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_join_data2.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_join_data2.png)



	
  * Click **Save**, then **OK**.


[![GISlesson1_join_data4](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_join_data4.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_join_data4.png)



	
  * Click **Yes** to add the exported data to the map as a layer.


You are done with **GP_county_1930 **so uncheck its box.



	
  * Click on the **List by Drawing Order** button ![GISlesson1_listbydrawingorder](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_listbydrawingorder.png) and drag **GP_states_1930** back to the top of the list.




## **VI. Symbolize attribute data**


You have completed the basic data set-up procedures for a GIS.  The map data and the attribute data are related to one another.  Because the data represent conditions more than 75 years ago, this is an HGIS, a Historical Geographic Information System.  Now we can ask historical questions of the GIS.

**Question:**


Where in the 12 Great Plains states could we find the most people of Norwegian birth in 1930?


**_Key concept: _**_One of the fun parts of GIS analysis is the process of data exploration.  _Data exploration_ refers to the iterative mapping and remapping of attribute information to look for interesting spatial patterns.  Some of the most productive and creative analysis in GIS work comes from repeatedly making maps, then changing a parameter and remaking the map, as a way to learn about the nature of the attribute data._

In this exercise we will begin the data exploration process.



	
  * Clear any selected features and close the **Table** window so that the map display occupies the main space.


The data are still there, connected to the map, but they need not always be visible.

	
  * In the TOC right-click on the **GP_county_1930_join_census**

	
  * Select **Properties** to bring up the **Layer Properties** dialog
(note that because we will use this dialog extensively,
double-clicking on the layer name in the TOC opens it automatically).

	
  * Select the **Symbology**

	
  * On the left side of the dialog box select **Quantities** and then **Graduated colors**.


Here you can instruct the program to represent one of the census attributes on the map.

	
  * In the **Fields** section, set **Value** to the **Population**


This instructs the software to map the total population information from the attribute table, joined from the census table earlier.

	
  * From the **Color Ramp** dropdown, select a red option.

	
  * Change the number of classes to 4 and click the **Classify**

	
  * On the right side of the Classification dialog box set the **Break Values** to the following:

	
    * 9999

	
    * 24999

	
    * 79999

	
    * 1000000





[![GISlesson1_classification](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_classification.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_classification.png)



	
  * Click **OK**.


You have just instructed the program to represent (or display) the counties using 4 distinct classes based on total population size:  those under 10,000, those between 10,000 and 24,999, those between 25,000 and 79,999, and those over 80,000.  The more people in a county, the darker red the fill symbol will be.

[![GISlesson1_layer_properties](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_layer_properties.png?w=625)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_layer_properties.png)



	
  * Inspect the **Layer Properties** dialog to confirm that the classes seem appropriate.

	
  * Move the **Layer Properties** dialog off of the map and click the **Apply** button to see which parts of the plains had more people and which had fewer in 1930.


**_Note: _**_clicking **Apply** applies the change to the layer but leaves the dialog open, whereas clicking **OK** applies the change and closes the dialog._

During this data exploration phase, you can change parameters on the fly to ask different questions and to refine your answers.  Maybe you want to change the 4 population class ranges or the number of classes represented.  You can change the colour choices and even the variable mapped until you hit on information that is useful and interesting.  So to answer the question “where would we find a lot of Norwegians in 1930?”:



	
  * change the **Value** field under the **Symbology** tab of the **Layer Properties** dialog to **Born_Norway**and click **Apply**.


**Question:**



	
  * Which Great Plains states had many counties with high Norwegian-born populations in 1930?


Don’t remember your American geography?  Using the **Identify** tool  , click on one of the states.  You can find the state’s name in the **Identify** window that pops up.

**Question:**



	
  * Which Great Plains states had some counties with high Norwegian-born population in 1930?


We got our answer, but what do we really mean by “high Norwegian-born populations”? High compared to what?  What we have mapped here is high Norwegian-born populations compared to all counties in the 12 states.  We don’t really know what percentage of the population in these redder counties was Norwegian-born.  To discover that we need to represent the data as a percentage rather than an absolute population count. ArcMap calls this process “**Normalization**”, which is not the same as statistical or database normalization.

**_Key concept: _**__Normalization___ is the process of allocating data equivalently based on a larger total.  For example, when we represent wheat acreage as a proportion of the total acreage of a county, we normalize based on total area.  When we represent Norwegian-born people as a proportion of all the people in the county we normalize based on total population.  It is often more accurate and honest to represent normalized data rather than raw data._

Inspect the map as it is now.  Note the large county in northeastern Minnesota that is one of the darkest on the map.  This county may have a large Norwegian-born population simply because it is considerably bigger than the one just to the south of it.  Mapping raw data doesn’t account for the variations in county size or for the fact that a county with a large city in it has a lot more total people than a rural county.

Revise your map to normalize for total population.



	
  * Set **Normalization** to **Population**:  [![GISlesson1_normalization](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_normalization.png)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_normalization.png)


This tells ArcMap to take the Norwegian-born number for each county and divide it by the total population of each county.  The result will be the proportion Norwegian-born.  [Remember your math?  Example:  A proportion of 0.11 = 11% of the population.  To convert proportion to percentage, shift the decimal point 2 positions to the right.]

	
  * Click **Apply**.


The map changes quite dramatically.

** **

**Question:**



	
  * Which Great Plains states had many counties with high Norwegian-born proportions in 1930?


**Question: **



	
  * Which Great Plains states had some counties with high Norwegian-born proportions in 1930?


Let’s adjust the map to use more intuitive break points in the legend.

In the Layer Properties dialog, under the Symbology tap, click the **Classify** button and change the **Break Values** on the right side of the **Classification** box to the following:

[![GISlesson1_break_values](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_break_values.png?w=116)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_break_values.png)



	
  * Click **OK**.


This setting groups together the counties with under 2%, 2-5%, 5-10% and 10-13% Norwegian-born population, with darker reds indicating higher percentages.

	
  * Convert the proportions indicated under the **Range** heading to percentages under the **Label** heading by typing in the following label items:

	
    * 0 - 2.0%

	
    * 1 - 5.0%

	
    * 1 - 10.0%

	
    * 1 - 13.0%





[![GISlesson1_label_percentages](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_label_percentages.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_label_percentages.png)



	
  * Click **OK** to close the **Layer Properties**




## **VII. Generate a finished map**


Now that you have answered your analytical question, you may want to generate a map to accompany the historical discussion of this question in your text.



	
  * On the toolbar at the top of the ArcMap window look for a blue-green globe icon called
**Full Extent** [![GISlesson1_full_extent](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_full_extent.png)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_full_extent.png).


**_Key concept: _**_ArcMap offers two distinct ways to display your layers. _Data View_ is used primarily for data manipulation, exploration and analysis, to assemble your collection of layers and data tables, to change their symbols, etc. _Layout View_ on the other hand displays a page and is used to design a map that will be sent to the printer or published as a pdf or jpg file._

Now look in the bottom left corner of the map display.  A small map icon indicates that you are viewing your map in “**Data View**”. [![GISlesson1_page_icon](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_page_icon.png)](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_page_icon.png).



	
  * Hold your mouse pointer over the icon to confirm this.




Now we will switch to “**Layout View**” to complete our map.  Just to the right of the small map icon is a page icon.



	
  * Click on the page icon to see a page layout mock-up of a publishable map.


The map we just created is already there.  We need to add a legend, scale bar, and title that will help map readers interpret the meaning of the map.  Because we are conscientious scholars, we will also add a credit line to acknowledge the source of our data.  The steps below tell you how to add these items to your layout page.  If you don’t like the initial result, you can always delete the element and try again.

	
  * From the menu bar at the top of the ArcMap window, select **Insert** > **Title**.


A text box appears on the map layout.

	
  * Type in “Percentage Norwegian-born, 1930” for the map’s title and click **OK**.

	
  * Click on the title text box to select it, and use your arrow keys to move the title up above the map but still inside the solid black neat line.

	
  * From the menu bar, select **Insert** > **Legend**.

	
  * In the **Legend Wizard** set **Legend Items** to show only GP_county_1930_join_census.  Click **Next**.

	
  * Change the **Legend Title** to read “Percent Norwegian-born.”

	
  * Continue to click **Next** through the rest of the windows and **Finish** to complete the legend.


It shows up in the middle of the page.

	
  * Click and drag the legend box to the bottom left corner of the page, inside the neat line.

	
  * From the menu bar, select **Insert** > **Scale Bar**.

	
  * In the **Scale Bar Selector** dialog choose the option you like best.

	
  * If you want to tinker with the scale bar properties, click the **Properties**


For example, you might want the scale bar to indicate kilometres instead of meters.

	
  * When you are done, click **OK**.

	
  * Select the scale bar box, click, and drag it to the bottom right of the layout, inside the neat line.

	
  * From the menu bar, select **Insert** > **Text**. A small text box appears in the middle of the map.

	
  * Type the following: “Map data and U.S. Census data from _http://www.nhgis.org.”_

	
  * Drag the box to the bottom of the page so that it doesn’t overlap with any other map elements.


When the layout is arranged to your satisfaction, you are ready to export your map.  You could, at this point, print a paper copy.  Instead, for today, we will export the map as a .jpg image that could be imbedded into a Word document, uploaded to a web site, or used in a PowerPoint presentation.

	
  * From the menu bar, select **File** > **Export Map**.

	
  * Navigate to **ArcGIS_Lesson1****\OutputMaps** and name your file Norwegian1930.jpg.

	
  * Set **Save as type**: to JPEG (*.jpg) and dpi to 200.

	
  * Click **Save**.




## **VIII. Explore your own historical question using the 1930 data**





	
  * Click the **Save** button (in case you haven’t already done so 12 times…) to save your Norwegian-born map in its current form.


Now we need to create a second copy of this document.

	
  * From the menu bar, select **File** > **Save As**.

	
  * Rename the map document as **mxd**.


Be sure to save the newly saved file in**ArcGIS_Lesson1\ProjectFiles**.  Every time you are ready to generate a new map, start by re-saving the ***.mxd** file with a new name

It is time to pursue your own curiosity. Because the data are already set up for analysis, you don’t need to repeat sections I-V above. Instead, repeat the procedures outlined in sections VI-VII above to ask historical questions of the data, symbolize the answers appropriately, and generate output maps.  Try mapping lots of different attributes.  Tinker with the best symbolization settings to represent them accurately and clearly.  Find one or two with interesting results, and generate a couple of output maps. (If you come up with something good, post it on Twitter and tag @geospatialhist.)


## **IX. Explore change through time**


**_Key concept: _**_GIS is useful to many academic disciplines and for a multitude of commercial applications.  _Historical GIS_ is an emerging methodology within the historical profession that uses GIS technology to analyze and understand the past.  An aspect of HGIS that distinguishes it from other GIS uses is the need to represent time.  One solution to the challenge of time in GIS is to make sequential maps that hold constant the attribute mapped, the scale, and the legend, but change the dates_

Choose one variable and map it for several time points. To explore change through time you’ll need to repeat some of the steps from sections I-V above to import map and attribute data, join them, and then symbolize variables. The exercise files contain data for several census years.  Keep in mind that the attributes available for each year are not always the same.  One that is consistent is total population, so a relatively easy time series to construct would be changes in total population through time.  To make maps that are truly comparable through time, they all need to have the same scale, and use the same classification and colours.


