---
author: joshmac
comments: true
date: 2014-11-27 21:53:45+00:00
layout: page
link: https://geospatialhistorian.wordpress.com/lessons/arcgis-lesson-4-digitizing/
slug: arcgis-lesson-4-digitizing
title: 'ArcGIS Lesson 4: Digitizing Archival Maps'
wordpress_id: 917
---

By Geoff Cunfer with Jessica DeWitt, revised by Louis-Jean Faucher


## Introduction


This lesson introduces the concept of digitizing features with ArcGIS. Scanning historic maps makes it possible to bring them as images into a GIS and extract features from the original paper map. You saw in the previous lesson that one of the valuable aspects to raster data is that it can be georeferenced. You will now “digitize” (or draw) the features shown on the raster image using point, line and polygon vector features.

For this lesson we will be using a map scanned by Geoff Cunfer, Professor of History at the University of Saskatchewan, during a research trip to the archives of the Kansas State Historical Society in Topeka, Kansas. The archive holds copies of landownership maps from across the state, but does not allow researchers to handle the originals. Instead, they make them available on microfilm. The image was printed from a microfilm machine, then scanned it with a flatbed scanner. The map’s main purpose is to show who owns which parcels of land in Logan Township, Rooks County, Kansas, and it dates to 1905. “Plat maps” like this one are important artifacts of the American property rights regime and are common across North America. They contain rich information about social structure, class, land use, and many other aspects of rural life.


## **I. Getting Started**





	
  * Download [the zipped file](https://drive.google.com/open?id=0ByEStot3aAG_R25sdG1ERGtzNzA) and save in your **Documents\ArcGIS **folder (remember to unzip the folder).


The first step is to examine the image. For this lesson we are using the image **Plat_LoganTwp_1905.jpg** located in the **ArcGIS_Lesson4\Scans** folder.



	
  * From the **Windows File Explorer**, double-click the file to open the image in a viewer.


![Picture21](https://geospatialhistorian.files.wordpress.com/2014/11/picture21.png)





	
  * Zoom and pan around the map to examine it closely.


[![2 Zoom in On Map](http://geospatialhistorian.files.wordpress.com/2014/04/2-zoom-in-on-map.png)](http://geospatialhistorian.files.wordpress.com/2014/04/2-zoom-in-on-map.png)
[![3 Zoom in on Map II](http://geospatialhistorian.files.wordpress.com/2014/04/3-zoom-in-on-map-ii.png)](http://geospatialhistorian.files.wordpress.com/2014/04/3-zoom-in-on-map-ii.png)

While looking closely at the map start identifying the features that can be digitized into distinct features classes.



	
  * What map features can you identify in this map?


Today we will focus on three of the map features found on this map: _land parcels_, _buildings_, and the _rail line_:



	
  * The _buildings_ are represented by the black dots on the map.

	
  * The _rail line_ is represented by the dashed, dark hatched line shown in the above image.

	
  * The _land parcels_ are the polygons identified by the owner’s name and the parcel’s acreage.


**_Reminder_**_: __Vector data can be represented by three different geometry types: points, lines, and polygons (see ArcGIS Lesson1)._



	
  * Which type of data will best represent our three selected map features?

	
  * The _buildings_ will be created using **point**

	
  * The _rail line_ will be created using **line**

	
  * The _land parcels_ will be created using **polygon**


Next, it is important to identify the map attributes that will be attached to each feature class.

	
  * What map attribute information can you identify in the map?


**_Reminder_**_: __Attribute Data consists of descriptive information that can be attached to each feature in a feature class. Examples of attribute data include the median income of a state, the speed limit of a road segment, or the name of a city. Each feature class includes its own specific attribute data._

Important attribute data in this map includes, but are not limited to:



	
  * The acreage of each parcel of land.

	
  * The name of the land parcel’s owner.

	
  * The name of the railway line.

	
  * The names of bordering townships.



	
  * Can you identify any other attribute information?


After adequately examining the image, you may close the image viewer.


## **II. Import and Georeference the Map in ArcMap**


Before the features on a map image can be digitized, it needs to be georeferenced.
(_For your convenience, the image has already been georeferenced and can be found in the **ArcGIS_Lesson4\GeoreferencedScans** folder, although more hands-on practice is always beneficial_).



	
  * Open **ArcMap** and click the **Add Data![adddatta](https://geospatialhistorian.files.wordpress.com/2014/11/adddatta.png)**

	
  * Navigate to **ArcGIS_Lesson4**\**gdb** and select the feature class called **Sample_Townships_1905**, then click the **Add** button.

	
  * From the** Table Of Contents** (TOC), change the symbol of the townships layer to the **Hollow box** symbol, making the **Outline Color** red and the **Outline Width** = 2, then click **OK**.

	
  * Using the **Add Data** button again, navigate to the **ArcGIS_Lesson4**\**Scans**folder and add the **jpg **image.

	
  * In the TOC, **right-click** the **Sample_Townships_1905 **layer and select **O****pen Attribute Table**.

	
  * Locate the feature where **TWP_NAME = Logan** and **COUNTY_NAM = Rooks**.

	
  * Click to highlight the record in the attribute table and on the map.

	
  * Click the **Zoom To Selected** button to bring it up in the map.


![Picture22](https://geospatialhistorian.files.wordpress.com/2014/11/picture22.png)

Georeference the **Plat_LoganTwp_1905.jpg **image using the **Sample_Townships_1905** as a reference layer following the same procedure outlined in ArcGIS Lesson3.



	
  * After georeferencing the image, **right-click** > **Remove** on the **Sample_Townships_1905 **layer;

	
  * Click **File **>** Save** (or **Ctrl-S**) and save to **ArcGIS_Lesson3\ProjectFiles **called **mxd**.




## **III. Digitize Map Features**




The **Digitizing1.gdb **geodatabase contains 3 feature classes to which we will now add map features.



	
  * Click the **Add Data** button, navigate to **ArcGIS_Lesson4**\**gdb**

	
  * Select the feature classes named **Rooks_Logan_1905_buildings**, **Rooks_Logan_1905_parcels**, and **Rooks_Logan_1905_rail** (use the **Ctrl** or **Shift** key to highlight multiple feature classes at once), then click the **Add **button.


![Picture23](https://geospatialhistorian.files.wordpress.com/2014/11/picture23.png)

Even with the layers turned on in the TOC, no features will draw on the map because there are no features yet in these feature classes; they contain no data.

**_Key concept:_**_ Most of the work you do in ArcMap involves changing a layer’s symbology and display properties, or copying a layer in the map, which does not contain nor change or duplicate the __source data__. _Digitizing_ (or the process of “_editing_”) on the other hand creates new or modifies existing features and attributes directly in the underlying feature class. Normally the attribute table only allows you to view and select rows and cells; during an “_edit session_” it allows you to freely type as you would in a spreadsheet. Drawing a new feature on the map will create new record in the feature class table, and any layer that references this data source will automatically be updated to reflect the change._

Before digitizing features and creating new data, you will set the symbology for each layer.



	
  * In the TOC, click the symbol under each layer

	
  * **Rooks_Logan_1905_buildings**: Square 1, Size: 8, Color: red.

	
  * **Rooks_Logan_1905_parcels**: Hollow, Outline Width: 1.00, Color: red

	
  * **Rooks_Logan_1905_rail**: Railroad, Width: 4.00, Color: red


![Picture25](https://geospatialhistorian.files.wordpress.com/2014/11/picture25.png)

**_Tip_**_: when working with black and white imagery, red features provide easily discernible contrasts._

Make sure the **Editor** toolbar is active. If not,



	
  * Click on **Customize** >**Toolbars** > **Editor**, or click the Editor Toolbar button:


![Picture26](https://geospatialhistorian.files.wordpress.com/2014/11/picture26.png)

We will now start editing.



	
  * Click on **Editor** > **Start Editing**.


![Picture27.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture27.png)



	
  * If the following **Create Features** does not appear,


![Picture28](https://geospatialhistorian.files.wordpress.com/2014/11/picture28.png)



	
  * Click on the **Create Features** button on the **Editor** toolbar:


![Picture29](https://geospatialhistorian.files.wordpress.com/2014/11/picture29.png)

**_Tip_**_: T__he Editor tools are quite useful since they allow you to add, change, or delete features, but can also be dangerous. Usually map features are locked, but once you choose to _start editing_ any map feature can be added, changed, or deleted. When finished editing make sure to go to **Editor** > **Save Edits** to permanently save the changes. If you make a mistake while editing one way to reverse it is to go to **Editor** > **Stop Editing** and choose NOT to save the edits, which will revert the layer back to its original state. Always **Stop Editing** and save your edits once you are done; there is no way to undo the changes that you made._

The first layer we will edit is the buildings layer. We will digitize the buildings located in Sections 25-36 on the map.



	
  * Zoom to Section 25 using the **Zoom In**


![11 Section 25](https://geospatialhistorian.files.wordpress.com/2014/04/11-section-25.jpg)

Sections are 1 mile square and comprise 640 acres. The section number appears in the center of each section. Section 25 is comprised of 2 quarter sections in the south owned by Goodman (160 acres) and Smee (160 acres), and 2 parcels in the north owned by Novotny (80 acres) and Baumgartner (240 acres).

You will now digitize the three buildings in section 25. The buildings are the small, black rectangles.



	
  * Make sure _buildings_ layer is selected in the **Create Features** window and click on the **Point** construction tool:


![Picture30](https://geospatialhistorian.files.wordpress.com/2014/11/picture30.png)



	
  * Click on the center of each building rectangle with your cursor.


Each click creates a separate point in the feature class. The points should look like this:

![12 Created Points](https://geospatialhistorian.files.wordpress.com/2014/04/12-created-points.jpg)



	
  * Now use the pan tool ![13 Pan Tool](https://geospatialhistorian.files.wordpress.com/2014/04/13-pan-tool.jpg) to move left to Section 26 and digitize the three buildings in this section using the same process (you may have to go back and click on the **Point** construction tool).

	
  * Repeat for sections 27-36.

	
  * Click on **Editor** > **Save Edits** when finished.


**_Tip_**_: __If you make a mistake you can use the black arrow tool _ ![14 Edit Black Arrow](https://geospatialhistorian.files.wordpress.com/2014/04/14-edit-black-arrow.jpg)_ on the **Editor** toolbar to select a point. Once selected you can move the point to its proper position or get rid of it by hitting the **Delete** key._

You will now digitize the Union Pacific railroad that crosses Section 31-36 into a line layer.



	
  * Zoom in on Section 35 and 36 using the **Zoom In** tool:


![Picture31](https://geospatialhistorian.files.wordpress.com/2014/11/picture31.png)



	
  * Make sure the _rail_ layer is selected in the **Create Features** window with the **Line **construction tool:


![Picture32.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture32.png)



	
  * Click on the right-most-end of the railway line, then click left along the line in intervals, making sure to follow it as close as possible.




![Picture33.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture33.png)

When you get to the edge of the screen use the pan button   to move leftward (_shortcut: press and hold the **c** key on your keyboard_). Click on the **Line** construction tool again to continue your line without interruption. Continue following the line until you reach the left-most-end.



	
  * **Double-click** to complete the line (or press **F2** to finish).

	
  * Click on **Editor** > **Save Edits** when finished.


Your line should look like this:

![Picture34.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture34.png)

**_Tip_**_: __A line is constructed in GIS with a beginning point, a number of intermediate nodes (called vertices), and an end point. There is no specific number of vertices that a line should contain. There should be a balance between time effectiveness and accuracy. The more vertices, the more accurate a line is, but it will take longer to create. The necessary accuracy depends on the scale in which the map will be used. Make as few vertices as necessary to create the accuracy needed for the scale of the map._

**_Note_**_: Lines should be digitized in the direction that they flow. For the above railway line it does not matter because the railway travels both ways. However, if you are mapping a river or the migration of a group of people, the line should be created in the direction of the flow or movement._

You will now digitize the land ownership parcels in Sections 23, 24, 25, 26, 35, and 36.



	
  * **Zoom In **to Section 36.

	
  * Make sure _parcels_ layer is selected in the **Create Features** window with the **Polygon **drawing tool:


![Picture35.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture35.png)



	
  * On the Mayhew parcel, **click **on the bottom-right corner to add the first “vertex”.

	
  * Then **click** on the bottom-left corner,

	
  * Then **click** the top-left corner.

	
  * Then **double-click** on the top-right corner to complete the polygon.


![Picture36.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture36.png)

If you ever get tangled-up in your drawing, you can always **right-click** > **Delete Sketch** (or press **Ctrl-Del**) to erase and start over.

![Picture37.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture37.png)

You can also **right-click** > **Finish Sketch** (or **F2**) if you have completed your drawing; it is sometimes more accurate than double-clicking to complete.

![Picture38.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture38.png)

Now digitize the Smee parcel, using the snapping function to snap to the edge of the Mayhew parcel.



	
  * Go to the **Editor** > **Snapping > Snapping Toolbar**.

	
  * Click on the **Vertex Snapping** and **Edge Snapping**


![Picture39.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture39.png)

**_Tip_**_: Snapping pulls your cursor to an existing vertex or edge when you are close to it. This ensures you are drawing with accuracy and do not leave gaps or create overlap between features._



	
  * Click on the **Polygon** construction tool and place your cursor on the bottom-right corner of the parcel.


Notice how the name of the layer appears above a small square? This indicates you are “snapping” to the features’ **Vertex**.

![Picture40.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture40.png)



	
  * Click on the corner to add the first vertex.

	
  * Move your cursor to the bottom-left corner of the parcel


Notice how the name of the layer appears above a small square crossed by a line? This indicates you are “snapping” to the features’ **Edge**.

![Picture41.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture41.png)



	
  * Then **click** the top-left corner.

	
  * Then **double-click** on the top-right corner to complete the polygon.


With the Smee parcel highlighted (select it with the edit tool  if it isn’t):

	
  * Click on the **Attributes** button of the **Editor** toolbar to display the **Attribute**

	
  * Type in the values for Owner, Acreage and Section as they appear on the map:


![Picture42.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture42.png)![Picture43](https://geospatialhistorian.files.wordpress.com/2014/11/picture43.png?w=300)

Continue digitizing the parcel polygons and entering their attributes for the specified sections. Note that property lines within sections are adjacent, however those in separate sections are not due to road allowances. You may turn snapping on and off to make drawing easier.



	
  * When finished click **Editor** > **Stop Editing**.

	
  * When asked if you wish to save your edits, click **Yes**.


You have now digitized a selection of the point, line, and polygon features on the map. Explore what you have created by checking and unchecking features in the Table of Contents.

	
  * Open the **Attribute Table** for the **Rooks_Logan_1905_parcels**


It contains the attributes you typed in a minute ago.

	
  * Close the **Table**

	
  * Turn off the **tif **layer in the TOC.


When you uncheck the layer you can see the feature class layers that you just created. It should look like this:

![20 Final Product](https://geospatialhistorian.files.wordpress.com/2014/04/20-final-product.jpg)

**_Note_**_: Digitizing is labour-intensive. Only digitize unique map features that will enable you to answer questions connected to your research and are not available elsewhere. For example, one would not digitize the township border represented on this map because this data is widely available elsewhere. Someone else has already done the work._
