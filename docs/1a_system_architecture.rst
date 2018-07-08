System Architecture
===================

Please note that this page only describes the specification for the project's final output i.e. the citizen facing web and mobile applications currently in place for the Jaibik Map project and does not include descriptions of other details such as data collection, species distribution modeling methodology, etc.

Challenges
----------

For each mammal, the outputs generated during the modeling exercise comprise of raster (TIFF) files at a 1km*1km resolution for the whole of Nepal across two different climate change scenarios, and 3 time periods.

Based on this understanding, it was clear that serving such large datasets for smooth, interactive viewing in the web browser was one the major challenges that we needed to address. It was what one would called an optimization problem. How could we ensure that all of the information generated can be quickly made available to the user, while at the same time ensuring that the resolution of the data is not compromised?

Using vector tiles to serve large geospatial datasets
-----------------------------------------------------
Traditionally, the use of standard formats such as GeoJSON has greatly simplified and accelerated the process of developing data driven, web based maps. However, when it comes to serving large datasets that contain hundreds (if not thousands) of geometries, this approach seems to be lacking—the geojson file becomes much larger than what can be handled by the web browser, causing the application to lag/crash.

After a fair amount of research by the technical team, it was clear that the use of vector tile layers could be one possible way to get around this problem. Serving the vector representation of the data—which is much smaller than bitmap images served in any raster tile— would not only help reduce overall data transfer,  but also provide us (developers) access to the data being served in all stages of map development. This, in turn would also enable greater flexibility in terms of data-driven styling and tile layer customization.

Proposed system
---------------

.. image:: _data/system_architecture.png
    :alt: Architecture diagram for the Jaibik Map system

The above diagram outlines the overall system architecture followed in Jaibik Map.

As already explained in the previous section, the technical team has used a vector tile server based  architecture to serve geospatial data for consumption in the web and mobile applications.  
