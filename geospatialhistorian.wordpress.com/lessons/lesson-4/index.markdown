---
author: cljim22
comments: true
date: 2013-02-04 16:24:32+00:00
layout: page
link: https://geospatialhistorian.wordpress.com/lessons/lesson-4/
slug: lesson-4
title: 'Lesson 4: Georeferencing'
wordpress_id: 170
---

**These lessons are currently in open review by the [Programming Historian 2](http://programminghistorian.org/).**

In this lesson, you will learn how to georeference historical maps so that they may be added to a GIS as a raster layer. Georeferencing is required for anyone who wants to accurately digitize data found on a paper map, and since historians work mostly in the realm of paper, georeferencing is one of our most commonly used tools.  The technique uses a series of control points to give a two-dimensional object like a paper map the real world coordinates it needs to align with the three-dimensional features of the earth in GIS software (in [Lesson 1](http://geospatialhistorian.wordpress.com/lessons/lesson-1/) we saw an "overlay" which is  a Google Earth shortcut version of georeferencing).

Georeferencing a historical map requires a knowledge of both the geography and the history of the place you are studying to ensure accuracy.  The built and natural landscapes change over time, and it is important to confirm that the location of your control points -- whether they be houses, intersections, or even towns -- have remained constant.  Entering control points in a GIS is easy, but behind the scenes, georeferencing uses complex transformation and compression processes.  These are used to correct the distortions and inaccuracies found in many historical maps and stretch the maps so that they fit geographic coordinates.  In cartography this is known as [rubber-sheeting](http://en.wikipedia.org/wiki/Rubbersheeting) because it treats the map as if it were made of rubber and the control points as if they were tacks "pinning" the historical document to a three dimensional surface like the globe.

To offer some examples of georeferenced historical maps, we prepared some National Topographic Series maps hosted on the University of Toronto Map Library website courtesy of Marcel Fortin, and we overlaid them on a Google web map. Viewers can adjust the transparency with the slider bar on the top right, view the historical map as an overlay on terrain or satellite images, or click "Earth" to switch into Google Earth mode and see 3D elevation and modern buildings (in Halifax and Dartmouth). Note: these historical images are large and will appear on the screen slowly, especially as you zoom into the Google map.



	
  * [National Topographic System Maps](http://maps.library.utoronto.ca/datapub/digital/3400s_63_1929/maptile/Halifax/googlemaps.html) - Halifax, 1920s

	
  * [National Topographic System Maps](http://maps.library.utoronto.ca/datapub/PEI/NTS/west/) - Western PEI, 1939-1944

	
  * [National Topographic System Maps](http://maps.library.utoronto.ca/datapub/PEI/NTS/east/) - Eastern PEI 1939-1944


**Getting started:**

Before proceeding with georeferencing in Quantum GIS, we need to turn on the appropriate Plugins. On the toolbar go to Plugins -> Manage Plugins

[![manage_plugins](http://geospatialhistorian.files.wordpress.com/2013/02/manage_plugins.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/manage_plugins.png)

A window titled QGIS Plugin Manager will open. Scroll down to Georeference GDAL and check the box beside it, and click OK.

[![GeoreferencerGDAL_plugin](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencergdal_plugin.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencergdal_plugin.png)



	
  * At this point, you need to shut down and relaunch QGIS. For the purposes of this example, and to keep things as simple as possible, don't reload your existing project but instead start a new project.

	
  * Set up the [Coordinate Reference System](http://en.wikipedia.org/wiki/Spatial_reference_system) (CRS) correctly (see [Lesson 2](http://geospatialhistorian.wordpress.com/lessons/lesson-2-installing-qgis-and-adding-layers/) for a reminder)

	
  * Save this new project (under File menu, select Save Project) and call it "georeferencing."

	
  * Add the coastline_polygon layer (see [Lesson 2](http://geospatialhistorian.wordpress.com/lessons/lesson-2-installing-qgis-and-adding-layers/) for a reminder)


**Open the necessary GIS layers:**

For the Prince Edward Island case study, we are going to use the township boundaries as control points because they were established in 1764 by Samuel Holland, they are identified on most maps of PEI, and they have changed very minimally since then.

_Download lot_township_polygon:_

This is the shapefile containing the modern vector layer we are going to use to georeference the historical map.  Note that townships were not given names but rather a lot number in 1764, so they are usually referred to as "Lots" in PEI.  Hence the file name "lot_township_polygon."



	
  * Navigate to the link below in your web browser, read/accept the license agreement, and then download the following (they will ask for your name and email before you can download the file).
[http://www.gov.pe.ca/gis/license_agreement.php3?name=lot_town&file_format=SHP
](http://www.gov.pe.ca/gis/license_agreement.php3?name=lot_town&file_format=SHP)

	
  * After downloading the file called lot_township_polygon, move it into a folder that you can find later and unzip the file. (Remember to keep the files together as they are all required to open this layer in your GIS)


![DownloadingGIS-shapefile](http://geospatialhistorian.files.wordpress.com/2013/02/downloadinggis-shapefile.png?w=300)

_Add lot_township_polygon to QGIS: _



	
  * under Layer on the toolbar, choose Add Vector Layer (alternatively the same icon you see next to “Add Vector Layer” can also be selected from the tool bar)

	
  * Click Browse. Navigate to your unzipped file and select the file titled lot_township_polygon.shp

	
  * Click Open


[![vector_button](http://geospatialhistorian.files.wordpress.com/2013/02/vector_button.png?w=64&h=71)](http://geospatialhistorian.files.wordpress.com/2013/02/vector_button.png)

For more information on adding and visualizing layers see [Lesson 2](http://geospatialhistorian.wordpress.com/lessons/lesson-2-installing-qgis-and-adding-layers/).

[![Georeferencing_gettingstarted](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencing_gettingstarted.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencing_gettingstarted.png)

**Open the Georeferencer tool:**

Georeferencer is now available under the Raster menu on the toolbar - select it.

[![raster-georef](http://geospatialhistorian.files.wordpress.com/2013/02/raster-georef.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/raster-georef.png)

_Add your historical map:_



	
  * In the resulting window, click on the Open Raster button on the top left (which looks identical to the Add Raster layer).


![raster](http://geospatialhistorian.files.wordpress.com/2013/02/raster.png)



	
  * Find the file titled "PEI_LakeMap1863.jpg" on your computer and select Open (the file [can be downloaded here](http://geospatialhistorian.wordpress.com/?attachment_id=121) or in its original location at the [Island Imagined](http://www.islandimagined.ca/fedora/repository/imagined%3A208687) online map repository)

	
  * You will be prompted to define this layer's coordinate system. In the Filter box search for "2291", then in the box below select "NAD83(CSRS98) / Prince Edward ..."


The result will look like this:

[![Screen Shot 2013-02-01 at 3.57.50 PM](http://geospatialhistorian.files.wordpress.com/2013/02/screen-shot-2013-02-01-at-3-57-50-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/screen-shot-2013-02-01-at-3-57-50-pm.png)

_Adding control points:_

Plan the locations you are going to use as control points in advance of the steps that follow.  It is much easier to navigate around the historical map first, so get a good idea of the best points to use and keep them in mind.

Some tips for choosing control points:



	
  * **How many** points do you need? Usually the more points you assign the more accurate your georeferenced map will be.  Two control points will tell the GIS to scale and rotate the map to those two points, but in order to truly rubber-sheet the historical document you need to add more points.

	
  * **Where** should you put control points? Select areas as close as possible to the four corners of your map so that these outer areas do not get omitted in the rubber-sheeting.  

	
  * Select additional control points close to your area of interest.  Everything in between the four corner control points should georeference evenly, but if you are concerned about the accuracy of one place in particular, make sure to select additional control points in that area.  

	
  * Select the middle of intersections and roads, because the edges of roads changed a certain amount over time as road improvements were made.

	
  * Check that your control points did not change location over time.  Roads were often re-routed, and even houses and other buildings were moved, especially [in Atlantic Canada](http://books.google.ca/books?id=TqCNZYXWXAUC&dq=tilting&source=gbs_navlinks_s)! 


_Add your first control point:_

**First**, navigate to the location of your first control point on the **historical map**.



	
  * click on Zoom In Magnifying Glass on the window tool bar or use the mouse roller wheel to zoom in


[![georeference_zoom_in](http://geospatialhistorian.files.wordpress.com/2013/02/georeference_zoom_in.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/georeference_zoom_in.png)



	
  * zoom in to a point which you can recognize on both your printed map and your GIS



	
  * Click on Add Point on toolbar


[![georeferencer_add_point](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencer_add_point.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencer_add_point.png)



	
  * Click on the place in the printed map that you can locate in your GIS (i.e. the control point). The Georeferencer window will now minimize automatically. If it does not (some versions have a bug in this plugin) manually minimize the window

	
  * Click on the place in the GIS which matches the control point![georeferencer_enter_map_coordinates](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencer_enter_map_coordinates.png?w=300)

	
  * At this stage we identified a problem in lot boundaries. We planned to use the location where the southern border of Lot 1 at the West end of the Province contains a "dog leg" near the middle of the land mass.  However, it was clear that not all the dog legs on these lots matched the historical map.  It is possible that lot boundaries have changed somewhat in the 250 years since they were established, so it is best to choose the point you are most sure of.  In this case the dog leg between Lot 2 and Lot 3 was fine (see arrow).  It was the border of Lots 3 and 4 that has changed. The discrepancy at the border of 1 and 2 shows that more control points are needed to properly rubber-sheet this somewhat distorted 1863 map to the Provincial GIS layer

	
  * [![LotBoundaryConflicts](http://geospatialhistorian.files.wordpress.com/2013/02/lotboundaryconflicts1.png?w=281)](http://geospatialhistorian.files.wordpress.com/2013/02/lotboundaryconflicts1.png)


_Add at least one more control point:_



	
  * return to the Georeferencer window and repeat the steps under "_Add your first control point_" above, to add additional control points.

	
  * Add a point close to the opposite side of your printed map (the further apart your control points are placed the more accurate the georeferencing process) and another one near Charlottetown

	
  * return to the Georeferencer window. You should see three red dots on the printed map, and three records in the GCP table at the bottom of your window (outlined in red on the following image)


[![georeferencer_with_controlpoints](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencer_with_controlpoints2.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencer_with_controlpoints2.png)

_Determine the transformation settings:_

Before you click Play and start the automated georeferencing process you need to tell QGIS where to save the new file (this will be a raster file), how it should interpret your control points, and how it should compress the image.



	
  * Click on the Transformation Settings button


[![TransformationSettings](http://geospatialhistorian.files.wordpress.com/2013/02/transformationsettings.png)](http://geospatialhistorian.files.wordpress.com/2013/02/transformationsettings.png)

Most of these settings can be left as default: linear transformation type, nearest neighbour resampling method, and LZW compression.  (The [world file](http://en.wikipedia.org/wiki/World_file) is not necessary, unless you want to georeference the same image again in another GIS or if someone else needs to georeference the image and does not have access to your GIS data, coordinate reference system, etc.)  The target SRS is not important, but you could use this feature to give the new raster a different reference system.



	
  * Assign a folder for your new georeferenced raster file.  [Tif](http://en.wikipedia.org/wiki/Tagged_Image_File_Format) is the default format for rasters georeferenced in QGIS.  

	
  * Be aware that a Tif file is going to be much larger than your original map, even with LZW compression, so make sure you have adequate space if you are using a jump drive.
(warning: the Tif file produced from this 6.8 Mb .jpg will be **over 1GB** once georeferenced. One way to manage the size of the georeferenced raster file while maintaining a high enough resolution for legibility is to crop out only the area needed for the map project.  In this case, a lower resolution option is also available from the [Island Imagined](http://www.islandimagined.ca/fedora/repository/imagined%3A208687) online map repository.) 

	
  * Leave the target resolution at the default

	
  * You can select "Use 0 transparency when needed"  to eliminate black spaces around the edges of the map, but this is not necessary and you can experiment as needed

	
  * Make sure "Load in QGIS" is selected to save a step. This will automatically add the new file to your GIS's Table of Contents so that you don't have to go looking for the Tif file later


![georeferencer_transformation_settings](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencer_transformation_settings.png?w=264)

_Georeference!_



	
  * Click on the Play button on the toolbar (beside Add Raster) - this begins the georeferencing process

	
  * A window will appear titled Define CRS: select 2291, click OK


[![georeferencer_result](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencer_result.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencer_result.png)

_Explore your map:_



	
  * Drag the new layer "PEI_LakeMap1863_modified" down to the bottom of your Table of Contents (i.e. below the "lot_township_polygon" layer


![GeoreferencingResult2](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencingresult2.png?w=300)



	
  * Change the fill of the lot_township_polygon layer to "no brush" by Selecting the layer, clicking on Layer -> Properties, and clicking on Symbol Properties. Click OK


[![ChangeBrushType](http://geospatialhistorian.files.wordpress.com/2013/02/changebrushtype.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/changebrushtype.png)



	
  * Now you should see the modern GIS layer with the historical map in behind[![GeoreferencedMap_behindLotPoly](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencedmap_behindlotpoly.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/georeferencedmap_behindlotpoly.png)


Now that you have a newly georeferenced map in your GIS you can explore the layer, adjust the transparency, contrast and brightness, and go back through [Lesson 3](http://geospatialhistorian.wordpress.com/lessons/lesson-3/) to digitize some of the historical information that you have created.  For instance, this georeferenced map of PEI shows the locations of all homes in 1863, including the name of the head of household.  By assigning points on the map you can enter home locations and owner names and then analyze or share that new geospatial layer as a shapefile.

By digitizing line vectors such as roads or coastlines you can compare the location of these features with other historical data, or simply compare them visually with the lot_township_polygon layer in this GIS.

In more advanced processes you can even drape this georeferenced image over a DEM (digital elevation model) to give it a hillshade terrain or 3D effect and perform a "fly-over" of PEI homes in the nineteenth century.
