---
author: joshmac
comments: true
date: 2014-11-27 21:58:15+00:00
layout: page
link: https://geospatialhistorian.wordpress.com/lessons/arcgis-lesson-3-georeferencing-maps/
slug: arcgis-lesson-3-georeferencing-maps
title: 'ArcGIS Lesson 3: Georeferencing Maps'
wordpress_id: 923
---

[Please Leave Comments and Suggestions for Revisions]

By: Geoff Cunfer, revised by Louis-Jean Faucher


## Introduction


This lesson will teach you how to georeference a scanned historic map as raster data in ArcMap.

There are two types of data in ArcGIS – vector and raster. The difference between the two is that vector data is made up of points, lines and polygons. Each point, line or polygon represents a feature on a map. Raster data is an image. As an environmental historian the first step in many analytical processes using historical GIS is to convert raster data to vector data, a process that begins with georeferencing.

One of the imitations of raster data resides in its cell resolution (or pixel size) which doesn’t prove useful when we zoom in close. One of the most valuable aspects to raster data is that it can be georeferenced. It is valuable because it allows researchers to conduct more detailed spatial analysis of the features in historic maps. Features shown on a raster map can later be “vectorized” meaning converted to vector data.


The 1954 historical erosion map used in this exercise comes from the U.S. National Archives, College Park, Maryland in the Soil Conservation Service documents found in RG 114, Entry 5, 330/c/17/2-1.


**Getting Started**



	
  * 

	
    * Download [the zipped file](https://drive.google.com/open?id=0ByEStot3aAG_ejU4VDhwOVhfZ28) and save in your **Documents\ArcGIS **folder (remember to unzip the folder).

	
    * From your computer desktop open the **ArcMap**


Begin by saving a new project file

	
    * Click **File **>** Save** (or **Ctrl-S**) and save to **ArcGIS_Lesson3\ProjectFiles **called **mxd**.







## **II. Add Reference Data**


(If you have trouble locating your folder, make sure you connected the ArcGIS_Lesson3 folder to ArcMap using the **Connect to Folder** button. ![3](http://geospatialhistorian.files.wordpress.com/2014/04/3.png)

If you unzipped the folder in **Documents\ArcGIS **you should be able to find it, but if you saved it elsewhere on your hard drive, you will need to use the **Connect to Folder **button.)

![Picture3](https://geospatialhistorian.files.wordpress.com/2014/11/picture3.png?w=265)



	
  * In ArcMap click the **Add Data** button ![adddatta](https://geospatialhistorian.files.wordpress.com/2014/11/adddatta.png)

	
  * Navigate to **ArcGIS_Lesson3\WindErosion1.gdb**and select the feature class called **GP_states_1930 **then click the **Add**


![Picture4](https://geospatialhistorian.files.wordpress.com/2014/11/picture4.png)![Picture5](https://geospatialhistorian.files.wordpress.com/2014/11/picture5.png)

On the left side of your screen in the **Table Of Contents** (TOC) a new layer appears represented by a coloured box below it.  On the right side of your screen appears a corresponding map of the 12 Great Plains states as they existed in 1930.

![Picture6](https://geospatialhistorian.files.wordpress.com/2014/11/picture6.png)

**_Key Concept_**_: Georeferencing is the process of assigning coordinates to an otherwise __“__unreferenced” image. These coordinates are obtained from a second dataset (raster or vector) that has a properly specified “spatial reference” (sometimes also referred to as “coordinate system”). Coordinates are tied to the image by identifying common geographic features also found in the reference dataset.
This process is sometimes called “rubber-sheeting” because it treats the scanned historic map as a sort of rubber sheet that can be stretched and manipulated to fit real world features.
When referred to as “georectification”, the process entails that a new image is created when the original is “warped”, or rectified._

The **GP_states_1930 **layer we just added is the reference layer and it MUST be added first because it provides the spatial reference or coordinate system for your unreferenced image.



	
  * Double-click on **GP_states_1930** to bring up its **Layer Properties**

	
  * Click on the **Source** tab and scroll down under the **Data Source** section to observe the layer’s **coordinate system** (USA_Contiguous_Albers_Equal_Area_Conic).


![Picture7](https://geospatialhistorian.files.wordpress.com/2014/11/picture7.png)



	
  * Click **Cancel** to close the window.




## III. **Symbolize and arrange map layers**


Now you will “symbolize” (change the graphic representation) of the **GP_states_1930** layer.



	
  * Click on the coloured box beneath **GP_states_1930**. The **Symbol Selector** dialog appears.

	
  * Select the **Hollow box** Make the **Outline Color** black and the **Outline Width** = 2.

	
  * Click **OK**.




## **IV. Add the Georeferencing toolbar**


The tools required for georeferencing are not currently displayed in ArcMap. You must add the appropriate toolbar first.



	
  * Click **Customize** > **Toolbars** > **Georeferencing** to display the toolbar.


![Picture8](https://geospatialhistorian.files.wordpress.com/2014/11/picture8.png)

You now have his new toolbar:

![Picture9](https://geospatialhistorian.files.wordpress.com/2014/11/picture9.png)



You may wish to anchor the toolbar to the ArcMap window (or leave it floating, as you prefer). To do so:



	
  * Click the toolbar by its name, slowly drag it above the map display, then drop it.




## **V. Adding Scanned Images**


The next step is to add the scanned images that you are going to georeference.



	
  * Click the **Add Data** button![adddatta](https://geospatialhistorian.files.wordpress.com/2014/11/adddatta.png)

	
  * Navigate to **ArcGIS_Lesson3\Scans** and select the **ErosionMap1954a.tif** raster image, then click the **Add** button


A dialog window appears where ArcMap will ask if you want to create Pyramids

	
  * Select **Yes**.


ArcMap will then inform you that the spatial reference to this file is unknown (the purpose of this lesson is to add spatial reference to the raster image).

![Picture10](https://geospatialhistorian.files.wordpress.com/2014/11/picture10.png?w=300)



	
  * Click **OK**.

	
  * The new raster layer appears in the TOC to the right.

	
  * Rename the layer from **tif **to** Erosion Map**.


Even with the checkbox turned on, the layer does not display on your map because ArcMap does not know where to display it, or where to anchor it to the map in relation to other layers.

**_Note_**_:__  In the future when you add a layer to your map and it does not appear on your screen with your other layers the problem is likely that, like this layer, ArcMap does not know what to do with it because it lacks a coordinate system._

Have a look at the image you just added before you georeference it.



	
  * Right-click on the **Erosion Map** layer and select **Zoom to Layer**.


This will allow you to see the **Erosion Map** image (ArcMap has arbitrarily placed it at coordinate 0,0 at the “origin” of the coordinate system’s x and y axes).



	
  * Click the **Full Extent** button ![Picture11](https://geospatialhistorian.files.wordpress.com/2014/11/picture11.png)in order to zoom back to the states layer.

	
  * Change the symbol of the **GP_states_1930**layer to make its **Outline Colour**




## **VI. Georeferencing the Map**


Now you need to bring the scanned Erosion Map image and the reference Layer (the States boundaries) together as best you can. This will make georeferencing much easier.



	
  * From the **Georeferencing** menu, select **Fit To Display**.


![Picture12](https://geospatialhistorian.files.wordpress.com/2014/11/picture12.png)

This will cause the Erosion Map layer to move within the map extent with the states layer. You will make them line up soon.

**_Note_**_: Look for common features between the reference layer and the unreferenced image. Are there features that can be clearly recognized on both maps? It is important to take a moment to look for these because they will help you plan where to place “control points” to tie the layers together. This map has easily recognizable and unchanged political boundaries to work with. You may sometimes have to use a road layer as a reference and identify common intersections. Certain maps contain few or no man made features and you may have to identify common stream or coastal features from a hydrography layers. Natural features have a tendency to be more dynamic and can change fast or drastically over time, this making the georeferencing more difficult less accurate._


## **VII. Adding Control Points**


**Control Points** are placed where common features are found on both the unreferenced image and the reference layer. The process of georeferencing involves you clicking on a feature from the unreferenced image and then clicking on the same feature from the referenced layer. This tells ArcMap that this point is the same on both layers. ArcMap then adjusts the image you are georeferencing to fit the reference layer.

A minimum of 3 control points are needed to rotate and scale the image. 6-10 control points will allow you to perform further stretching and warping of the image. Placing 20 control points or more can ensure a greater adjustment or higher accuracy but is also much more difficult and time consuming. Control points should be spread out as evenly as possible over the whole map and ideally in all 4 corners, if there are enough identifiable common features to do so.

![Picture13](https://geospatialhistorian.files.wordpress.com/2014/11/picture13.png)

_Tip__: While adding Control Points you will be required to zoom in and out quite often.
The easiest way to do so is to use the **Zoom In** / **Zoom Out** tools. A quick zoom to
**Full Extent** will take you back to your starting extent. You may also use keyboard
shortcuts to make the task easier. Press and hold **Z** for Zoom In, **X** for Zoom Out, and **C** for the Pan tool._

You want to start by zooming to an area of the map where you identified common features.



	
  * **Zoom In** to the Northwest corner of the map at the Montana border.

	
  * From the **Georeferencing** toolbar select the **Add Control Points** tool ![Picture14](https://geospatialhistorian.files.wordpress.com/2014/11/picture14.png)


As you can see both corners of the border are clear and you can easily place your cursor to accurately match them.

	
  * First, click on the corner of the border in the unreferenced image.

	
  * Next, click on the corner of the border in the referenced states layer.


![Picture15.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture15.png)

The image corners automatically line up as such:

![Picture16.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture16.png)



	
  * Click the **Full Extent ![Picture11](https://geospatialhistorian.files.wordpress.com/2014/11/picture11.png)** button zoom back out and see what has changed.


The image should now start to align with the states layer, but is still off enough that additional points are needed. Repeat the process with the Southwest corner of New Mexico, the Northeast corner of North Dakota, and the Northeast corner of Texas. After you have placed at least 4 control points, your map should look something like this:

![Picture17.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture17.png)



	
  * From the **Georeferencing** toolbar click the **View Link Table** ![18](https://geospatialhistorian.files.wordpress.com/2014/04/18.png)  to see the mathematical conversion at work behind what you have just done.


![Picture18](https://geospatialhistorian.files.wordpress.com/2014/11/picture18.png)

**_Note_**_: ArcMap calculates the relative accuracy of each pair of control points and provides an approximation of the offset (in this case, in metres) between each, listed as the **Residual** error. A higher value indicates a higher probable offset._

_Georeferencing __is an imperfect process and the goal is to get is as accurate as you need it to be; know the scale of your map and what you need it for. Do not stress about the map being off because it will be no matter what; you need to decide HOW off your map can be and still be useful to you._



	
  * Place 3 more control points.

	
  * Open the **View Link Table**again and click the **Transformation:**


![Picture19.png](https://geospatialhistorian.files.wordpress.com/2014/11/picture19.png)

Notice there is a **2nd Order** transformation available, and selecting it produces a lower **Residual error**. This is the difference between simply rotating and scaling the image, vs stretching and bending of the image which produces a more flexible fit and a lower error.

Placing control points is an **_iterative_** process. You place a few points, open the **Link** table, look at the Residual values. Place a few more points, look at the Link table, delete a couple of points with the highest offset. Place a few more points, look at the Link table, delete a couple of points with the highest offset. Repeat until you are satisfied with the result.

**_Tip_**: If your geocoding should go completely off the rails, you may want to delete all control points and start over from **Fit To Display** in the _VI. Georeferencing the Map_ section.

On the **Link** table you will see there is something called the **Total RMS Error**. It stands for is Root Mean Square Error. This shows an overall error based on all points _(in this case, in metres)_. An RMS Error of ~1000 means that the average pixel in the map is a little over 1km off its real world location. The RMS is really a matter of scale. If the scale of your project is small (large area like province or country), 1km off is not bad; if the scale of your project is large (small area like a city or neighbourhood) you want to make sure the RME Error low enough to produce accurate results.


## VII. **Preserving the georeference**


At this point you have set your control points and accepted the RMS Error as one you are willing to work with. Now you need to make the georeferenced permanent and save this information alongside the image file so you don’t have to redo this work again for future GIS projects.



	
  * Go to **Georeferencing** toolbar and click on **Update Georeferencing**.


This creates a companion file for the **ErosionMap1954a.tif**. The new file has the same name but its extension is **.tfw** or **.tfwx** and it must stay along the image file for the georeference to be preserved.

![Picture20](https://geospatialhistorian.files.wordpress.com/2014/11/picture20.png)

Alternatively, you can use the **Georeferencing** > **Rectify** method to apply the georeferencing to your image. The difference is that **Rectify** writes a NEW image file to disk, with the georeference saved permanently within the file.



	
  * Close ArcMap without saving.


There is no need to save your map document because we have only manipulated data rather than symbolized layers and created a map for analysis.

Now to verify that the georeference has been preserved.

	
  * Open ArcMap.

	
  * Add the GP_States_1930 feature class as a layer

	
  * Add the ErosionMap1954a.tif image from your folder.


The two maps should line up and you don’t get a warning message regarding spatial reference. The Erosion Map layer is ready for digitizing (turning raster data into vector data) in the next lesson!
