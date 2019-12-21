---
author: cljim22
comments: true
date: 2014-11-27 22:00:30+00:00
layout: post
link: https://geospatialhistorian.wordpress.com/2014/11/27/arc-5-map-design-with-arcgis/
slug: arc-5-map-design-with-arcgis
title: 'Arc 5: Map Design with ArcGIS'
wordpress_id: 893
---

**Introduction**

This exercise has three goals:  1) to review and reinforce GIS skill learned so far; 2) to put some of the design and symbolization principles from [Monmonier’s _Mapping it Out_](http://www.press.uchicago.edu/ucp/books/book/chicago/M/bo3645221.html) into practice; and 3) to learn how to create a map layout for print or export.

The example included here address how much and where land was plowed for crops in the 1930s.  It brings together maps based on two distinct spatial primary sources:  the 1935 Agricultural Census and a set of digitized aerial photos taken in Weld County, Colorado in 1938.





	
  1. ** Add data**


All data are in the **Workshop 5** folder.  For this exercise we’ll use two of the same datasets as in the previous Overlay Excercise.



	
  1. From the **Design1.gdb** geodatabase add the following polygon layers:



	
  * **Weld_1930s** (land use polygons digitized from a sample of 1938 air photos—8 cells of 9 square miles each)

	
  * **AgCensus_1935** (land use attributes from the 1935 agricultural census for all Great Plains counties)



	
  2. Save your project by clicking the Save button, navigating to your **Workshop 5** folder, and assigning an appropriate name. This will create a single file with the extension .mxd. Most of the finished maps you create for final output in ArcMap will be saved with an .mxd extension.  Each time you want to change a map design, you should immediately save it as an .mxd file with a new name, using the Save or Save As commands.  Today, you should click Save about every 10 minutes or so as you go along.



	
  1. ** Explore data**



	
  3. Locate the small air photo polygons in relation to the much larger county map. Look at the attribute tables for the 2 polygon layers in order to understand the information they contain. For the **AgCensus_1935** layer you can refer to **04254-0009-Codebook.pdf** for variable descriptions.  Keep in mind the two very different scales represented by these two datasets.


**III. Sybmolize data**



	
  4. Make a map showing the amount of cropland in each county of the Great Plains. The best attribute for this map is **CRP_XK_A**. For the county-level **AgCensus_1935** layer, choose an appropriate symbolization scheme.   (You may need to refer to Workshop I:  Mapping Great Plains Agriculture section V. Sybolize attribute data to refresh your memory.)  To start, right click on the **AgCensus_1935** layer name in the Table of Contents and go to Properties and then the Sybmology tab.  For this map, the Quantities, Graduated colors options are most appropriate.  You’ll need to set the Value field to **CRP_XK_A**, select a color ramp you like, and choose a number of classes (then click Classify to determine the range of each class).  The result should be a map of counties in which those with the most cropland are darkest in color, and those with little cropland are lightest in color.



	
  5. Now zoom in to the **Weld_1930s** aerial photo layer, and sybmolize this map to show the locations of cropland in each cell. Again, you’ll right click on the **Weld_1930s** layer name in the Table of Contents, then select Properties and the Symbology tab. This time you’ll select Categories, Unique values.  Set the Value Field to **Land_cover** and click the Add All Values button below.  From this window you can set the color for each type of land cover identified from the air photos.  In this case we want to highlight the Cropland polygons only (perhaps using the same color as in your county map?), and set all other polygons to show a black outline with no fill.



	
  1. ** Separate layers into two data frames**


Once you have both maps designed to your satisfaction, you’ll have to confront the fact that it will be very difficult to present these two maps at the same scale, since one covers only a small part of a single county and the other covers more than 1000 counties.  If you zoom the map so that one is visible, the other becomes hopelessly obsured.

One solution is to present the maps at two different scales on your layout.  In cartography, this approach is called an “inset map” or a “locator map.”

	
  6. So far in this class we’ve only employed one data frame, which in the Table of Contents is called Layers. Now it is time to branch out. Go to Insert and select New Data Frame.  Notice that in the Table of Contents the label New Data Frame has appeared in bold, and your maps have disappeared from the map window.  Right click on Layers and select Activate:  it becomes bold, New Data Frame is no longer bold, and your maps have reappeared.  In Data View, you can only see and work with one data frame at a time.


You can create as many data frames as you want, and when you Add Data to insert layers, the new maps, tables, or images will appear only in the currently active data frame (although it is easy to then drag them to other data frames if you want the same map in more than one).

	
  7. Rename the two data frames. Right click on Layers, select Properties, and then the General tab. Change the Name to read “Weld County Cropland.”  Now do the same to change the name of New Data Frame to read “Great Plains Cropland.”



	
  8. Click on the **AgCensus_1935** layer and drag it down to the Great Plains Cropland data frame. A duplicate map layer appears with all of your symbolization intact. We don’t need the original any more, so right click on the original **AgCensus_1935** layer and select Remove to delete it from the Weld County Cropland data frame.



	
  9. Zoom to the full extent of both maps. Activate Weld County Cropland then click the Zoom to Full Extent button. Activate the other data frame and do the same.


You’ve now put your two maps in separate data frames, and selected a scale that is appropiate to each.  Great—but now you can no longer view the two maps at the same time.  Because we are working in Data View, we can only deal with one data frame and scale at a time.

	
  1. ** Create a layout**



	
  10. Now it is time to discover a section of ArcMap we haven’t dealt with yet: the Layout View. So far, all of our exercizes have taken place in Data View, which is the nuts-and-bolts mechanical part of ArcMap, where the interesting GIS analysis and basic symbolization takes place.  But once the hard core analysis is done and the map is symbolized to your satisfaction, we need more artistic options, and that’s where Layout View comes in.




Look in the map window section of the ArcMap interface, and go down to the bottom left corner.  Two tiny icons to the left of the scroll bar allow you to toggle between Data View and Layout View.  First, hold your mouse over each to confirm that you’ve found the right buttons—they’re not easy to spot.  Then click on Layout View.



Now you see a mocked-up page with your two maps both visible, though probably not where you want them to appear.  Layout View mimicks graphics programs like Adobe Illustrator (although with many fewer functions), so you might find commands that are familiar from that environment.  Here you can do the final design for an output map.



Key concept:  Complete all analysis and map symbolization in Data View _before_ you start working in Layout View.  Going back later to change color choices, data categories, or the scale will often create havoc in Layout View, requiring re-working your final map design.  After years of heartache, take this advice from a grizzled veteran!



Note:  the program defaults to a Portrait layout, but you can change to Landscape if you like.  It also defaults to an 8.5 x 11 inch page size, but this can be re-set.  Make both changes by going to File and selecting Page and Print Setup.





	
  11. Click on each map to highlight its window, which can be dragged to a new location or resized by clicking on an anchor around the outside. Arrange the 2 maps as you like on the page. If you think that the **Weld_1930s** maps are still too hard to see, you could consider going back into Data View and zooming in on only one of the cells.  Then you would come back to Layout View to complete the map.




	
  12. From the Insert menu, insert each of the following map elements. In each case, use your own design sensibilities to choose from among the many options offered.




	
  * Title (create one)

	
  * Scale bar (one for each map, since they are at different scales)

	
  * Text box (in which you should identify the map author and date)

	
  * North arrow

	
  * Legend (one for each map, unless you used the same colors for both)




You can drag these elements into correct position, resize them, and format text (double click on the element, click the Text tab, and click Change Symbol) as you like.  If you don’t like the outcome, just select the element, hit delete, and start again.



Warning:  While it is very helpful to zoom in and out on the page and pan around as you do the design work, be careful to use only the zoom and pan buttons for the Page View (and not the very similar buttons connected to Data View).





	
  1. ** Generate a final map**




	
  13. Once you are satisfied with your map layout, you can create two kinds of output. First, print a hard copy, by going to File and selecting Print. In order to get full color, send it to HP Color LaserJet CP4005 PCL6, which is the color laser printer in Kirk 213.




	
  14. Then export a .jpg file of your map, which could be used to post to a web site or to insert into a word document. Go to File and select Export Map. From the dialog box, set Save as Type to JPEG.  Here you can also adjust the resolution if you like (many publishers specifiy 300 dpi for print graphics, while web designers like 150 dpi or even lower for online purposes).  You can save the file to your Workshop 5 folder, then copy and paste it into a Word document.


