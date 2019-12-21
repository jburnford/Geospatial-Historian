---
author: cljim22
comments: true
date: 2013-02-04 16:43:19+00:00
layout: post
link: https://geospatialhistorian.wordpress.com/2013/02/04/the-geospatial-historian-part-1-niagara-falls/
slug: the-geospatial-historian-part-1-niagara-falls
title: 'The Geospatial Historian: Part 1, Niagara Falls'
wordpress_id: 181
---

_By Dan Macfarlane_

[From the Otter.](http://niche-canada.org/node/10547)

The modules are designed similar to Programming Historian lessons, and will potentially be offered there as well. After getting the [necessary software](http://www.parallels.com/products/desktop/) that allowed me to run [ArcGIS 10](http://www.esri.com/software/arcgis/arcgis10) on my Mac, taking online training modules made available for free through the Carleton University library, and collaborating with Jim and Josh, I have been available to develop these skills beyond what appeared in my [original posts](http://niche-canada.org/node/9890). What follows is the first of a series of examples of what will appear in our hands-on learning modules on using historical GIS.

The two maps contained in this post are both of Niagara Falls, and are part of my ongoing research about the engineering of the Niagara Falls hydro-electric landscape – basically, showing how Niagara Falls borders on the artificial – to the point that one would be tempted to say that the waterfall is little more than an elaborate faucet – because it has been so manipulated by Canada and the U.S. to produce hydro power and the effect on the actual cataract.

I’m writing a book on this subject, but for those who are curious and don’t want to wait several years for the book to be done, I have a chapter on Niagara in the upcoming environmental histories of southern Ontario collection that will coincide with [ASEH Toronto](http://aseh.net/conference-workshops/toronto-conference-2013) (in fact, I’m co-leading [a tour to Niagara](http://aseh.net/conference-workshops/toronto-conference-2013/special-field-trip-to-niagara-falls-sunday-7-april) as part of the conference) and I have an article on the topic forthcoming in the journal Environmental History. And for those who don’t want to wait several more months, see a blog post I did earlier this year on [ActiveHistory.ca](http://activehistory.ca/2012/05/above-and-below-manipulating-the-niagara-waterscape/)

Back to the mapping. For the first map (Hydro-electric Landscape of Niagara Falls) the initial step was finding the right base maps and layers (a base map is akin to a background image on which you do your digital mapping – in this case the base map is a Google Earth picture). I wasn’t entirely sure what I was looking for, but I knew that I wanted to create a map of the hydro-electric landscape of Niagara Falls. I scoured the internet for appropriate base maps of Niagara Falls, both present and historic. I also searched for aerial photos, which are sometimes used as base maps. In an Otter [post](http://niche-canada.org/node/10401) earlier this year Josh gave useful tips on places to look for map data.

I used a .jpg of map from Canadian Geographic as a raster image, which are common to use as base maps (there are two main types of data/image: vectors, which are essentially made up of points, lines and polygons, and raster images, which like any digital image are made up of pixels on a grid), and then matched it up with an aerial photo using georeferencing (which I’ll explain a bit further down). At first I attempted a straight-above aerial view without any raster image – so that the different features you see in the final map were all on a white background. So after some quasi-successful starts, and going back for help to the various ArcGIS education resources I had at my disposal, I had made some headway.

The simplicity and non-cluttered effect of the blank background had some advantages, but I wanted a different angle as well as a representation of the surrounding communities geographic features, such as the water. I downloaded a map from Google Earth at an oblique angle to use as a base map, which is what you see in this post, and set out to georeference and digitize the Canadian Geographic map.

Georeferencing involves creating control points so that the software will match up the maps, as maps of the same area don’t necessary line up perfectly (some maps of the same features will be to such different dimensions and proportions that it won’t be possible to match them up without extreme distortion). So I put control points at Horseshoe Falls, Goat Island, Lake Ontario, Grand Island, various older hydro stations – and kept adding control points until the maps lined up.

Then I started digitizing features. Digitizing features really just means any type of drawing, tracing, or creating of something on a new layer as a digital vector (i.e. a point, line, or polygon). So the hydro station, the tunnels, the outline of the reservoirs are all digitized information that I created via the drawing feature on ArcGIS 10. An easy aid for doing this is to adjust the transparency on one of the two stacked maps so that you can see them both at the same time for tracing purposes.

All this of talk of layers might have you wondering what a layer is. Think of layers as transparencies on the overhead projectors your teacher might have used in elementary or high school. Each feature – be it road or a type of building or a type of tree – that you create is done on a new layer; thus, the information is independent of the other types of information, and you can add or remove it as you wish

To digitize vectors as a point line or polygon, one has to decide which best represents the real world feature. For representing cities on a world wide map, a point would be a good idea; but to represent the limits of that city in a zoomed-in view, a polygon would be useful. If we were looking at a map of North America, the Niagara River would be best represented with a line; but if we are looking at a close-up of the river, such as in the post, a polygon of the river’s shape would more effectively show its shape.

In the map you see here, the canals, conduits, and tunnels are line features, while the power stations and reservoirs are polygons (transparent on the inside to show the features in the base map, below). I didn’t actually use a polygon for the actual river and waterfalls, as I found that the the base map better illustrates those.

Adding labels was fairly straightforward, and it was relatively easy to shape text labels around certain features (e.g. running parallel to tunnels). For other features, there is an indicator line from the label text to the feature – this is a “call-out” line.

The second map (Modifications of Horseshoe Falls) shows the fill and excavations that were done in the 1950s, while the former crestlines indicate the amount of recession that has taken place. Because it used mostly the same approach and skills, as well as similar types of data (photographs and blueprints), I had used in creating Map 1, I completed this map much quicker.

![Horseshoe Falls](http://geospatialhistorian.files.wordpress.com/images/Map2-ModificationsOfHorseshoeFalls.jpg)

There you have it. Nothing too complex compared to the kind of stuff GIS can do – in fact, what I was doing was mostly cartographic map-making rather than using the full abilities of the software to compute numbers and create new information (for example, the information in Map 2 could be used to measure the amount of feet the crestline has receded, or the amount of square feet that were reclaimed from the waterfall at the flanks). But I also found what I created quite useful for representing spatially what I was writing about in my research, and thus this is the type of end product that is within the reach of historians with a general competence around computers. Each map would benefit from further work, such as having a table of contents to better explain features, but I haven’t had time for that yet … after all, who knows what inane trend I’ve been missing while writing this post.
