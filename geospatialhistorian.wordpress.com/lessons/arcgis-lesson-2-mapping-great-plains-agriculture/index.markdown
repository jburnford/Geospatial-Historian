---
author: cljim22
comments: true
date: 2014-11-27 21:55:24+00:00
layout: page
link: https://geospatialhistorian.wordpress.com/lessons/arcgis-lesson-2-mapping-great-plains-agriculture/
slug: arcgis-lesson-2-mapping-great-plains-agriculture
title: 'ArcGIS Lesson 2:  Mapping Great Plains Agriculture'
wordpress_id: 920
---

[Please Leave Comments and Suggestions for Revisions]

By Geoff Cunfer with Patrick Chassé, revised by Louis-Jean Faucher


## **Introduction**


This lesson has two goals.  First, it will reinforce the basic GIS methods and concepts introduced in the [Population exercise](https://geospatialhistorian.wordpress.com/lessons/arcgis-lesson-1-mapping-great-plains-population/).  Second, it will introduce you to additional HGIS methods and concepts, expanding the spatial exploration of the Great Plains in the past.

This exercise uses the same map data employed in the Population exercise.  The data are publicly available from the National Historical GIS project based at the University of Minnesota.  That project created map layers at various scales (nation, state, county, census tract, etc.) to correspond with the decennial U.S. censuses for all years ending in 0 from 1790 until 2000.  You can download census statistics and corresponding maps, designed for use in a GIS or in statistical software, from [**http://www.nhgis.org**](http://www.nhgis.org/).

The agricultural census data employed here come from the Great Plains Population and Environment Database held at the Inter-University Consortium for Political and Social Research (ICPSR) at the University of Michigan.  Registered users can download data from a web site. See [**http://www.icpsr.umich.edu/PLAINS**](http://www.icpsr.umich.edu/PLAINS) for full documentation and information about how to register.

This project will repeat the process of loading GIS data, joining attributes to maps, and symbolizing maps based on those attribute data.  It will introduce [overlay](http://support.esri.com/en/knowledgebase/GISDictionary/search) mapping techniques while enabling you to explore historical questions about the spatial distribution of agricultural land use in the past.  You will learn how to create printable maps that answer descriptive historical questions.



	
  * **Download [the ](https://drive.google.com/open?id=0ByEStot3aAG_djdKWWgxQTljM1U)****[zipped file](https://drive.google.com/open?id=0ByEStot3aAG_djdKWWgxQTljM1U) ****and save in your Documents\ArcGIS folder (make sure you unzip the folder).**




## **I. Open ArcMap**





	
  * From your computer desktop open the ArcMap software.


Begin by saving a new project file

	
  * Click **File **>** Save** (or **Ctrl-S**) and save to **ArcGIS_Lesson2\ProjectFiles **called **mxd**.


If you have trouble locating your folder, make sure you connected the ArcGIS_Lesson2 Folder to ArcGIS using the **Connect to Folder** button.![Connect to Folder](https://geospatialhistorian.files.wordpress.com/2014/11/connect-to-folder.jpg)

If you unzipped the folder in **Documents\ArcGIS **you should be able to find it, but if you saved it elsewhere on your hard drive, you will need to use the **Connect to Folder **button.

It is very important not to move the location of the folders or change the name of the folders holding GIS data.

![Connect to Folder2](https://geospatialhistorian.files.wordpress.com/2014/11/connect-to-folder2-e1502306972327.jpg)

**_Note:_** Remember t_he ArcGIS software has a tendency to crash now and again.  Click the **Save** button (or **Ctrl-S**) to save your work about every 5 minutes throughout the exercise._



	
  1. **_ Load map data_**



	
  * In ArcMap click the **Add Data** button

	
  * Navigate to **ArcGIS_Lesson2\GIS_Demo1.gdb**and select the feature classes called **GP_county_1930 **and **GP_states_1930**. Hold down the **Ctrl** key to select both at the same time, then click the **Add**


[![Save 1930ag1](https://geospatialhistorian.files.wordpress.com/2014/11/save-1930ag1.jpg)](https://geospatialhistorian.files.wordpress.com/2014/11/save-1930ag1.jpg)

If you have trouble locating your folder, make sure you connected the ArcLesson2 Folder to ArcGIS using the Connect to Folder button. If you unzipped the folder in **Documents\ArcGIS **you should be able to find it, but if you saved it elsewhere on your hardrive, you will need to use the Connect to Folder button.

It is very important not to move the location of the folders or change the name of the folders holding GIS data.

[![Connect to Folder2](https://geospatialhistorian.files.wordpress.com/2014/11/connect-to-folder2-e1502306972327.jpg)](https://geospatialhistorian.files.wordpress.com/2014/11/connect-to-folder2.jpg)

**Remember**: ArcGIS can crash unexpectedly. To avoid losing your work, click the Save button frequently throughout the exercise.


## **II. Load map data**





	
  * In ArcMap click the **Add Data** button ![add_data](https://geospatialhistorian.files.wordpress.com/2014/11/add_data.png)

	
  * Navigate to **ArcGIS_Lesson2\GIS_Demo1.gdb**and select the feature classes called **GP_county_1930 **and **GP_states_1930**. Hold down the **Ctrl** key to select both at the same time, then click the **Add**


![GISdemo1](https://geospatialhistorian.files.wordpress.com/2014/11/gisdemo1.png)

On the left side of your screen in the **Table Of Contents** (TOC) two new layers appear with check marks next to them.  One is **GP_county_1930** and the other is **GP_states_1930**.  Each has a coloured box below it.  On the right side of your screen appears a corresponding map of all of the counties in the 12 Great Plains states as they existed in 1930.



[![Add Data GP Output](https://geospatialhistorian.files.wordpress.com/2014/11/add-data-gp-output.jpg)](https://geospatialhistorian.files.wordpress.com/2014/11/add-data-gp-output.jpg)


## **III. Symbolize and arrange map layers**





	
  * Check and uncheck the boxes next to the two layers to turn them on and off. ![GISlesson1_listbydrawingorder](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_listbydrawingorder.png)

	
  * Check both to turn both layers on.  Click the icon in the top left corner of the **TOC** to **List By Drawing Order**.  Then click and hold on the **GP_states_1930** layer and drag it above the **GP_county_1930** layer.  When you release the mouse button it moves to the top of the list.


You may have to click on the **List By Drawing Order** icon in the top left of the TOC.

![List By Drawing Order](https://geospatialhistorian.files.wordpress.com/2014/11/list-by-drawing-order.jpg)

Now you will “symbolize” (change the graphic representation) of the **GP_states_1930** layer so that it complements the **GP_county_1930** layer, rather than obscuring it.



	
  * Click on the coloured box beneath **GP_states_1930**. The **Symbol Selector** dialog appears.

	
  * Select the **Hollow box** Make the **Outline Color** black and the **Outline Width** = 2.

	
  * Click **OK**.


Notice how the symbol box has changed.

![GISlesson1_symbol_selector](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_symbol_selector.png)

Now you can see both map layers at the same time.  **GP_states_1930** appears as an outline only, without any fill colour, while **GP_county_1930** retains its fill colour. The state boundaries make it easier to distinguish which counties are within which state.


## **IV. Load attribute data**





	
  * Click the **Add Data** button again ![add_data](https://geospatialhistorian.files.wordpress.com/2014/11/add_data.png). Inside **gdb**select the dataset called **GP1930ag**.

	
  * Click the **Add**


A new data table appears in the TOC, but this time there is no layer corresponding to it in the map display.

	
  * Right-click on the table called **GP1930ag**and select **Open**.


A Table called **GP1930ag** opens in the **Table** view; it looks much like a spreadsheet.  Each row (or record) represents one county in the 12 Great Plains states.  Each column (or attribute / variable) represents one type of information about those counties.



[![Attribute Data GP1930Ag](https://geospatialhistorian.files.wordpress.com/2014/11/attribute-data-gp1930ag.jpg)](https://geospatialhistorian.files.wordpress.com/2014/11/attribute-data-gp1930ag.jpg)



	
  * Explore the data table by scrolling up and down and left and right.


The **name** attribute indicates the county that each row represents.  The column headings across the top indicate what information about those places is available in this dataset.  Individual cells contain numerical or textual data.  This selection of data from the 1930 U.S. Census of Agriculture includes the following information about each county:



	
  * acreage harvested for various crops

	
  * idle and failed cropland

	
  * number of farms

	
  * acreage irrigated

	
  * acreage in pasture and woodland

	
  * number of tractors

	
  * number of various livestock


[![Farmland Irrigated](https://geospatialhistorian.files.wordpress.com/2014/11/farmland-irrigated.jpg)](https://geospatialhistorian.files.wordpress.com/2014/11/farmland-irrigated.jpg)

This data table will help us to characterize the land use history of each county and to understand the agricultural structures of different places in the Great Plains.


## **V. Join map data and attribute data**


At the moment, ArcMap represents the location of all of the counties in the Great Plains states.  And the map contains a table of information (attributes) about all of those counties.  But the program does not yet know those two sets of information are related.

The map layers do have some attributes already built in.



	
  * Right-click on the **GP_county_1930** layer and select **Open Attribute Table**.


A similar data table called **GP_county_1930** appears in the **Table** window.  This table looks a lot like the other one, with several columns of attribute data and a row for every county feature.  There are 17 attribute columns, all with different kinds of identification information.

This table doesn’t contain much information of substance about the characteristics of each county. The crucial difference between the two tables is that attributes of **GP_county_1930** are directly connected to the map while the other one is not.



	
  * Resize and drag the **Table** window so that it doesn’t obscure the map.

	
  * In **GP_county_1930, **click on one of the small gray boxes to the far left of the table window.


Doing so highlights a row in the table that represents a single county _and_ highlights the corresponding county feature on the map.  If you want to know where any given county is, click on the adjacent gray box in the table to select it.

[![Select County Iowa](https://geospatialhistorian.files.wordpress.com/2014/11/select-county-iowa.jpg)](https://geospatialhistorian.files.wordpress.com/2014/11/select-county-iowa.jpg)

Click the **Clear Selection** button ![GISlesson1_clear_selection](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_clear_selection.png) at the top of the **Table** window before moving on.

Clicking on the small gray box next to a row in the** GP1930ag** table selects that row in the table.  But it does not select a corresponding county on the map.  So far, ArcMap doesn’t know how to connect the agricultural census data to a location on the map.

Notice that one column is identical in both tables:** UNFIPS**. (It is in capital letters in one table and in lower case in the other; the field names can be different, as long as the **data types** and **values** are identical.)  This variable presents a unique ID code for each county.  (Note that with the agriculture data, the unique ID is** UNFIPS**, while with the population data the unique ID is **GISJOIN**.  This difference stems from the two different sources of the attribute datasets.)  Guthrie County, Iowa has the code 19077 in both tables, for example.  These unique IDs will allow ArcMap to join the data table with agricultural census information to the map layer attribute table so that the program can connect locations on earth with attributes describing those locations.



[![unfips 1930 county](https://geospatialhistorian.files.wordpress.com/2014/12/unfips-1930-county.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/unfips-1930-county.jpg)





	
  * Click on the **Clear Selection** button at the top of both data tables (in case you have any rows selected).

	
  * In the TOC, right-click on **GP_county_1930**and select **Joins and Relates** > **Join**.


[![Join and Relate Step 1](https://geospatialhistorian.files.wordpress.com/2014/12/join-and-relate-step-1.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/join-and-relate-step-1.jpg)

The **Join Data** dialog box appears, which will allow you to connect the data to the map.

What do you want to join to this layer? Make the following selections in the dialog box:



	
  * Choose the field in this layer that the join will be based on: **UNFIPS**

	
  * Choose the table to join to this layer, or load the table from disk: **GP1930ag**

	
  * Choose the field in the table to base the join on: **unfips**

	
  * Click **OK**.


[![Join Data Step 2](https://geospatialhistorian.files.wordpress.com/2014/12/join-data-step-2.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/join-data-step-2.jpg)

The table called **GP1930ag** has not changed.  Close it.  Inspect the table called**GP_county_1930**.  All of the 17 original ID columns are still there.  Scroll to the right in the table.  All of the agricultural census data are now also present in the map’s attribute table.  Now when you click on a gray box on the left side of the table, selecting both the row and a county on the map, you can determine how many farms were in that county in 1930, how many acres of corn, wheat, or cotton farmers there harvested, and how many cows, horses, and sheep they owned.  The join procedure has connected the map data with attribute data about the map features, in this case counties. If you right click on a highlighted county, you can use the **Identify** command to reveal information about the county you selected. Note that this connection is ephemeral and is only temporarily stored in your map document.

[![Identify](https://geospatialhistorian.files.wordpress.com/2014/12/identify.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/identify.jpg)



	
  * Remember to **Clear Selection** before moving onto the next part of the exercise.




## **VI. Symbolize attribute data**


You have completed the basic data set-up procedures for a GIS.  The map data and the attribute data are related to one another.  Because the data represent conditions more than 75 years ago, this is an HGIS, a Historical Geographic Information System.  Now we can ask historical questions of the GIS.  In this exercise we will begin the data exploration process.

**Question:**



	
  * Where in the 12 Great Plains states was the most wheat, hay, and cotton growing in 1930?

	
  * Close the attribute table so that only the map is visible.


The data are still there, connected to the map, but they need not always be visible.

	
  * In the TOC right-click on the **GP_county_1930**

	
  * Select **Properties** to bring up the **Layer Properties** dialog
(note that because we will use this dialog extensively,
double-clicking on the layer name in the TOC opens it automatically).

	
  * Select the **Symbology**

	
  * On the left side of the dialog box select **Quantities** and then **Graduated colors**.


Here you can instruct the program to represent one of the census attributes on the map.

	
  * In the **Fields** section, set **Value** to the **Wheat**


This instructs the software to map the total wheat acreage from the attribute table.

	
  * From the **Color Ramp** dropdown, select a red option.

	
  * Change the number of classes to 4 and click the **Classify**

	
  * Click **Apply**.


![RedWheatEDIT](https://geospatialhistorian.files.wordpress.com/2014/11/redwheatedit.jpg)

**_Key Concept:_**_ Classification is the action or process of classifying something according to shared qualities or characteristics. In geography terms, classification is a way to generalize attributes and is the process of data analysis used to make choropleth maps. It arranges data according to the values of information and allows the cartographer to recognize patterns in the data. Using different classification methods, you control the message communicated by your map; with the exact same data, you can create a map that makes the main theme appear quite insignificant, or very pronounced._

You have just instructed the program to represent (or display) the counties using 4 distinct classes based on wheat acreage using the natural breaks in the distribution.  The more wheat in a county, the darker red the fill symbol will be.



	
  * Inspect the **Layer Properties** box to confirm that the legend seems appropriate.

	
  * Move the **Layer Properties** box off of the map to see which parts of the plains had more wheat and which had less in 1930.


![RedWheatPlainsEDIT](https://geospatialhistorian.files.wordpress.com/2014/11/redwheatplainsedit.jpg)

**Questions:**



	
  * Which Great Plains regions had the highest acreage devoted to wheat in 1930?

	
  * Why do there appear to be two distinctive wheat regions in the plains?


Don’t remember your American geography?  Using the **Identify** tool ![GISlesson1_identify](https://geospatialhistorian.files.wordpress.com/2014/11/gislesson1_identify.png), click on one of the states.  You can find the state’s name in the **Identify** window that pops up.

**_Key concept: _**_GIS methods are excellent for answering _descriptive questions_ like the first one above.  Where did phenomena occur in the past?  The GIS answers this much better than a data table of wheat acreages could have.  The second question above is a lot harder to answer because it is an _analytical question_ that asks why the spatial distribution existed as it did.  The present GIS doesn’t have enough information to answer this question.  You might design a GIS that allowed you to answer it, but we’re not there yet.  Often, HGIS helps us to understand what happened in the past, and raises new analytical questions about why things happened, requiring traditional research methods to answer._

Remember that it is important to normalize your data so all counties are comparable.  Because many of the data employed in this exercise represent areas of land, total county area is the relevant denominator for comparability.



	
  * In the **Normalization** box select **Area**.

	
  * Click Apply.


**Reminder:** Don’t remember your American geography?  Click on the Identify button  [![Identify 3](https://geospatialhistorian.files.wordpress.com/2014/12/identify-3.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/identify-3.jpg) and then click inside one of the states.  You can find the state’s name in the small table that pops up.

This now reports the proportion of total county area devoted to wheat.  By looking at the ranges listed you can see that the lowest wheat county had 0% wheat acreage, while the highest wheat county devoted 64% of its entire area to wheat.

![RedWheatArea](https://geospatialhistorian.files.wordpress.com/2014/11/redwheatarea.jpg)

During data exploration you can change parameters on the fly to ask different questions and to refine your answers.  Maybe you want to change the data ranges or the number of ranges represented.  You can change the colour choices and the variable mapped until you hit on information that is useful and interesting.  Answer the following descriptive questions, then speculate about their analytical explanations.

**Questions**



	
  * Which Great Plains regions had the highest acreage devoted to hay in 1930?

	
  * Why was hay grown in those areas and not elsewhere?

	
  * Which Great Plains regions had the highest acreage devoted to cotton in 1930?

	
  * Why was cotton grown in those areas and not elsewhere?


**_Key concept: _**_ _Thematic maps_ show the distribution of one attribute across space.  They address a single theme.  The maps you’ve generated above are thematic maps of crop acreages.  Thematic maps usually represent spatial variation.  Alone, they don’t represent variation in time or in theme very well.  For example, can you imagine a single thematic map that shows both hay acreage and wheat acreage in the same image?  How about one that shows hay acreage in both 1890 and 1930?  Addressing these more complex questions usually requires making and comparing two or more maps._




## **VII. Explore spatial change over time**




Let’s map land use information, but now for two different time points, to begin to evaluate change over time. Using the techniques outlined above:



	
  * Symbolize 1930 acreage of **Farmland_irrigated** and normalize by **Area**.

	
  * Set the number of **Classes** to 4, and click the **Classify**

	
  * Change the **Break Values** as follows:

	
    * 0.02

	
    * 0.1

	
    * 0.2

	
    * 0.75





[![Classify](https://geospatialhistorian.files.wordpress.com/2014/12/classify.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/classify.jpg)





	
  * Click **OK**.

	
  * Inspect the Ranges.


These settings group together counties with up to 2% of total area irrigated, with 2-10% irrigated, with 10-20% irrigated, and with 20-75% of their total area irrigated.  We also need to adjust the colours.

	
  * For the first range, double-click on the pink patch to open the **Symbol Selector** dialog box.

	
  * Click the drop-down arrow next to **Fill Color** and select the white patch.

	
  * Click **OK**.


Do the same to change the colours of the other three patches, making the second range the lightest pink, the third range the next darker pink, and the fourth range a bold red.
_Alternatively, you can experiment using one of the many pre-defined **Color Ramp** within ArcMap._



	
  * Click **Apply**.


[![Symbology Colors](https://geospatialhistorian.files.wordpress.com/2014/12/symbology-colors.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/symbology-colors.jpg)

[![Map Irrigated Farms](https://geospatialhistorian.files.wordpress.com/2014/12/map-irrigated-farms.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/map-irrigated-farms.jpg)

**_Note:_** _Classes always need to me _mutually exclusive_.  In the example above, inside of which class does a county with 20% irrigation fall into?  The Classification tool handles this correctly, but you need to make sure this is appropriately displayed in your map legend.  Therefore, rounded class ranges should be 0-2%, 3-10%, 11-20%, 21-75%. If using decimals, they could be 0-2.0%, 2.1-10.0%, 10.1-20.0%, 20.1-75%.  This way, any single value is guaranteed to fall into a single class._

**Questions:**



	
  * Which regions of the 12 Great Plains states had the most irrigated land in 1930?




	
  * Why was there so much irrigation in the Rocky Mountains and so little in the Great Plains?


Now we’ll add more data to ask the same question 30 years later, in 1959. Using the procedures outlined above:

	
  * Add the feature classes called **GP_county_1960**and **GP_states_1960 **as

	
  * Add the standalone table called **GP1959ag**.

	
  * By clicking the relevant check boxes, turn off the two 1930 map layers and turn on the two 1960 map layers.

	
  * Symbolize the **GP_states_1960**layer to make it hollow, with a thick black outline.

	
  * Drag it to the top of the list so that it draws over top of the 1960 county map.


You may wish to group layers together to better organize your TOC. It also makes it easier to turn on/off multiple layers at once. To do so:

	
  * Select both 1930 layers using **Ctrl-click**.

	
  * **Right-click** > **Group** to create a new group.

	
  * Rename the group **1930**.

	
  * Repeat the same operations for the year 1960.


![Picture1](https://geospatialhistorian.files.wordpress.com/2014/11/picture1.png)



	
  * Join **GP1959ag**to the **GP_county_1960** map layer, using the system described above.
(We’re assuming that no county boundaries changed between 1959 and 1960).


[![1960 Ag](https://geospatialhistorian.files.wordpress.com/2014/12/1960-ag.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/1960-ag.jpg)



	
  * Symbolize the**GP_county_1960** layer, using **Value: Farmland_irrigated** and **Normalization: Area**.

	
  * For the classification, employ the same number of classes, the same data ranges, and the same colour selections that you used for 1930 so that the two maps will be truly comparable.


[![Farmland Irrigated 1960](https://geospatialhistorian.files.wordpress.com/2014/12/farmland-irrigated-1960.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/farmland-irrigated-1960.jpg)

Make sure that the map layers fall in this order:



![Picture2](https://geospatialhistorian.files.wordpress.com/2014/11/picture2.png)

Click the check boxes next to each layer to turn on **GP_states_1960** and **GP_county_1960**.  Turn off the entire **1930** group to display the layers hidden beneath.  Now click repeatedly the check box next to the **1960** group layer to toggle between the 1930 and the 1960 irrigation maps.

![19301960](https://geospatialhistorian.files.wordpress.com/2014/12/19301960.gif)

**Questions:**



	
  * How did the location of irrigation on farms change between 1930 and 1959?

	
  * Why did irrigation geography change so dramatically between 1930 and 1959?




## **VIII. Use overlay techniques to address analytical questions**


The descriptive question above is easily answered. The analytical question is harder. Next we’ll introduce an overlay map layer that will help us to answer the tougher analytical _why_ question.



	
  * Add the feature class called **Ogallala** to the map as layer

	
  * Reorder so that that it appears at the very top of the list of map layers.

	
  * Click its colour patch to bring up the **Symbol Selector**

	
  * Select a hollow **Fill Color **and make the **Outline Color** a bright blue, and the
**Outline Width**0.

	
  * Click OK.




[![Ogallala Aquifer](https://geospatialhistorian.files.wordpress.com/2014/12/ogallala-aquifer.jpg)](https://geospatialhistorian.files.wordpress.com/2014/12/ogallala-aquifer.jpg)

This map layer represents the location of the Ogallala Aquifer deep underneath the Great Plains.  It is the largest freshwater aquifer in North America, and farmers developed the technology to begin tapping into it during the 1930s.  The aquifer was there in 1930 (and for the 5 million years before that), but people didn’t know how to make use of it.  What does that tell you about the “nature” of natural resources?

**Question:**



	
  * Why, by 1959, did so many farmers in the Texas panhandle irrigate, while so few in North Dakota did so?


**_Key concept:_**_  _Overlay analysis_ compares two different map layers to explore connections and interactions between them.  Overlay analysis asks if there is any spatial correlation between two separate pieces of information, like the location of an aquifer and the location of farm irrigation.  Sometimes the connections are clear, but other times they are not.  The ability to look at two or more separate categories of spatial information at the same time is one of GIS’s most powerful analytical tools.  Thematic mapping helps to answer descriptive where questions.  To answer analytical why questions, we often need to employ overlay methods._


## **IX. Generate finished maps**


Use the same procedures employed in Lesson 1 to generate output maps of your analytical discoveries as .jpg files.


## **X. Explore your own historical question using the 1930 data**


Before exploring new questions, click the **Save** button to save your **1930ag1.mxd** project as is.



	
  * Click on **File** > **Save As**.

	
  * Create a new .mxd file name for your next data exploration.


Be sure to save the new .mxd files in **ArcGIS_Lesson2\ProjectFiles**.  Every time you are ready to generate a new map, start by re-saving the .mxd file with a new name.

This exercise includes map layers and agricultural census data for 1890, 1930, 1959, and 1997, plus map layers for the Ogallala Aquifer and for the location of the worst dust storms in 1934-35. See what kind of interesting land use history you can uncover through maps about the Great Plains.
