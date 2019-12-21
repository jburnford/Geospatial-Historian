---
author: joshmac
comments: true
date: 2013-12-10 18:33:29+00:00
layout: page
link: https://geospatialhistorian.wordpress.com/lesson-5-3d-landscapes-and-buildings-sketchup/
slug: lesson-5-3d-landscapes-and-buildings-sketchup
title: 'Lesson 5: 3D Landscapes (SketchUp)'
wordpress_id: 665
---

In this lesson, you will learn how to install Trimble SketchUp, locate the geographic site of a model in SketchUp, add modern imagery from Google Earth, and add historical imagery such as aerial photographs to the model.

In [Lesson 4,](http://geospatialhistorian.wordpress.com/lessons/lesson-4/) we mentioned that advanced forms of georeferencing would allow you to drape historical imagery over a DEM (digital elevation model) and create "fly-overs" of historical landscapes. In this lesson we will do the next best thing and perform fly-overs of historical landscapes in SketchUp. No GIS is required.



	
  1. **Installing _SketchUp Make_**

	
  2. **Setting up your first SketchUp model**

	
  3. ****Adding layers and historical aerial photographs to SketchUp**
**


Note: the disadvantage of using SketchUp for a 3D landscape is that the historical imagery will only have limited accuracy in a SketchUp model, and the modern map and terrain will be limited to the resolution available on Google Earth. However, the advantage is that it is very simple to view the landscape in 3D and "build" new features including historical buildings and natural features.

[caption id="attachment_713" align="alignnone" width="375"][![Model of Green Gables house placed on 1968 Aerial Photographs and 3D terrain](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-32-33-pm.png?w=625)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-32-33-pm.png) Model of Green Gables house placed on 1968 Aerial Photographs and 3D terrain[/caption]

http://www.youtube.com/watch?v=gpp6j8AKfrI

**Getting started:**

Before proceeding with this lesson, it would be useful to review [Lesson 1](http://geospatialhistorian.wordpress.com/lessons/lesson-1/) on Google Maps and Google Earth, although this is not a requirement for using SketchUp.

_Install and set up SketchUp_

[SketchUp](http://en.wikipedia.org/wiki/SketchUp) is a 3D modeling program popularized by Google and now offered in freeware ([SketchUp Make](http://www.sketchup.com/products/sketchup-make)) and commercial (SketchUp Pro) versions by Trimble Navigation.

Download SketchUp Make [here](http://www.sketchup.com/download). Enter your (1) intended use (2) contact information and operating system, and (3) version of SketchUp. Choose SketchUp Make. Review and agree to the terms and click download.

[![Download SketchUp Make](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-09-13-pm.png?w=300)](http://www.sketchup.com/download)

The download gives you an installation package which will install the software and let you start using it immediately.

When you open SketchUp the program will probably ask you to choose a template. Choose the units (metric vs imperial) you prefer to work in, and the kind of background you want to use. Then click "Start using SketchUp."

This is what your opening screen will probably look like on a Mac.

[![SketchUp opening screen](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-23-24-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-23-24-pm.png)

Orbit around the model with the orbit, pan and zoom tools (or with the centre roller wheel and button on a 3-button mouse). Note holding down the "Shift" key while orbiting allows you to pan left and right or up and down.

[![SU Navigation buttons](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-53-59-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-53-59-pm.png)

Other useful navigational tools like "Standard Views" tools can be found in the Customize Toolbar section (see below).

The most commonly used features in SketchUp are the drawing tools, such as the line, rectangle, circle, and polygon tools.

[![SU drawing tools](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-29-40-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-29-40-pm.png)

Once you create basic shapes you can easily modify them with the push/pull and offset tools

[![SU push tools](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-31-07-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-31-07-pm.png)

or with the move, rotate, and scale tools

[![SU move tools](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-31-40-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-31-40-pm.png)

The drawings will all represent real world dimensions, and the person standing near the red, green, and blue axes helps create a reference point.

[![Derrick - the point of reference](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-39-34-pm.png?w=237)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-39-34-pm.png)

The "Measurements" window at the bottom right shows the dimensions of each drawing you make or select.

[![SU Measurements bar](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-39-57-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-39-57-pm.png)

But **before doing any modeling** we are going to set up a landscape so the software knows where, and what scale, our model will represent.

**Setting up the model**

_Activate layers_

SketchUp layers act similarly to GIS layers. They represent subsections of the model and they can be turned "off" and "on" in the display. And, as in GIS, these layers are critical to visualizing a historical model where elements change over time. Unfortunately, at the point of writing (Fall 2013) it is not yet possible to group, sort, or export layers. Still, they are essential to historical visualizations and hopefully they continue to improve.

Click Window and make sure "Layers" and "Entity Info" are selected.

[![SU Layers](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-48-17-pm.png?w=150)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-48-17-pm.png)

This opens two additional windows which can then me moved, docked, or minimized. They currently contain only 1 layer: "Layer0"

Snap the “Entity Info” Window to the bottom of the “Layers” Window.

[![Layer and Entity windows](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-55-06-pm.png?w=229)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-55-06-pm.png)

Layer0 is the default layer. All features that you add to your model will appear here. Other features that you import (either from Google Earth or from from the 3D model warehouse) will usually appear as separate layers. So let's start by adding a location.

_Add location_

This step adds your desired location to the model.

First, click the "Add location..." button

[![SU Add location](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-43-57-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-43-57-pm.png)

Then close the message with the x

[![SU GE info message](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-45-40-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-45-40-pm.png)

and enter a location in the search bar. This accesses Google Earth's search engine and makes geolocating the model easy. Enter "Cavendish, PE"

[![SU GE location search](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-45-52-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-45-52-pm.png)

Click "Select Region"; use the blue pins to set the parameters to the following area (the Southwest of the main intersection in Cavendish), and click "Grab"

Note: selecting large regions will increase the project file size and reduce the performance of your computer.

[![SU GE Grab location](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-03-15-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-03-15-pm.png)

Note: some macs will show the selected region but will not import it into the model. For some reason this bug affected all of the Macs at Western University, but not the Windows stations or other Macs.

**Save your project** as "Cavendish.skp"

The resulting screen looks like this

[![SU with GE imagery of Cavendish](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-21-44-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-21-44-pm.png)

and the layers window has changed to this. Two new layers were created for the Google Earth imagery.

[![SU layers bar w GE layers](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-21-50-pm.png?w=229)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-21-50-pm.png)

At this point you can start drawing new features on the map, (like you would on a GIS see [Lesson 3](http://geospatialhistorian.wordpress.com/lessons/lesson-3/)) with the drawing tools discussed above.

If you zoom into the middle of the map where the red, blue, and green axes meet, you will see that the reference person is likely standing in the middle of (or on) a forest, but that the map is in scale, proportional to the person. This axis is the centre point of the Google image you just imported. Once you start drawing new features it probably makes sense to move the axis out of the forest and onto a building site, but for now the green line points north and it is best to leave it in this location.

![SU Reference point in GE imagery](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-26-36-pm.png?w=300)

So far the imagery in this model is "flat." In other words it has 0 value on the Z (blue) axis. If you draw features onto the landscape and then give the Z axis positive or negative value (elevation) all or part of your model could be covered or left in the air. So before adding new feature we will turn on the terrain elevation.

This button needs to be added to the toolbar In our version of SketchUp. To do this click "View > Customize Toolbar."

[![SU customize toolbar](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-37-10-pm.png?w=172)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-37-10-pm.png)

Then find the "Toggle Terrain" button and drag it to the toolbar. Click Done.

![Screen Shot 2013-12-10 at 2.39.43 PM](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-39-43-pm.png?w=37)

![SU customize toolbar](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-38-51-pm.png?w=300)

Now click the "Toggle Terrain" button.

Note that the landscape now shows elevation, and the active layer in the layer window has switched from "Google Earth Snapshot" to "Google Earth Terrain."

[![SU active layer changed](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-42-09-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-42-09-pm.png)

Click the empty box to activate the "Google Earth Snapshot" and you will see that the terrain layer is considerably higher than the Snapshot layer near the edges. This is because our centre point is at a lower elevation. In other places, like the pond by the highway, the elevation is lower than the centre point and the Z value of the terrain imagery is negative.

[![SU Google Earth Terrain and Google Earth Snapshot layers](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-46-14-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-2-46-14-pm.png)

Explore the model so far. You are now ready to start adding, modifying, and visualizing historical landscapes and models!

**Adding historical aerial photographs to SketchUp**


_Remove Reference Character, and __Configure Layers_




Select the standard Google Earth person using the Select tool




[![SU Select tool](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-03-57-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-03-57-pm.png)




Hit delete




![SU delete figure](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-03-23-pm.png?w=300)




De-select the visibility of “Google Earth Snapshot.”




Select the visibility of "Google Earth Terrain."


_Creating Layers I_


Select all – Highlight everything or hold down CTRL+A (Command+A for Mac Users).




Right click on the Google Earth snapshot and select “Unlock.”




[![SU Unlock layer](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-05-07-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-05-07-pm.png)




While everything is still highlighted, right click and select “Explode.”




[![SU explode layer](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-05-22-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-05-22-pm.png)




While everything is still highlighted, copy everything by holding down CTRL+C (Command+C for Mac).




While everything is still highlighted, right click on the image and select “Make Group.”




[![SU make group from entitites](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-06-31-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-06-31-pm.png)




While everything is still highlighted, right click on the image and select “Lock”




Deselect the image by clicking outside the image.




_Adding New Layer(s)_




Select Edit from the Menu and click “**Paste in Place**”. This may take a few minutes depending on your computer's processing speed.




[![SU paste in place](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-06-16-pm.png?w=177)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-06-16-pm.png)




While everything is highlighted, right click and select “Make Group.”




_Assigning New Layer_




In the “Layers” window, click the Plus (+) button to add a new Layer




Name new layer “GE Terrain 2” and hit Enter (return)




With the image still highlighted, in the “Entity Info” window, select “GE Terrain 2” from the Layer dropdown box.




[![SU assign entities to layer](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-07-46-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-07-46-pm.png)




Your second snapshot is now saved in the “GE Terrain 2” layer.




_Adjusting Layers_




In the “Layers” window, deselect the visibility of “Google Earth Terrain.”




Select Image now on screen (GE Terrain 2).




Right click and select “Lock.”




_Adding another Layer_




Return to the step "Adding New Layer(s)" above and paste another layer into the model with the name "GE Terrain 3." This will allow you to add a third layer (and so on) to the model for importing historical aerial photography.




_Importing Historical Aerial Photograph or Images_




Deselect the image by clicking outside of the terrain image.




Download the following 1968 and 1935 aerial images as jpgs and save them to your computer






	
  * 1968 http://geospatialhistorian.files.wordpress.com/2013/12/ora20357_185.jpg

	
  * 1935 http://geospatialhistorian.files.wordpress.com/2013/12/5056-108.jpg




In SketchUp select “File” from the menu and click “Import”




Navigate to your 1968 image (ora20357_185.jpg) and select “Import”




Note: Change the “Format” dropdown bar to "all supported images" if you cannot locate your image.




Click in the window to place your image




Move your mouse to adjust your image to the approximate size (we will resize later) and click on the screen.




![SU 1968 image imported](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-3-43-11-pm.png?w=625)Your image is now in the model




_Adjusting and Resizing the Image (option 1 - try this first)_




Select “View” from the menu and click “Hidden Geometry”




Right click on your recently imported photo and select “Hide”




This makes your image transparent and helps you adjust its size and location.




Select “Move” from the toolbar. (Hint, hold the up arrow when drawing to continue along the blue axis). By moving your mouse, this will let you adjust the height of your image. Adjust the height so the entire, or most of, your photo appears just above the satellite imagery.




Use the “Orbit” button on your toolbar to help you see the adjusted height.




Use the “Scale” option on the toolbar to then scale the photo so major features like roads line up.  Use the “Rotate” option on the toolbar to rotate photo, if necessary. Note: in this example the 1968 aerial photo is georeferenced* already. It will not require rotation, only scaling and moving. The 1935 aerial photograph is oriented to the East, so it needs to be rotated about 90 degrees in SketchUp.




Repeat the process until you have lined up your photo to the Google Earth terrain imagery




Once you are happy with the alignment, right click on your photo and select “Unhide.” Select “View” from the menu and deselect “Hidden Geometry.”




__Adjusting and Resizing the Image_ (method 2)_




Find two control points that you can identify on Google Earth terrain imagery and on the historical air photo(s).




Use the draw line tool to start drawing a line from the control point on the surface of Google Earth Terrain upward about 900 feet (Hint, hold the up arrow when drawing to continue along the blue axis). Repeat for the second control point.




Import and Align the first aerial photo using the scale and move tools described above (in _method 1)_ until the control point lines intersect with the two control points.




[![SU Control point method of alignment](http://geospatialhistorian.files.wordpress.com/2013/12/control-point-method-of-alignment.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/control-point-method-of-alignment.png)




Import and Align the second aerial photo. The two images and control point lines will look like this from the side view.




[![SU preparing multiple 2D aerial images for application to 3D terrain](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-03-55-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-03-55-pm.png)




Assign the first aerial photo to a new layer. In the “Layers” window, click the Plus (+) button to add a new Layer




Name new layer “1968 Air Photo” and hit Enter (return)




With the image still highlighted in blue, in the “Entity Info” window, select “1968 Air Photo” from the Layer dropdown box.




![SU Assigning aerial photo to new layer](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-32-21-pm.png?w=300)




Assign the second aerial photo to a new layer called "1935 Air Photo" following the steps above.




_Preparing the Photo_




Turn off the "1935 Air Photo" in the layer window.




Select your 1965 photo in the main project window, right click, and select “Explode.” The surface of the image will take on a blue stipple.




[![SU explode image surface](http://geospatialhistorian.files.wordpress.com/2013/12/su-explode-image-surface.png?w=178)](http://geospatialhistorian.files.wordpress.com/2013/12/su-explode-image-surface.png)




[![SU blue stipple](http://geospatialhistorian.files.wordpress.com/2013/12/su-blue-stipple.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/su-blue-stipple.png)




Select the surface of your photo, right click, navigate to “Texture” and ensure that “Projected” is selected. If it is not, select “Projected.”




[![SU project image surface](http://geospatialhistorian.files.wordpress.com/2013/12/su-project-image-surface.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/su-project-image-surface.png)




_Applying the Photo(s)_




Make sure that the “Google Earth Terrain” in the Layers window is deselected at this point ("Google Earth Snapshot" should also have been deselected throughout this lesson). If this makes the entire model disappear you will have to return to the step "_Adding New Layer_" above.




Right click on your satellite image and select “Unlock.”




Click on the surface of your 1968 air photo.




Click the “Push/pull” button on the toolbar.




[![SU push tools](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-31-07-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-1-31-07-pm.png)




Click on the photo and drag downwards so that it completely intersects with the Google Earth terrain.




This creates a large box with your photo.




[![SU extruded aerial photo](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-30-23-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-30-23-pm.png)




Select all – Highlight everything or press CTRL+A (Command+A for Mac)




Right click on selection, hover over “Intersect Faces” and select “With Selection"




[![SU Intersect Faces > with selection](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-30-51-pm.png?w=191)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-30-51-pm.png)




Depending on the size of your image, this make take a while and may cause SketchUp to freeze temporarily.




_Painting the Image_




From the menu bar, select paint bucket.




[![SU paint bucket](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-20-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-20-pm.png)




While holding down CTRL (Command for Mac) click the paintbucket on the surface of your photo (an eyedropper image will appear with the paintbucket).




This creates the photo as a unique texture.




[![SU colour paint bucket air photo as unique texture](http://geospatialhistorian.files.wordpress.com/2013/12/su-colour-paint-bucket-air-photo-as-unique-texture.png?w=178)](http://geospatialhistorian.files.wordpress.com/2013/12/su-colour-paint-bucket-air-photo-as-unique-texture.png)




Select the top of your picture box. Click delete.




[![Screen Shot 2013-12-10 at 4.31.03 PM](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-03-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-03-pm.png)




Select the surface of your satellite image inside the box.




Right click on surface and click “Explode.”




Select the surface of your satellite image that appears in your photo box. The blue stipple appear again.




Click “Paintbucket” again on the toolbar.




[![SU paint bucket](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-20-pm.png)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-20-pm.png)




Click on the satellite image that appears within your photo box. You will now have the 1968 air photo “painted” upon your satellite image. 




[![SU landscape terrain with 1968 imagery applied](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-25-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-25-pm.png)




Note: This only paints the image within the picture box, leaving the satellite image on the outside.




To delete the picture box, select the various entities and click delete. Hint: triple-clicking on on of the edges of the box will select the connected entities. Click delete.




[![SU landscape terrain with 1968 imagery applied, cleaned](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-35-pm.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/screen-shot-2013-12-10-at-4-31-35-pm.png)




Select all by pressing CTRL+A (Command+A for Mac), right click  and select “Make Group”




While everything is still highlighted, right click and select “Lock”




All done!




In order to create another historical terrain layer from the "1935 Air Photo" then return to the step "_Preparing the Photo_" above. Turn on the layer "1935 Air Photo" and follow the same process with "GE Terrain 3."


Note: to see the original satellite image, select the visibility of the “Google Earth Terrain” in the “Layers” window and deselect “GE Terrain 2” and "GE Terrain 3."

**Bonus: Importing building models into the historical ****terrain**.

Now that you have a 3D image of the terrain in 1968 (and 1935) you can import one of the models of Green Gables house that has been created by members of the SketchUp community.

Click the import from 3D warehouse button.

[![SU get models from warehouse](http://geospatialhistorian.files.wordpress.com/2013/12/su-get-models-from-warehouse.png)](http://geospatialhistorian.files.wordpress.com/2013/12/su-get-models-from-warehouse.png)

Search for Green Gables, click Download Model, and agree to import the model directly into SketchUp.

[![SU 3D warehouse](http://geospatialhistorian.files.wordpress.com/2013/12/su-3d-warehouse.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/su-3d-warehouse.png)

[![SU 3D warehouse green gables](http://geospatialhistorian.files.wordpress.com/2013/12/su-3d-warehouse-green-gables.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/su-3d-warehouse-green-gables.png)

[![SU 3D warehouse import directly to SU](http://geospatialhistorian.files.wordpress.com/2013/12/su-3d-warehouse-import-directly-to-su.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/su-3d-warehouse-import-directly-to-su.png)

Because the model was created to scale in a geo-located model, it should appear in your model in the exact location. The main difference is that the modern model of the house will appear on a historical layer created with historical imagery.

_Add scenes and create an animation_

To add a series of scenes and create an animation, orbit to the location you would like to start and click "View > Animation > Add Scene"

[![SU add animation](http://geospatialhistorian.files.wordpress.com/2013/12/su-add-animation.png?w=254)](http://geospatialhistorian.files.wordpress.com/2013/12/su-add-animation.png)

Orbit to the next scene and click Add Scene again. Repeat this process until you have finished a tour of the site. A series of scenes will be listed at the top of the screen. These can be accessed at any time for quick viewing, played as an animation, or exported as a movie.

[![SU scenes for animation](http://geospatialhistorian.files.wordpress.com/2013/12/su-scenes-for-animation.png?w=300)](http://geospatialhistorian.files.wordpress.com/2013/12/su-scenes-for-animation.png)

To create a video from the animation select File > Export > Animation; select mp4; and click "Options" to change the resolution and other options for the video.

http://www.youtube.com/watch?v=gpp6j8AKfrI

*We use the term georeferenced to refer to the process discussed in Lesson 4. This is not quite correct in the case of the the 1968 aerial photographs. These images are professionally orthorectified, which means the distortions present in all ordinary photographs have been corrected to fit the 3D features of the Earth.
