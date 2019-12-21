---
author: joshmac
comments: false
date: 2018-10-04 18:52:25+00:00
layout: page
link: https://geospatialhistorian.wordpress.com/lesson-2-installing-qgis-and-adding-layers-qgis-3-0/
slug: lesson-2-installing-qgis-and-adding-layers-qgis-3-0
title: Lesson 2 Installing QGIS and Adding Layers (QGIS 3.0)
wordpress_id: 1351
---

**This lesson was peer reviewed and published by the [Programming Historian 2](http://programminghistorian.org/lessons/qgis-layers).**

In this lesson you will install QGIS software, download geospatial files like shapefiles and GeoTIFFs, and create a map out of a number of vector and raster layers. Quantum or QGIS is an open source alternative to the industry leader, ArcGIS from ESRI. QGIS is multiplatform, which means it runs on Windows, Macs, Linux, and Android, and it has many of the functions most commonly used by historians.

ArcGIS is expensive for individual users, and it only runs on Windows (though software can be purchased to allow it to run on Mac). However, many universities have site licenses, meaning students and employees have access to free copies of the software (try contacting your map librarian, computer services, or the geography department). QGIS is ideal for those without access to a free copy of Arc and it is also a good option for learning basic GIS skills and deciding if you want to install a copy of ArcGIS on your machine. Moreover, any work you do in QGIS can be exported to ArcGIS at a later date if you decide to upgrade.

The authors tend to use both and are happy to run QGIS on Mac and Linux computers for basic tasks, but still return to ArcGIS for more advanced work. In many cases it is not lack of functions, but stability issues that bring us back to ArcGIS. For those who are learning Python with the Programming Historian, you will be glad to know that both QGIS and ArcGIS use Python as their main scripting language.

**Installing QGIS**

Navigate to the [QGIS Download page](http://qgis.org/en/site/forusers/download.html). The procedure is a little different depending on your operating system. Click on the appropriate Operating System. Follow the instructions below.

_Mac Instructions_



	
  * Follow the link to the Mac Installer Package. This brings you to the KyngChaos QGIS download page (see image below). Under "Latest Release" you will see a link to Download "QGIS macOS Installer Version 3.x". Download the dmg file and open it to see the disk image.


![QGIS-Mac-download](https://geospatialhistorian.files.wordpress.com/2018/10/qgis-mac-download.png)



	
  * Open each package in the disk image in order, starting with "1 Install Python 3.rtf." This is because Mac users will still need to install two other free software packages _before_ installing QGIS. The first is Python 3 and the second is the dependency framework "GDAL Complete."  Follow the link to find the right version of Python 3 for your operating system. GDAL is included in the disk image. Install it like any other Mac program.


![QGIS-Mac-diskimage](https://geospatialhistorian.files.wordpress.com/2018/10/qgis-mac-diskimage.png)



	
  * once Python 3 and GDAL framework are installed, open "3 Install QGIS 3" and follow the instructions to install QGIS on your machine.

	
  * as with many other Mac applications you use for the first time, you may have to go find the QGIS application in "Applications."


_Windows Instructions_



	
  * For most people it will be best to choose Latest release (the Standalone Installer package "QGIS Standalone Installer Version 3.x"). Select 32 or 64 bit depending on your computer's hardware. In order to determine which version you have, click Start, Right-click My Computer, and then click Properties. If you see "x64 Edition" under System, your processor is 64-bit.


![QGIS-Windows-download](https://geospatialhistorian.files.wordpress.com/2018/10/qgis-windows-download.png)





	
  * double-click on the .exe file to execute


QGIS is very simple to install in most versions of Linux. Follow the instructions on the download page.

QGIS 3 is also available for Android devices. At the moment an experimental release can be found in the Play Store.

**Prince Edward Island Data**

We will be using some government data from the Canadian province of Prince Edward Island. PEI is a great example because there is a lot of data for free online and because it is Canada's smallest province, making the downloads quick!

Download PEI shapefiles:



	
  * Navigate to the links below in your web browser. Click on "Download File." You may have to read/accept the license agreement and supply your name and email. We created the final two shapefiles, so they should download directly:



	
  1. [http://www.gov.pe.ca/gis/license_agreement.php3?name=coastline&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=coastline&file_format=SHP)

	
  2. [http://www.gov.pe.ca/gis/license_agreement.php3?name=lot_town&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=lot_town&file_format=SHP)

	
  3. [http://www.gov.pe.ca/gis/license_agreement.php3?name=hydronetwork&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=hydronetwork&file_format=SHP)

	
  4. [http://www.gov.pe.ca/gis/license_agreement.php3?name=forest_35&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=forest_35&file_format=SHP)

	
  5. [http://www.gov.pe.ca/gis/license_agreement.php3?name=nat_parks&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=nat_parks&file_format=SHP)

	
  6. [PEI Highways](https://www.dropbox.com/s/7k08fewk1si6hp1/PEI_highway.zip?dl=0)

	
  7. [PEI Places](https://www.dropbox.com/s/9jn0onvt2otnlno/PEI_placenames.zip?dl=0)



	
  * After downloading all seven files, move them into a folder and unzip the zipped files. Take a look at the contents of the folders. You will notice four files with the same name, but different file types. When you navigate to these folders from GIS software, you will find that you only need to click on the .shp and that the other three formats support this file in the background. It is important when moving files on your computer to always move and keep all four files together. This is one reason Shapefiles are normally shared using zip compression. Remember the folder in which you save uncompressed shapefile folders, as you will need to find them from within QGIS in a few minutes.


**Starting Your GIS Project**

Open QGIS.

Investigate the components on the screen, including the tool bars, and the views or windows. On the left you should see a "Layers" panel and a "Browser" panel. These can be resized and moved. In the canvas on the right you should see the Map View. You can open and resize multiple views for the same project (click View and "New Map View"), but the default is a single Map View.



	
  * Note: there has been a common bug in QGIS 3 that affects the default Map View on some Macs. The Map View appears smaller than the viewing pane and it is impossible to move or resize it.

	
  * The best way to fix the bug is to open a second Map View (click View and "New Map View") and reposition this view around the top of the original Map View until it docks in place. Then resize it and close it, and the original Map View should correct itself and fill the entire canvas in that viewing pane.


The first thing we need to do is set up the [Coordinate Reference System](http://en.wikipedia.org/wiki/Spatial_reference_system) (CRS) correctly. The CRS is the map projection and projections are the various ways to represent real world places on two-dimensional maps. The default is WGS84 (it is increasingly common to use WGS 84), but since most of our data and examples are created by Canadian governments we recommend using NAD 83 (North American Datum, 1983).  For more on NAD 83 and the Federal Government's datum, see [NRCan's website](http://www.nrcan.gc.ca/earth-sciences/geography-boundary/mapping/topographic-mapping/10272).  PEI has its own NAD 83 coordinate reference system which uses a [Double Stereographic projection](http://www.gov.pe.ca/gis/index.php3?number=77865&lang=E). Managing the CRS of different layers of information and making sure they are working correctly is one of the most complicated aspects of GIS for beginners. Nonetheless, if the software is setup correctly, it should convert the CRS and allow you to work with data imported from different sources.

_Select Properties _



	
  * Mac: Project--> Properties


![QGIS3-properties](https://geospatialhistorian.files.wordpress.com/2018/10/qgis3-properties.png)



	
  * Windows: Settings--> Project Properties


[![change_CRS_windows](http://geospatialhistorian.files.wordpress.com/2013/02/change_crs_windows.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/change_crs_windows.png)



	
  * In the left window pane select CRS (third from the top)

	
  * click Enable ‘on the fly’ CRS transformation button on top left



	
  * in the Filter box enter “2291” - this quickly navigates to the best Coordinate reference system for Prince Edward Island.

	
  * under the box titled Coordinate reference systems of the world, select “NAD83(CSRS98) / Prince Edward Isl. (Stereographic)” and hit OK


![QGIS3-CRS](https://geospatialhistorian.files.wordpress.com/2018/10/qgis3-crs.png)



	
  * notice the projection has changed in the bottom right corner of the QGIS window.  Next to that you will see the geographic location of your mouse pointer in metres

	
  * under Project menu, select Save Project (you should save your project after each step)




You are now set up to work on the tutorial project, but might have a few questions about what CRS to use for your own project. WGS83 might work in the short term, particularly if you are working on a fairly large scale, but it will be difficult to accurately work on local maps. One hint is to learn what CRS or Projections is used for paper maps of the region. If you are scanning a good quality paper map to use as the base layer  it might be a good idea to use the same projection. You can also try searching the internet for the more common CRS for a particular region. For those of you working on North American projects identifying the correct NAD83 for your region will often be the best CRS. Here are a few links to other resources that will help you choose a CRS for your own project: [Tutorial: Working with Projections in QGIS](http://qgis.spatialthoughts.com/2012/04/tutorial-working-with-projections-in.html)


**Building a Base Map**

Now that your computer is driving with the right directions, it's time to add some information that makes sense to humans.  Your project should start with a base map, or a selection of geospatial information that lets your readers recognize real world features on the map.  For most users this will be comprised of several "layers" of vector and raster data, which can be rearranged, coloured, and labeled in such a way that they make sense to your readers and your project's objectives.

A relatively new feature on many GIS programs is the availability of pre-fab base maps, but since this technology is under development for open source platforms like QGIS we will walk through the process of creating our own base map by adding vector and raster layers in this module.

For those who would like to add pre-fab base maps to QGIS 3, at this point the only option is to add OpenStreetMaps using the XYZ Tiles service in the Browser Pane.



	
  * Click the down arrow next to XYZ Tiles and right click OpenStreetMap and click "Add Selected Layer to Canvas."
![OpenStreetMap](https://geospatialhistorian.files.wordpress.com/2018/10/openstreetmap.png)

	
  * Note: On older versions of GIS you can also install Google Maps and Google Satellite views. You do this by installing the "OpenLayers" Plugin under Plugins->Manage and Install Plugins. Select "Get More" on the left. Click OpenLayers and then click Install plugin. Click OK and then click close.  Once installed, you'll find OpenLayers in the Plugins Menu. Try installing some of the different Google and OpenStreetMaps layers.


Navigate around the new map. QGIS uses navigation tools that will be familiar to people who have used other GIS programs or even other webmaps.

	
  * Use the Zoom in and Zoom out tools to navigate around the new view of OpenStreetMaps in the Map View canvas.
![QGIS-nav-tools](https://geospatialhistorian.files.wordpress.com/2018/10/qgis-nav-tools.png)


Check the Coordinate Reference System. After adding the OpenStreetMap layer the Coordinate Reference System will usually change to the default for that layer. Change it back to the one we will use for PEI (EPSG:2291) following the steps above.

Use the navigation tools to zoom into an area around the Canadian Maritime Provinces. On a Mac the project should look something like this.

![QGIS-withOSM-in-canvas](https://geospatialhistorian.files.wordpress.com/2018/10/qgis-withosm-in-canvas.png)

**Opening Vectors**

Vectors [defined](http://www.gislounge.com/geodatabases-explored-vector-and-raster-data/): GIS uses points, lines, and polygons, also known as **vector** data. Its first order of work is to arrange these points, lines, and polygons and project them accurately on maps. Points may be towns or telephone poles; lines could represent rivers, roads, or railroads; and polygons could encompass a farmer’s lot or larger political boundaries. However, it is also possible to attach historical data to these geographical places and study how people interacted with and changed their physical environments. The population of towns changed, rivers moved their courses, lots were subdivided, and land was planted with various crops.



	
  * under Layer on the menu, choose Add Layer --> Add Vector Layer (alternatively the same icon you see next to “Add Vector Layer” can also be selected from the tool bar on the upper left side if it appeared there by default)

	
  * If convenient tools like this one are not on the tool bar by default add them by right-clicking on an empty space on the toolbar.


![Add-layer-Vector](https://geospatialhistorian.files.wordpress.com/2018/10/add-layer-vector.png)



	
  * click the three dots under "Source", find your downloaded Prince Edward Island shapefiles in the folder

	
  * open the coastline_polygon folder

	
  * select coastline_polygon.shp, then select "Add", and you should see the island's coastline on your screen. Sometimes QGIS adds a coloured background (see the image below). If you have a coloured background, follow the steps below. If not, skip down the page to the ***.
![Added-coastline](https://geospatialhistorian.files.wordpress.com/2018/10/added-coastline.png)

	
  * right click the layer (coastline_polygon) in the Layers menu and choose Properties.[![Properties](http://geospatialhistorian.files.wordpress.com/2013/09/properties.png?w=278)](http://geospatialhistorian.files.wordpress.com/2013/09/properties.png)

	
  * In the ensuing window, click Symbology in the left pane



	
  * There are a range of options, but we want to get rid of the background all together. Click **Simple fill**.


[![layerproperties_coastline](http://geospatialhistorian.files.wordpress.com/2013/09/layerproperties_coastline.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/layerproperties_coastline.png)



	
  * Then choose "**No Brush**" in the **Fill style** drop down menu. **Click OK.**


[![layerproperties_nobrush_2_0](http://geospatialhistorian.files.wordpress.com/2013/09/layerproperties_nobrush_2_0.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/layerproperties_nobrush_2_0.png)

***



	
  * Choose Add Vector Layer again.

	
  * click Browse, find your downloaded Prince Edward Island shapefiles in the folder

	
  * select "PEI_HYDRONETWORK"

	
  * click on "PEI_HYDRONETWORK.shp" and then hit "Open"

	
  * right click the layer in the Layers menu and choose Properties.

	
  * select Style tab, and choose an appropriate blue to color the hydronetwork and select "OK" at the bottom right of the window


[![blue](http://geospatialhistorian.files.wordpress.com/2013/09/blue.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/blue.png)



	
  * Your map should now look like this:


[![plusHydro2_0](http://geospatialhistorian.files.wordpress.com/2013/09/plushydro2_0.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/plushydro2_0.png)



	
  * Choose Add Vector Layer again.

	
  * click Browse, find your downloaded Prince Edward Island shapefiles in the folder

	
  * double-click on “1935 inventory_region.shp”  and then hit "Open"


This will add a dense map showing the different forest cover in 1935. However, to see the different categories, you will need to change the symbology to represent the different categories of forest with different colours. We will need to know which column of the database tables includes the forest category information, so the first step is to open and inspect the attribute table.

	
  * right click on the 1935_inventory_region layer in the Layers window on the left and click on Open Attribute Table


[![open attribute table](http://geospatialhistorian.files.wordpress.com/2013/09/open-attribute-table.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/open-attribute-table.png)

An Attribute Table will open. It has a number of categories and identifiers. Of particular interest is the LANDUSE category which provides information on the forest cover in 1935. We will now show you how to display these categories on the map.

[![attribute table](http://geospatialhistorian.files.wordpress.com/2013/09/attribute-table.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/attribute-table.png)



	
  * Close the Attribute Table, and right click on the 1935_inventory_region layer again and this time choose Properties (alternatively, the shortcut is to double click on the 1935_inventory_region layer).

	
  * click Symbology along the left


[![categorized](http://geospatialhistorian.files.wordpress.com/2013/09/categorized1.png)](http://geospatialhistorian.files.wordpress.com/2013/09/categorized1.png)



	
  * on the menu bar that reads "Single Symbol"  select “Categorized”


[![landuse](http://geospatialhistorian.files.wordpress.com/2013/09/landuse.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/landuse.png)



	
  * beside Column choose "Landuse"

	
  * under Color ramp choose Greens

	
  * click "Classify below and to the left

	
  * in Symbol Column, choose the furthest down dark green square (with no value beside it) and hit the “minus sign” button (to the right of Classify); also delete the Developed category, as we want to highlight forested areas. Click "OK"


[![categorized](http://geospatialhistorian.files.wordpress.com/2013/09/categorized.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/categorized.png)



	
  * in Layers sidebar menu, click on the little arrow beside 1935_inventory_region to view the legend.



	
  * You can now see the extent of the forests in 1935. Try using the magnifying glass tool to zoom in and inspect the different landuses.


[![zoomforest](http://geospatialhistorian.files.wordpress.com/2013/09/zoomforest.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/zoomforest.png)



	
  * To get back to the full island, right click on any of the layers and choose "**Zoom to Layer.**"


[![zoomtolayer](http://geospatialhistorian.files.wordpress.com/2013/09/zoomtolayer.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/zoomtolayer.png)



	
  * Next, we will add a layer of roads.

	
  * under Layer on toolbar, choose Add Vector Layer

	
  * click Browse, find your downloaded Prince Edward Island shapefiles in the folder

	
  * select “PEI_highway.shp”

	
  * in the Layers menu on the left, double-click "PEI_highway" and select Style from the menu on the left (if it isn't already selected)

	
  * click on “Single Symbol” on top left and select “Categorized”

	
  * beside Column choose “TYPE”

	
  * click Classify


[![primaryroad](http://geospatialhistorian.files.wordpress.com/2013/09/primaryroad.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/primaryroad.png)



	
  * in the Symbol column, double-click beside “primary” - in the ensuing window, there is a box with different symbols. Scroll down and find "primary road".



	
  * You are back in the Style window. Repeat for the item that called "primary_link" in the Label column.


![simpleroadline](http://geospatialhistorian.files.wordpress.com/2013/09/simpleroadline.png?w=300)



	
  * click Symbol beside secondary and change color to black and width to 0.7

	
  * repeat for secondary link

	
  * click OK. You will now have the highways and other major roads represented on the map


[![roadnetwork](http://geospatialhistorian.files.wordpress.com/2013/09/roadnetwork.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/roadnetwork.png)



	
  * under Layer on toolbar, choose Add Vector Layer

	
  * click Browse, find your downloaded Prince Edward Island shapefiles in the folder

	
  * select “PEI_placenames_shp”

	
  * double click on PEI_placenames and select "Open"

	
  * in the Layers window, double-click on the PEI_placenames layer. Choose Labels tab along the left (under Style). At the top, select the box beside "Label this layer with" and in the dropdown box beside that select "Placename"


[![labels](http://geospatialhistorian.files.wordpress.com/2013/09/labels.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/labels.png)



	
  * Change Font size to "18"

	
  * Click "OK" and examine the results on the map


[![labels2_0](http://geospatialhistorian.files.wordpress.com/2013/09/labels2_0.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/labels2_0.png)



	
  * Labelling is where QGIS falls well short of real cartography - it will take tinkering to adjust settings to display the detail desired for a presentation. Try going back to the Labels tab and changing the different settings to see how symbols and displays change.


Note that in the Layers menu you can add and remove the various layers we've added to the map much the same way you did in Google Earth. Click on the check boxes to remove and add the various layers. Drag and drop layers to change the the order they appear. Dragging a layer to the top will place it above the rest of the layers and make it the most prominent. For example, if you drag "coastline_polygon" to the top, you have a simplified outline of the province along with place names.

[![labelsclean2_0](http://geospatialhistorian.files.wordpress.com/2013/09/labelsclean2_0.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/labelsclean2_0.png)



	
  * Along the toolbar on the top left of the main window are icons that allow you to explore the map. The hand symbol, for example, allows you to click on the map and move it around, while the magnifying glass symbols with plus and minus on them allow you to zoom in and out. Play with these and familiarize yourself with the various functions


[![Screen Shot 2013-09-23 at 10.03.30 PM](http://geospatialhistorian.files.wordpress.com/2013/09/screen-shot-2013-09-23-at-10-03-30-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/09/screen-shot-2013-09-23-at-10-03-30-pm.png)



	
  * having created a map using vector layers, we will now add or use our first raster layer. This is a  good time to save your work.


**Opening Rasters**

**R****aster** data are digital images made up of grids. All remote sensing data such as satellite images or [aerial photos](http://en.wikipedia.org/wiki/Orthophoto) are rasters, but usually you can't see the grids in these images because they are made up of tiny pixels.  Each pixel has its own value and when those values are symbolized in colour or greyscale they make up an image that is useful for display or topographical analysis.  A scanned historical map is also brought into GIS in raster format.



	
  * download: ["PEI_CumminsMap1927.tif"](https://www.dropbox.com/s/jrh5gaqr192sc1h/PEI_CumminsMap1927_compLZW.tif?dl=0) to your project folder.

	
  * under Layer on toolbar, choose Add Raster Layer (alternatively the same icon you see next to “Add Raster Layer” can also be selected from the tool bar along the left side of the window)


[![Screen Shot 2013-09-23 at 9.44.20 PM](http://geospatialhistorian.files.wordpress.com/2013/09/screen-shot-2013-09-23-at-9-44-20-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/09/screen-shot-2013-09-23-at-9-44-20-pm.png)



	
  * find the file you have downloaded titled "PEI_CumminsMap1927.tif"

	
  * you will be prompted to define this layer's coordinate system. In the Filter box search for "2291", then in the box below select "NAD83(CSRS98) / Prince Edward Isl. (Stereographic)..."


[![Screen Shot 2013-09-23 at 9.45.30 PM](http://geospatialhistorian.files.wordpress.com/2013/09/screen-shot-2013-09-23-at-9-45-30-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/screen-shot-2013-09-23-at-9-45-30-pm.png)



	
  * If the program does not prompt you for the CRS you need to change it yourself. Double click the PEI_CummingMap1927_compLZW layer and choose "**General**" from the menu on the left. Click "**Specify...**" beside the box showing the incorrect Coordinate reference system. Then follow the instructions above (choose 2291).


[![changerastorcrs](http://geospatialhistorian.files.wordpress.com/2013/09/changerastorcrs.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/changerastorcrs.png)



	
  * In the Layers window, the map should appear below the vector data. Move it to the bottom of the menu if necessary:


[![Screen Shot 2013-09-23 at 9.46.49 PM](http://geospatialhistorian.files.wordpress.com/2013/09/screen-shot-2013-09-23-at-9-46-49-pm.png?w=243)](http://geospatialhistorian.files.wordpress.com/2013/09/screen-shot-2013-09-23-at-9-46-49-pm.png)



	
  * Now we would like to make the coastline more visible, so double-click on coastline_polygon and select Style on the left. In the box under Symbol layers, select "Simple fill" and options appear in the box to the right. Click on the menu next to "Border" and make it red, and then beside Border width change it to 0.5, and click OK.


[![redoutline](http://geospatialhistorian.files.wordpress.com/2013/09/redoutline.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/09/redoutline.png)



	
  * You are now able to see the background raster map through the coastline_polygon layer. Zoom in for closer inspection, and you should be able to see the coastline layer clearly.  Notice that the alignment is relatively good, but not perfect. We will learn more in lesson 4 about the challenges of georeferencing historical maps to give them real world coordinates.


[![endlesson2](http://geospatialhistorian.files.wordpress.com/2013/09/endlesson2.png?w=189)](http://geospatialhistorian.files.wordpress.com/2013/09/endlesson2.png)

**You have learned how to install QGIS and add layers. Make sure you save your work!**
