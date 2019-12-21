---
author: sabre686
comments: true
date: 2019-12-21 16:42:22.633233
layout: post
link: https://geospatialhistorian.wordpress.com/?p=862
published: false
slug: No Content Found
title: 'Workshop V:  Digitizing Archival Maps'
wordpress_id: 862
---

This exercise has two goals.  First, it reinforces the basic GIS methods and concepts initiated in earlier exercises.  Second, it introduces the concept of digitizing, by which it is possible to extract features from a paper map and bring them into a GIS.



This exercise uses a map scanned by Geoff Cunfer during a research trip to the archives of the Kansas State Historical Society in Topeka, Kansas.  The archive holds paper copies of land ownership maps from across the state, but does not allow researchers to handle the originals.  Instead, they are available only on microfilm.  Cunfer printed the image from a microfilm machine, then scanned it with a normal flatbed scanner.  The map’s main purpose is to show who owns which parcels of land in Logan Township, Rooks County, Kansas, and it dates to 1905.  “Plat maps” like this one are important artifacts of our property rights regime and are common across North America.  They contain rich information about social structure, class, land use, and many other aspects of rural life.





	
  1. ** View archival map image**




	
  1. Open the **Scans** folder and double click on the image **Plat_LoganTwp_1905.tif** to launch Photoshop or another image viewer. Use the zoom and pan tools to inspect the map closely.




Now think about this map from a GIS perspective.  If you were to categorize the map’s many features into distinct map layers, what would they be?  List the layers of spatial information contained in this map.

Key concept:  GIS map data appear as layers of map features that can each be manipulated and symbolized independently.



	
  2. Next, distinguish the layers you have identified into the three basic GIS data types: points, lines, polygons.


Key concept:  Vector map data come in three different forms:  points, lines, and polygons.



	
  3. Now connect _map attributes_ to _map layers_. Identify attribute information included on this map.


Key concept:  Attribute data are descriptions of geographic places.  Examples of attributes include things like the total population of a county (polygon), the speed limit along a segment of road (line), or the temperature at a given time at a weather station (point).  The list of possible attributes about the world is infinite, but specific maps often focus on particular attribute information.



	
  4. Close the map image.






	
  1. ** Import map data to ArcMap**




	
  5. In order to digitize this map, we first need to georeference it. Copy and paste the scanned map from the **Scans** folder into the **GeoreferencedScans** folder. We are going to alter the data files, so it is important to keep a clean copy of the original scan separate, in case we make a mistake and have to start over.




	
  6. From your computer desktop open a blank project in the ArcMap software.




Note:  For now we’re doing data processing, and not creating a finished output map.  For this reason, there is no need to save a project file (.mxd), nor to click the save button.



	
  7. Import the scanned image you want to georeference. Click the Add Data button (a yellow diamond with a black plus sign) [![1 Add Data Button](http://geospatialhistorian.files.wordpress.com/2014/04/1-add-data-button.png)](http://geospatialhistorian.files.wordpress.com/2014/04/1-add-data-button.png) and navigate to **Workshop5/GeoreferencedScans**. [![2](http://geospatialhistorian.files.wordpress.com/2014/10/2.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/2.png)Select **Plat_LoganTwp_1905.tif** and click Add.  ArcMap will ask if you want to create pyramids for this raster.  Click Yes.  It will then notify you that this file’s spatial reference is unknown.  You are aware of that, of course, because the task at hand is to _add_ a spatial reference to this image.  Click OK.




	
  8. Import the reference map layer. The reference map for this exercise is a map of township boundaries in 25 Kansas counties. Click the Add Data button (a yellow diamond with a black plus sign) and navigate to the geodatabase in **Workshop5** called **Digitizing1.gdb**.  Double click it, select **Sample_Townships_1905**, and click Add.




Key concept:  In order to georeference an archival map it is necessary to align it with an existing GIS layer with common features, called the “reference layer” or the “target data.”  Add the scanned image first, then add the reference layer.  The coordinate system and projection of the reference layer will be applied to the scanned map when you digitize it, so make geospatial adjustments, if needed, before digitizing.



Note that while the **Sample_Townships_1905** layer now appears in the Table of Contents, you can’t see it on the map window.  This is because ArcMap doesn’t know how it relates to the scanned map.  If you ever add map data to a GIS project and it seems invisible, it is quite likely that the coordinate system is either missing or is different from the other layers in the project.



In the Table of Contents, right click on **Sample_Townships_1905 **and select Zoom to Layer.  Now you can see the reference layer, but not the scanned image.[![4](http://geospatialhistorian.files.wordpress.com/2014/10/4.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/4.png)



This map layer is represented in an Albers Equal Area projection.  That means that your georeferenced map image will also be in this projection.  If you want your output map in a different projection, make that change _before_ georeferencing.



Re-symbolize the township polygons to make them outlines (no fill, red outline with 1 pt. width).  Try changing these settings on your own. [![5](http://geospatialhistorian.files.wordpress.com/2014/10/5.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/5.png)



If you don’t remember how, then follow these instructions:  In the Table of Contents, click once on the patch under **Sample_Townships_1905** to open the Symbol Selector.  Change Fill Color to No Color, change the Outline Width to 1, and change the Outline Color to red.  Click OK.



If it is not already present, add the Georeferencing toolbar by clicking on the Customize menu at the top of the window.  Select Toolbars then click Georeferencing to launch this specialized set of tools, which you can drag to the top or side of your window.







**III. Georeference the scanned map**





	
  9. Our scanned image is of just one township, but our reference layer contains dozens of townships. Which one should we use? Find and select the correct township using the reference layer’s attribute table.  Remember that the scanned image is a map of Logan Township, Rooks County.  (Hint:  In the Table of Contents right click on **Sample_Townships_1905** and select Open Attribute Table.)[![6](http://geospatialhistorian.files.wordpress.com/2014/10/6.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/6.png)




Once you have selected the correct township (and it is highlighted in blue), zoom in so that it fills the map window.



	
  1. Align the scanned image approximately with the township boundaries. In the Table of Contents, click on **Plat_LoganTwp_1905.tif **to highlight it. From the Georeferencing toolbar, click Georeferencing and select Fit to Display.  Now you can at least see both the township boundaries and the map image at the same time, although they are not yet positioned accurately.[![7](http://geospatialhistorian.files.wordpress.com/2014/10/7.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/7.png)




Compare the scanned map with the reference map.  Can you see some common map features?  In this case, only the four sides of the township boundaries are common to both maps.  Use the four corners of the township as control points for georeferencing.  In this case there are only 4 good control points to use—luckily they are distributed at the extreme extent of the map, and so should give a good result.



Key concept:  “Control points” are known locations that appear on both the reference map and the scanned image.  You georeference an image by informing ArcMap that these control points are the same on both maps.  That is, you identify a pixel on the scanned image with its corresponding location on the reference map.  The software then executes a mathematical algorithm that adjusts all other pixels in the image accordingly.  You should normally have 4-10 control points, and your georeferencing will be most accurate if you can spread the control points around the map, rather than concentrating them in a small area.  A good rule of thumb is one in each corner of the map and a few spread around the middle.



	
  1. Adding control points often requires zooming in and out and panning around the image in between steps. Zoom in as much as possible, while keeping the current control point on both the scanned image and the reference layer in the window. From the Georeferencing tool bar, click the Add Control Points button (a green + and a red + joined by a small blue arrow).[![19](http://geospatialhistorian.files.wordpress.com/2014/04/19.png)](http://geospatialhistorian.files.wordpress.com/2014/04/19.png)First click on a known location on the raster image, then click on the corresponding location on the state boundary map.  The image will automatically align with the point you just specified.  Although the rest of the map will still be out of synch, it is probably already a lot closer than it was before.[![8](http://geospatialhistorian.files.wordpress.com/2014/10/8.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/8.png)




Zoom and pan around the image as necessary to bring your next control point onto the screen, on both the scanned map and the township boundaries layer.  Click the Add Control Point button again and repeat the process, adding 4 control points.  Each one should make the image more and more closely aligned.



	
  2. On the Georeferencing toolbar click the View Link Table button (small square with red and green links)[![18](http://geospatialhistorian.files.wordpress.com/2014/04/18.png)](http://geospatialhistorian.files.wordpress.com/2014/04/18.png)to view the mathematics behind your transformation. The residual column shows the distance error for each link (depending on the accuracy of the other links) in map units (in this case, meters). If one or more of the links have high residual values, you could consider deleting it and recreating the links in hopes of greater accuracy.




Record the Total RMS Error here:  __________________  Close the Link Table.



The Root Mean Square error shows an average error based on all of the control points.  For example, an RMS error of 20.76 means that the average pixel in the map image is a little over 20 m off from its real world location (assuming all control points are exactly correct).  The level of accuracy that you need depends on the scale you are working at.  For example, with a map of the world, 1km accuracy may be just fine, whereas with a map of a single city block, 1km accuracy would be insufficient.  In this case, the accuracy is limited by the poor quality of the scanned image, which has been distorted at least 3 times (once by the microfilm capture, again by the microfilm printer, and a third time by the flatbed scanner).  For high quality georeferencing, high quality image capture is necessary.



	
  3. So far you have changed the scanned map image on your screen, but not altered the underlying .tif file. Instead, ArcMap has created some extra files in your **GeoreferencedScans** folder that record all of the transformation data. If you look in that folder, you may see some extra files named **Plat_LoganTwp_1905.tif.aux.xml** and **Plat_LoganTwp_1905.tif.ovr**.  You don’t need to do anything with these files, but if you later wanted to recreate your transformation, you could use them to do so.




Today, however, we are going to make our transformation permanent so that we can use it in future GIS projects.  From the Georeferencing toolbar, click Georeferencing and select Update Georeferencing.  This embeds your changes into the scanned map’s underlying .tif file.



	
  4. Close ArcMap. There is no need to save changes to the project, since we’ve only manipulated data, not created a new output map for printing.




	
  5. Re-open ArcMap. First add the **Sample_Townships_1905** layer, as you did above. Then add the **Plat_LoganTwp_1905.tif** image from the **GeorectifiedScans** folder.  This time, it comes in aligned with the reference map.  (Drag it to the top of the Table of Contents so you can see it over the township map.)  It is now ready for digitizing or for use as a background image with other GIS data displayed on top.  Close ArcMap without saving.






	
  1. ** Digitize selected map layers**




	
  6. Re-open ArcMap. The **Digitizing1.gdb** geodatabase contains 3 additional feature classes, all of which currently contain no map features. Your job now is to fill them.  Add the following feature classes to ArcMap using the Add Data button:




Rooks_Logan_1905_buildings           (a point layer—Square 1, 8 point, red)

Rooks_Logan_1905_parcels               (a polygon layer—no fill colour, outline width 1.00, red)

Rooks_Logan_1905_rail                     (a line layer—Railroad, width 1.00, red)



Because all three layers are empty, the map window remains blank.  Set the symbolization for each layer as indicated above.  When working with a black-and-white image red features make an easy-to-see contrast.



Then add the **Plat_LoganTwp_1905.tif** image from the **GeorectifiedScans** folder.  Right click on it in the Table of Contents and select Zoom to Layer.  Make the Editor toolbar active by going to the Customize menu and selecting Toolbars and Editor.





	
  7. Digitize the buildings in Sections 25-36 into a point layer. In the Table of Contents select **Rooks_Logan_1905_buildings** then click on the Editor dropdown in the Editor toolbar and select Start Editing.




Key concept:  The Start Editing command is both powerful and dangerous.  Normally map layers are locked, so you cannot accidentally change the shape or location of map features.  When you click Start Editing, however, you gain the power to create, edit, and delete map features.  Use this tool sparingly, only when needed, and be sure to engage the Stop Editing function as soon as you are finished with necessary edits.  If you accidentally change map features there is only one chance to fix them:  choose NOT to Save Edits when prompted and the layer will revert to its original state.  Once you Save Edits, there is no undo command that can help you.



Zoom in on section 25 on the map.



Note:  Sections are 1 mile square, and comprise 640 acres; the section number appears at the centre of each section.  Section 25, for example, is comprised of 2 quarter sections (160 acres each) on the south owned by Goodman and Smee, and 2 parcels on the north, an 80 acre piece owned by Novotny and a 240 acre piece owned by Baumgartner.[![12](http://geospatialhistorian.files.wordpress.com/2014/10/12.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/12.png)



Digitize the 3 buildings in Section 25, which appear as small solid black rectangles.  Click on the Editor dropdown, select Editing Windows and then Create Features.  In the new window that opens select **Rooks_Logan_1905_buildings**.  Below, click on the Point tool.  Move over the map and position the cursor exactly over the building symbol and click once.  Move to the next, click, and then to the third, clicking once over each building symbol.  Use the Pan tool to move the map over to Section 26, click back on the Point tool, and digitize the 3 buildings in Section 26.  Proceed to digitize all of the buildings in Sections 25-36.  Pan, Zoom, and re-engage the Point tool as needed until you have digitized all of the buildings.[![13](http://geospatialhistorian.files.wordpress.com/2014/10/13.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/13.png)



If you place a marker and are dissatisfied with its location, go to the Edit tool, a black arrow next to the Editor dropdown.  Use that tool to select the errant point.  Once selected, you can click and drag it to another location or use the Delete button on your keyboard to delete it altogether.  Once you have all of the points where you want them, go to the Editor dropdown and select Save Edits.





	
  8. Digitize the Union Pacific railroad line that crosses Sections 31-36 into a line layer. Zoom in on Sections 35 and 36. In the Table of Contents select **Rooks_Logan_1905_rail** then click on the Editor dropdown in the Editor toolbar and select Start Editing.  In the Create Features window click on **Rooks_Logan_rail**, then select the Line tool at the bottom.




Click on the right-most end of the railway line, then proceed to click along it at intervals.  When you get to the edge of your screen, click on the Pan tool and move the map to the right.  When you click on the Line tool again, you can resume your new line uninterrupted.  Continue clicking and panning until you reach the left-most end of the railway line.  On the last node, double-click to complete the line.



Key concept:  A line is constructed in the GIS as a beginning point, some number of intermediate “vertices” (or “nodes”), and an end point.  How many vertices should there be?  In digitizing there is a trade-off between accuracy and time cost.  That is, the more vertices you add, the more accurate the shape of the line will be and the longer it will take to create.  The necessary accuracy depends on the scale at which the map will be used.  In general, make as few vertices as necessary to create the precision needed for the scale of use.



Key concept:  When digitizing lines, direction matters (sometimes).  If there is a logical direction to a line, start at the beginning and end at the end.  The railway goes in both directions, so it doesn’t matter in this case.  If, however, we were digitizing the streams shown on the map, the lines should move in the direction of water flow.



Once the line is complete to your satisfaction, go to the Editor dropdown and select Save Edits, then Stop Editing.



	
  9. Digitize the land ownership parcels in Sections 23, 24, 25, 26, 35, and 36 into a polygon layer. Zoom in on Section 36. In the Table of Contents select **Rooks_Logan_1905_parcels** then click on the Editor dropdown in the Editor toolbar and select Start Editing.  In the Create Features window click on **Rooks_Logan_parcels**, then select the Polygon tool at the bottom.




On the Mayhew parcel, click on the bottom right corner.  Then click on the top right corner, and the top left corner.  On the bottom left corner, double-click to complete the polygon.



Go to the Editor dropdown and select Snapping then Snapping Toolbar.  Make sure all 4 symbols on the Snapping Toolbar are highlighted.  The snapping function pulls your cursor to an existing vertex or edge when you are close to it.



Now digitize the adjacent Smee parcel, snapping to the edge of the Mayhew parcel as appropriate.  Continue adding parcel polygons in the six specified sections, using the Zoom, Pan, and Polygon tools as needed.  **Every 5 minutes or so go to the Editor dropdown and select Save Edits.**  Note that property lines within sections are adjacent, while those between sections are not, due to road allowances.  When you are finished, go to the Editor dropdown and select Stop Editing.[![15](http://geospatialhistorian.files.wordpress.com/2014/10/15.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/15.png)



Now you have digitized a portion of the point, line, and polygon features on this map.  Use the check boxes in the Table of Contents to turn on all 3 of your new feature classes, and turn off the scanned map.  Features from the archival map are now represented abstractly and electronically in the GIS, and can be disaggregated, aggregated, and integrated with other data.[![16](http://geospatialhistorian.files.wordpress.com/2014/10/16.png?w=300)](https://geospatialhistorian.files.wordpress.com/2014/10/16.png)



Key concept:  Often we don’t need to extract _all_ of the map features contained on archival maps, only the new or unique information they contain.  For example, this map shows the township boundaries.  These boundaries have not changed since 1905 and are easily available in GIS format already.  There is no need for us to extract the township boundaries from this map.  On the other hand, the land ownership parcels are unique to these maps, are not widely known to scholars, and are not available in GIS format.  Because digitizing is labour-intensive, only extract map features that will help you answer important research questions and that are not already available elsewhere.




