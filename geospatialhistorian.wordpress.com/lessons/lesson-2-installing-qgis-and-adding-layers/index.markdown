---
author: cljim22
comments: true
date: 2013-02-04 16:22:28+00:00
layout: page
link: https://geospatialhistorian.wordpress.com/lessons/lesson-2-installing-qgis-and-adding-layers/
slug: lesson-2-installing-qgis-and-adding-layers
title: 'Lesson 2: Installing QGIS and Adding Layers'
wordpress_id: 165
---

**These lessons are currently in open review by the [Programming Historian 2](http://programminghistorian.org/).**

In this lesson you will install QGIS software, download geospatial files like shapefiles and GeoTIFFs, and create a map out of a number of vector and raster layers. Quantum or QGIS is an open source alternative to the industry leader, ArcGIS from ESRI. QGIS is multiplatform, which means it runs on Windows, Macs, and Linux and it has many of the functions most commonly used by historians.

ArcGIS is prohibitively expensive and only runs on Windows (though software can be purchased to allow it to run on Mac). However, many universities have site licenses, meaning students and employees have access to free copies of the software (try contacting your map librarian, computer services, or the geography department). QGIS is ideal for those without access to a free copy of Arc and it is also a good option for learning basic GIS skills and deciding if you want to install a copy of ArcGIS on your machine. Moreover, any work you do in QGIS can be exported to ArcGIS at a later date if you decide to upgrade.

The authors tend to use both and are happy to run QGIS on Mac and Linux computers for basic tasks, but still return to ArcGIS for more advanced work. In many cases it is not lack of functions, but stability issues that bring us back to ArcGIS. For those who are learning Python with the Programming Historian, you will be glad to know that both QGIS and ArcGIS use Python as their main scripting language.

**Installing QGIS**

Navigate to the [QGIS Download page](http://hub.qgis.org/projects/quantum-gis/wiki/Download). The procedure is a little different depending on your operating system. Click on the appropriate Operating System. Follow the instructions below.

_Mac Instructions_



	
  * For most people it will be best to choose Master release (the one that has a single installer package). You will still need to install other software packages before installing QGIS. Click on the link and download the following two files (install like any other Mac programs): GDAL complete and GSL framework.


[![qgismac2](http://geospatialhistorian.files.wordpress.com/2013/02/qgismac2.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/qgismac2.png)



	
  * once the frameworks are installed, download and install QGIS.

	
  * as with any other Mac application you are using for the first time, you will have to go find the QGIS application in Applications


_Windows Instructions_



	
  * under Standalone Installer, click on the link to Download QGIS


[![gis_ms_win](http://geospatialhistorian.files.wordpress.com/2013/02/gis_ms_win.jpg?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/gis_ms_win.jpg)



	
  * double-click on the .exe file to execute


QGIS is very simple to install in most versions of Linux. Follow the instructions on the download page.

**Prince Edward Island Data**

We will be using some government data from the Canadian province of Prince Edward Island. PEI is a great example because there is a lot of data for free online and because it is Canada's smallest province, making the downloads quick!

Download PEI shapefiles:



	
  * Navigate to the links below in your web browser, read/accept the license agreement, and then download the following (they will ask for your name and email with each download). We created the final two shapefiles, so they should download directly:



	
  1. [http://www.gov.pe.ca/gis/license_agreement.php3?name=coastline&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=coastline&file_format=SHP)

	
  2. [http://www.gov.pe.ca/gis/license_agreement.php3?name=lot_town&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=lot_town&file_format=SHP)

	
  3. [http://www.gov.pe.ca/gis/license_agreement.php3?name=hydronetwork&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=hydronetwork&file_format=SHP)

	
  4. [http://www.gov.pe.ca/gis/license_agreement.php3?name=forest_35&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=forest_35&file_format=SHP)

	
  5. [http://www.gov.pe.ca/gis/license_agreement.php3?name=nat_parks&file_format=SHP](http://www.gov.pe.ca/gis/license_agreement.php3?name=nat_parks&file_format=SHP)

	
  6. [PEI Highways](https://www.dropbox.com/s/mgrb90vcpggnw8c/PEI_highway.zip) ([alternate Tar file](https://www.dropbox.com/s/8k81jnmhpoi99fv/pei_highway.tar.gz))

	
  7. [PEI Places](https://www.dropbox.com/s/fev9116zfr31ogb/PEI_placenames.zip) ([alternate Tar file](https://www.dropbox.com/s/33g19iqhdnxoayd/pei_placenames.tar.gz))



	
  * After downloading all seven files, move them into a folder and unzip the zipped files. Take a look at the contents of the folders. You will notice four files with the same name, but different file types. When you navigate to these folders from GIS software, you will find that you only need to click on the .shp and that the other three formats support this file in the background. It is important, however, when moving files on your computer to always move all four files together. This is one reason Shapefiles are normally shared using zip compression. Remember which folder you save the uncompressed shapefile folders to, as you will need to find them from within QGIS in a few minutes.


**Starting Your GIS Project**

Open QGIS. The first thing we need to do is set up the [Coordinate Reference System](http://en.wikipedia.org/wiki/Spatial_reference_system) (CRS) correctly. The CRS is the map projection and projections are the various ways to represent real world places on two-dimensional maps.   The default is WGS84 (it is increasingly common to use WGS 84 which is compatible with Google Earth type software), but since most of our data and examples are created by Canadian governments we recommend using NAD 83 (North American Datum, 1983).  For more on NAD 83 and the Federal Government's datum, see [NRCan's website](http://www.nrcan.gc.ca/earth-sciences/geography-boundary/mapping/topographic-mapping/10272).  PEI has its own NAD 83 coordinate reference system which uses a [Double Stereographic projection](http://www.gov.pe.ca/gis/index.php3?number=77865&lang=E). Managing the CRS of different layers of information and making sure they are working correctly is one of the most complicated aspects of GIS for beginners. Nonetheless, if the software is setup correctly, it should convert the CRS and allow you to work with data imported from different sources.



	
  * _Select Project Properties_

	
  * Mac: -File->Project Properties


[![project_prop](http://geospatialhistorian.files.wordpress.com/2013/02/project_prop.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/project_prop.png)



	
  * Windows: Settings-> Project Properties


[![change_CRS_windows](http://geospatialhistorian.files.wordpress.com/2013/02/change_crs_windows.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/change_crs_windows.png)



	
  * select Coordinate Reference System at top

	
  * click Enable ‘on the fly’ CRS transformation button on top left



	
  * [![crn](http://geospatialhistorian.files.wordpress.com/2013/02/crn.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/crn.png)in the Filter box enter “2291.” This quickly navigates to the best Coordinate reference system for Prince Edward Island.

	
  * under the box titled Coordinate reference systems of the world, select “Prince Edward Isl. (Stereographic)” and hit OK

	
  * notice the projection has changed in the bottom right corner of the QGIS window.  Next to that you will see the geographic location of your mouse pointer in metres

	
  * under File menu, select Save Project (you should save your project after each step)


You are now set up to work on the tutorial project, but might have a few questions about what CRS to use for your own project. WGS84 might work in the short term, particularly if you are working on a fairly large scale, but it will be difficult to accurately work on local maps. One hint is to learn what CRS or Projections is used for paper maps of the region. If you are scanning a good quality paper map to use as the base layer  it might be a good idea to use the same projection. You can also try searching the internet for the more common CRS for a particular region. For those of you working on North American projects identifying the correct NAD83 for your region will often be the best CRS. Here are a few links to other resources that will help you choose a CRS for your own project: [Tutorial: Working with Projections in QGIS](http://qgis.spatialthoughts.com/2012/04/tutorial-working-with-projections-in.html)

**SHOULD WE ADD MORE RESOURCES HERE?**

**Building a Base Map**

Now that your computer is driving with the right directions, it's time to add some information that makes sense to humans.  Your project should start with a base map, or a selection of geospatial information that lets your readers recognize real world features on the map.  For most users this will be comprised of several "layers" of vector and raster data, which can be rearranged, coloured, and labeled in such a way that they make sense to your readers and your project's objectives.

A relatively new feature on many GIS programs is the availability of pre-fab base maps, but since this technology is under development for open source platforms like QGIS we will walk through the process of creating our own base map by adding vector and raster layers in this module.

Note: for those who would like to add pre-fab base maps to QGIS, you can try installing the "OpenLayers" Plugin under Plugins->Fetch Python Plugins (enter "OpenLayers" in the Filter box).  At the time of writing this module, the OpenLayers plugin (v. 1.1) installs but on some machines fails to work properly on any Mac using OSX.  It appears to work more consistently on QGIS running on Windows 7. Give it a try, as we expect it will only get better in the months ahead. Note, however, that the projection for some of these global maps do not correct on the fly, so the satellite images might not alway sync up with data projected in a different CRS.

**Opening Vectors**

Vectors [defined](http://www.gislounge.com/geodatabases-explored-vector-and-raster-data/): GIS uses points, lines, and polygons, also known as **vector** data. Its first order of work is to arrange these and project them accurately on maps. Points may be towns or telephone poles; lines could represent rivers, roads, or railroads; and polygons could encompass a farmer’s lot or larger political boundaries. However, it is also possible to attach historical data to these geographical places and study how people interacted with and changed their physical environments. The population of towns changed, rivers moved their courses, lots were subdivided, and land was planted with various crops.



	
  * under Layer on toolbar, choose Add Vector Layer (alternatively the same icon you see next to “Add Vector Layer” can also be selected from tool bar)


[![vector_button](http://geospatialhistorian.files.wordpress.com/2013/02/vector_button.png)](http://geospatialhistorian.files.wordpress.com/2013/02/vector_button.png)



	
  * click Browse, find your downloaded Prince Edward Island shapefiles in the folder

	
  * open the coastline_polygon folder


[![first_coastline_map](http://geospatialhistorian.files.wordpress.com/2013/02/first_coastline_map.jpg?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/first_coastline_map.jpg)



	
  * double-click coastline_polygon and you should see the island's coastline on your screen. Sometimes QGIS adds a coloured background (see the image above). If you have a coloured background, follow the steps below. If not, skip down the page to the ***.

	
  * right click the layer in the right hand menu and choose Properties.[![layer_properties](http://geospatialhistorian.files.wordpress.com/2013/02/layer_properties.png?w=234)](http://geospatialhistorian.files.wordpress.com/2013/02/layer_properties.png)

	
  * click Style along top (unless you are already in the Style menu), click “change” (Note, there are two "Change" icons. Look for the one with a wrench icon or look at the image below.)


[![style_change](http://geospatialhistorian.files.wordpress.com/2013/02/style_change.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/style_change.png)



	
  * for Fill style select “No Brush”


[![no_brush](http://geospatialhistorian.files.wordpress.com/2013/02/no_brush.jpg?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/no_brush.jpg)



	
  * click OK, click OK


***

	
  * Choose Add Vector Layer again.

	
  * click Browse, find your downloaded Prince Edward Island shapefiles in the folder

	
  * select "PEI_HYDRONETWORK"

	
  * double-click on "PEI_HYDRONETWORK.shp"

	
  * right click the layer in the right hand menu and choose Properties.

	
  * select Style tab, and choose an appropriate blue to color the hydronetwork (it is possible that this may have been blue automatically).


[![river_blue](http://geospatialhistorian.files.wordpress.com/2013/02/river_blue.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/river_blue.png)



	
  * Choose Add Vector Layer again.

	
  * click Browse, find your downloaded Prince Edward Island shapefiles in the folder

	
  * select “1935 inventory_region”  and double click on 1935_inventory_region.shp


This will add a dense map showing the different forest cover in 1935. However, to see the different categories, you will need to change the symbology to represent the different categories of forest with different colours. We will need to know which column of the database tables includes the forest category information, so the first step is to open and inspect the attribute table.

	
  * right click on the 1935_inventory_region Layer and click on Open Attribute Table


[![open_attribute_table](http://geospatialhistorian.files.wordpress.com/2013/02/open_attribute_table.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/open_attribute_table.png)

An Attribute Table will open. It has a number of categories and identifiers. Of particular interest is the LANDUSE category which provides information on the forest cover in 1935. We will now show you how to display these categories on the map.

[![OpenAtrribute](http://geospatialhistorian.files.wordpress.com/2013/02/openatrribute.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/openatrribute.png)



	
  * Right click on the 1935_inventory_region layer again and this time choose Properties (alternatively, the shortcut is to double click on the 1935 Layer).

	
  * right click the layer in the right hand menu and choose Properties.

	
  * click Style along top, click on “Single Symbol” on top left and select “Categorized”

	
  * beside Column choose “Landuse”

	
  * under Color ramp choose Greens

	
  * click Classify

	
  * in Symbol Column, choose the furthest down dark green square (with no value beside it) and hit the “Delete” button; also delete the Developed category, as we want to highlight forested areas


[![forest_types_after_delete](http://geospatialhistorian.files.wordpress.com/2013/02/forest_types_after_delete.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/forest_types_after_delete.png)



	
  * in Layers sidebar menue, click on the little arrow beside 1935_inventory_region to view the legend.



	
  * You can now see the extent of the forests in 1935. Next, we will add a layer of roads.



	
  * under Layer on toolbar, choose Add Vector Layer

	
  * click Browse, find your downloaded Prince Edward Island shapefiles in the folder

	
  * select “PEI_highway” and double click on PEI_highway.shp

	
  * click Style along top, click on “Single Symbol” on top left and select “Categorized”

	
  * beside Column choose “TYPE”

	
  * click Classify

	
  * in Symbol Column, choose symbol beside “primary” choose the dotted red line under Saved styles


[![red_roads](http://geospatialhistorian.files.wordpress.com/2013/02/red_roads.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/red_roads.png)



	
  * repeat for primary link

	
  * click Symbol beside secondary and change color to black and width to 0.7

	
  * repeat for secondary link

	
  * click OK. You will now have the highways and other major roads represented on the map.

	
  * under Layer on toolbar, choose Add Vector Layer

	
  * click Browse, find your downloaded Prince Edward Island shapefiles in the folder

	
  * select “PEI_placenames”

	
  * double click on PEI_placenames

	
  * choose Labels tab at top, click Display labels, in Field containing label select Placenames


[![label](http://geospatialhistorian.files.wordpress.com/2013/02/label.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/label.png)



	
  * Change the Placement to "Below Right"

	
  * Change Font size to "18"

	
  * Labelling is where QGIS falls well short of real cartography - it will take tinkering to adjust settings to display the detail desired for a presentation. Try changing the different settings to see how symbols and displays change.


Note that you can click to add and remove the various layers we've added to the map much the same way you did in Google Earth. Click on the check boxes to remove and add the various layers. Drag and drop layers to change the the order they appear. Dragging a layer to the top will place it above the rest of the layers and make it the most prominent.

	
  * having created a map using vector layers, we will now add or use our first raster layer. This is a  good time to save your work.


**Opening Rasters**

**R****aster** data are digital images made up of grids. All remote sensing data such as satellite images or [aerial photos](http://en.wikipedia.org/wiki/Orthophoto) are rasters, but usually you can't see the grids in these images because they are made up of tiny pixels.  Each pixel has its own value and when those values are symbolized in colour or greyscale they make up an image that is useful for display or topographical analysis.  A scanned historical map is also brought into GIS in raster format.



	
  * download: ["PEI_CumminsMap1927.tif"](https://www.dropbox.com/s/5g7964rpu1w2ou1/PEI_CumminsMap1927_compLZW.tif) to your project folder.

	
  * under Layer on toolbar, choose Add Raster Layer (alternatively the same icon you see next to “Add Raster Layer” can also be selected from tool bar)


[![raster](http://geospatialhistorian.files.wordpress.com/2013/02/raster.png)](http://geospatialhistorian.files.wordpress.com/2013/02/raster.png)



	
  * find the file you have downloaded titled "PEI_CumminsMap1927.tif"

	
  * you will be prompted to define this layer's coordinate system. In the Filter box search for "2291", then in the box below select "NAD83(CSRS98) / Prince Edward Isl. (Stereographic)..."


[![defineCRS](http://geospatialhistorian.files.wordpress.com/2013/02/definecrs.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/definecrs.png)



	
  * the map should appear below the vector data. Move it to the bottom of the menu if necessary.

	
  * Now we would like to make the coastline more visible, so double-click on coastline_polygon, select Style, click the Change button (with wrench), in the following window change Border color to Red, increase Border to 0.5, click OK.

	
  * You should see the coastline layer clearly. Zoom in and inspect. Notice that the alignment is relatively good, but not perfect. We will learn more in lesson 4 about the challenges of georeferencing historical maps to give them real world coordinates.


[![cummins_map_1927](http://geospatialhistorian.files.wordpress.com/2013/02/cummins_map_1927.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/02/cummins_map_1927.png)

**You have learned how to install QGIS and add layers. Make sure you save your work!**
