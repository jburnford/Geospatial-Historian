---
author: mtoddy42
comments: true
date: 2014-04-10 21:40:19+00:00
layout: post
link: https://geospatialhistorian.wordpress.com/?p=779
published: false
slug: georectifying-in-arc10-2-using-great-plains-data
title: 'Arc 2: Georectifying in Arc10.2  Using Great Plains Data'
wordpress_id: 779
---

**Georectifying in Arc10.2
**

By: Matt Todd,

HGIS Laboratory, University of Saskatchewan

This exercise will teach how to georectify Raster data in ArcMap10.2. There are two types of data in ArcGIS—Vector and Raster. The difference between the two is that Vector data is made up of points, lines and polygons. Each point, line or polygon designates a feature on a map. Raster data is an image. As an environmental historian the first step in the majority of my analyses using ArcMap is to convert Raster data to Vector data, a process that begins with georectification.
This lesson will use a scanned historic map as the Raster data. One of the difficulties with Raster data is that because it is an image when we zoom in close the data can distort; however, one of the most valuable features to Raster data is that is can be georectified, that is, “warped” or “rubber-sheeted” to real geographic features allowing for analysis.

**Getting Started**

Step 1: Download the data from Dropbox: [https://www.dropbox.com/s/2qcoxxo7su8d07b/Georectifying%20Docs.zip ](https://www.dropbox.com/s/2qcoxxo7su8d07b/Georectifying%20Docs.zip%20) and move it to your C drive, desktop, or other spot that is easy to navigate to.  The file is called: Georectifying Docs. This is important because ArcMap will need to be able to find the data.

Step 2: Open ArcMap and Select Blank Map, press ok

**Add Reference Data**
Step 3: When looking at your screen in the top-left, directly under “Selection” you will see [![9](http://geospatialhistorian.files.wordpress.com/2014/04/9.png)](http://geospatialhistorian.files.wordpress.com/2014/04/9.png)this is a the “add data” tab. Left click on this tab and scroll to “Add- Data”
This opens the Add-Data dialogue window
[![2](http://geospatialhistorian.files.wordpress.com/2014/04/2.png?w=300)](http://geospatialhistorian.files.wordpress.com/2014/04/2.png)

On the right of the window there is [![3](http://geospatialhistorian.files.wordpress.com/2014/04/3.png)](http://geospatialhistorian.files.wordpress.com/2014/04/3.png), left click on this folder. From here select the area on your computer where the data for the lesson is stored
Select this area (for me it was desktop, to lessons) click “Add”
Select [![4](http://geospatialhistorian.files.wordpress.com/2014/04/4.png)](http://geospatialhistorian.files.wordpress.com/2014/04/4.png), click "Add".

The layer you want to add is [![5](http://geospatialhistorian.files.wordpress.com/2014/04/5.png)](http://geospatialhistorian.files.wordpress.com/2014/04/5.png), select this layer and click "Add"

This will bring up the map here (although it may not be green)[![6](http://geospatialhistorian.files.wordpress.com/2014/04/6.png?w=240)](http://geospatialhistorian.files.wordpress.com/2014/04/6.png)

Why did we just do this? A new map can only be georeferenced to an existing georeferenced layer with similar features. The layer we just added is called the “Reference Layer” and it is ALWAYS added first because it provides the co-ordinate system and projection for your unreferenced map.

**Getting the Reference Layer Ready**
Step 4: On the left hand side you will see  [![7](http://geospatialhistorian.files.wordpress.com/2014/04/7.png)   ](http://geospatialhistorian.files.wordpress.com/2014/04/7.png)Right click on the green square to bring up the “Symbol Selector” dialogue window. On “Fill Color” choose “no color”. Next, increase outline width to 2 and change the color to red, select “ok”. The reason we are changing the colors and thickness of lines is that these small changes will make georeferencing easier later on.

**Adding Tool Bars**

The tools required for georeferencing are not sitting open on your version of ArcMap right now, we need to add them.
Step 5: Find the Customize tab (between Geoprocessing and Windows). Left click on Customize, hover the cursor over “toolbars” and select “georeferencing”. After doing so you will now have this: [![8](http://geospatialhistorian.files.wordpress.com/2014/04/8.png?w=300)](http://geospatialhistorian.files.wordpress.com/2014/04/8.png)

The best way to deal with this “toolbar” is to drag it to the top of your screen and “park-it” next to your other toolbars. If it appears already “parked” at the top of your screen just leave it where it is.

**Adding Scanned Images**

The next step is to add the scanned images that you are going to georectify.
Step 6: Click the Add Data [![1](http://geospatialhistorian.files.wordpress.com/2014/04/1.png)](http://geospatialhistorian.files.wordpress.com/2014/04/1.png) button. Navigate to the “Scans” folder right click to highlight and then click “Add”.

Step 7: Select** ErosionMap1954a.tif**, and select “Add”.

Step 8: This will open another dialogue window where ArcMap will ask if you want to create Pyramids, you do so select yes. ArcMap will then inform you that the spatial reference to this file is unknown (the purpose of this lesson is to add spatial reference to the file so this message seems a little rhetorical) you should, again, click Ok.

Tip: On the left side of the screen you will see an addition to your Layers, this is the map you just added. In the future when you add a layer to your map and it does not appear on your screen with your other layers the problem is likely that, like this map, ArcMap does not know what to do with it because it lacks a coordinate system or the coordinate system it has is different than the other layers.

If you want to have a look at the new map before you georectify it right click on ErosionMap and select “Zoom to Layer”. This will allow you to see the ErosionMap image but not the States image. Select the Full Extent button [![13](http://geospatialhistorian.files.wordpress.com/2014/04/13.png)](http://geospatialhistorian.files.wordpress.com/2014/04/13.png) in order to get back to the States layer.

**Georeferencing the Map**

Step 9: Now you need to bring the scanned image (ErosionMap) and the Reference Layer (the States boundaries) together as best you can. This will make georeferencing much easier. In your table of contents (along the side) click on ErosionMap so that it is highlighted. Then, from the georeferencing tool bar, select [![11](http://geospatialhistorian.files.wordpress.com/2014/04/11.png)](http://geospatialhistorian.files.wordpress.com/2014/04/11.png) and then “fit to display”. This will cause the ErosionMap layer to sit on top of the States layer. While they do not line-up, they soon will.
Tip: Before you start adding control points look at the maps together. Are there common features? Are there similar boarders (especially where states come together)? It is important to take a moment to look for these because they will help you plan where to put your control points. This small step can save a great deal of time and frustration. As a side note, if your maps do not have State, country, or county boarders I like to georectify from roads or other prominent geographic features, like rivers.

**Adding Control Points**

**Control Points** are points that appear on the map you are georeferencing AND the Reference Layer. The process of georeferencing is simply you telling ArcMap that this point is the same on both maps and ArcMap adjusting the map you are georeferencing to the Reference layer. Generally, 4-10 control points, spread out over the whole map and ideally in all 4 corners, are required to properly georeference a map.

Tip: While adding Control Points you will be required to zoom in and out quite often. The easiest way to do so is to use [![12](http://geospatialhistorian.files.wordpress.com/2014/04/12.png)](http://geospatialhistorian.files.wordpress.com/2014/04/12.png) on the top left of your screen. A quick zoom-out is the [![13](http://geospatialhistorian.files.wordpress.com/2014/04/13.png)](http://geospatialhistorian.files.wordpress.com/2014/04/13.png) which will take you back to your starting extent.

Step 10: Visually select a point on the maps where you would like to begin. I tend to work from left to right but it’s up to you. Now, zoom in on that spot to roughly here: [![14](http://geospatialhistorian.files.wordpress.com/2014/04/14.png?w=300)](http://geospatialhistorian.files.wordpress.com/2014/04/14.png)

As you can see both corners of the boarder are clear and you can easily get your cursor to accurately select them.
Step 11: From the Georeferencing toolbar select the Add Control Points tool [![19](http://geospatialhistorian.files.wordpress.com/2014/04/19.png)](http://geospatialhistorian.files.wordpress.com/2014/04/19.png) Now select a point on the map you are georeferencing (ErosionMap) and select the corresponding point of the Reference Layer and double click. Hit the [![15](http://geospatialhistorian.files.wordpress.com/2014/04/15.png)](http://geospatialhistorian.files.wordpress.com/2014/04/15.png) to see what has changed.

Tip: I like to hit the [![15](http://geospatialhistorian.files.wordpress.com/2014/04/15.png)](http://geospatialhistorian.files.wordpress.com/2014/04/15.png) after every control point. I feel like I am getting a better look at how things are progressing.

The maps should now have come together quite a bit, but still off enough that additional points are needed. Repeat the process (if I start on the top left I like to make my next point on the bottom right. On this map Bowie County, Texas works well for a second point). After you have made at least 4 points your map should look something like this: [![17](http://geospatialhistorian.files.wordpress.com/2014/04/17.png?w=220)](http://geospatialhistorian.files.wordpress.com/2014/04/17.png)



Step 12: Now, select the View Link Table [![18](http://geospatialhistorian.files.wordpress.com/2014/04/18.png)](http://geospatialhistorian.files.wordpress.com/2014/04/18.png) from your Georeferencing toolbar too see the math behind what you have just done and the distance error for each link. If there is a high error on one of the points consider deleting it by clicking on it and hitting “delete” on your keyboard. However, feel free to use your eyes for accuracy as well.

Tip: this is an imperfect process and the goal is to get is as close as possible. Do not stress about the map being off because no matter what it will be, you need to decide HOW off your map can be and still be useful to you (more on this below).

Tip: If things should go completely off the rails I find it is best to delete all of my points and start over from “Fit to Display” in Step 9 in **Georeferencing the Map.**
On the Link Table you will see there is something called the RMS Error. What this stands for is Root Mean Square Error. This shows an average error based on all points, in the case of this map it is in meters. An RMS error of 1123.45 means that the average pixel in the map is a little over 1km off its real world location. The RMS is really a matter of scale. If the scale is global 1km off is not bad; however, if your scale is a city then perhaps there are new control points to be added or existing ones to be removed.

Tip: I like to think of the RMS Error in terms of the scene from Raiders of the Lost Ark where the Nazis are looking for the Well of Souls in the wrong place. Without the headpiece of the staff of Ra the Nazis did not know its correct length (it says 6 kadams which they knew, but, to return one to honor God making the true length 5 kadams which they did not know). As a result, they made the staff too long and their location of the Well of Souls was way off due to the resulting problem of scale. Had the scale of the map of Tanis been larger 1 kadam one way or the other may not have made a difference and the movie would have been 45 minutes shorter. The point is, know the scale of your map and what you need it for.

**Finalizing Your New Georeferenced Map**

At this point you have set your control points and accepted the RMS error as one you are willing to live with and I am sure the temptation to close everything down is pretty unbearable, but there are 3 more steps.

Step 13: While the map looks like it is finished you have not altered the underlying .tif file. In order to make the transformation permanent (and therefore usable for future GIS projects) go to the Georeferencing toolbar and select Update Georeferencing. This will finalize the changes to the tif file.

Step 14: you can now close ArcMap. There is no need to save because we have only manipulated data, not altered a map for print.

Last Step (promise): Re-open ArcMap and add the GP_States_1930 layer (your Reference Layer) and then add the ErosionMap1954a.tif image from your folder. The two maps should line up. If they do, the ErosionMap layer is ready for digitizing (turning Raster data into Vector data!).

A special thanks to Dr. Geoff Cunfer for supplying the data and for teaching me GIS for the last 7 years, Dr. Jim Clifford for his assistance with blogs, and Mike St. Louis for helping me with everything GIS related.
