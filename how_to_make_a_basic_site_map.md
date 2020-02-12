**How to Make a Basic 2D Site Map**

*This tutorial will cover the basics of ArcMap through the creation of a site plan of Morningside Heights*
What you will learn:
* How to add tabular and vector data in ArcMap
* How to visualize tabular data with coordinates on a map
* How to export data to CAD and Illustrator
* How to use selection and clipping tools 
* How to work with the attribute table  

ArcGIS consists of three separate programs: ArcMap for two-dimensional mapping, ArcScene for three-dimensional mapping and ArcCatalog for database management. Shapefiles and CSV (comma-separated value) files are among the most commonly used file formats for ArcGIS. Shapefiles are composed of up to six different file formats, three of which are essential: .shp which contains the geography and is the main file, .shx which is the index file and .dbf which is the database file. Spatial data can be created or downloaded from a variety of sources, many of which are detailed [here](https://guides.library.columbia.edu/GIS). This tutorial uses the following datasets:
* [NYC Building Footprints](https://data.cityofnewyork.us/Housing-Development/Building-Footprints/nqwf-w8eh)
* [Sidewalks](https://data.cityofnewyork.us/City-Government/Sidewalk/vfx9-tbb6)
* [Open Space(Parks)](https://data.cityofnewyork.us/Recreation/Open-Space-Parks-/g84h-jbjm)
* [NYC Neighborhood Tabulation Areas](https://data.cityofnewyork.us/City-Government/Neighborhood-Tabulation-Areas-NTA-/cpf4-rkhq)
* [Wifi Hotspots](https://data.cityofnewyork.us/Social-Services/NYC-Wi-Fi-Hotspot-Locations/a9we-mtpn)

Projections are two-dimensional representations of the earth - meaning they are representations of the curved surface of the earth on a flat surface. They matter for the shape, size and angles of the material you are working with. As they translate a curved surface to a flat surface, projections inherently distort distances, locations and sizes to different degrees depending on the projection system. 

Projections are based on coordinate systems, which locate points on the surface of the earth. Geographic coordinate systems are measured in decimal degrees while projected coordinate systems have linear units such as feet or meters. There are agreed upon projections which aim to accurately reflect all of these for local areas across the globe. Often these take the form of systems of projections, in the U.S. we have the State Plane coordinate system, globally there is the Universal Transverse Mercator coordinate system. If you're unsure of the conventional coordinate system for the place you're working, Googling it usually provides the answer. 

1. To get started, open up ArcMap. Go to `Start` > `Programs` > `ArcGIS` > `ArcMap`. A dialogue box should appear, as below. 
2. To start a new map project, select `Blank Map` and click `OK`.
![image](images/t1-01.jpg)

3. To Add Data to the map, click on the `Add Data` button on the toolbar, shown below. A dialogue will appear, allowing you to navigate to the data files you want to add as layers of your map. 
![image](images/t1-02.jpg)

4. Next, click on the `Connect to Folder` button in the dialog box that appears. This allows you to add an easily accessible folder for the project. 
![image](images/t1-03.jpg)

5. Navigate to the folder where the data is saved and add in the [Neighborhood Tabulation Areas](https://data.cityofnewyork.us/City-Government/Neighborhood-Tabulation-Areas-NTA-/cpf4-rkhq) shapefile. 

Once you have added data, you can zoom and pan using the buttons on the toolbar. You can arrange the ordering of the layers by stacking the data layer names in the `Display` tab of the `Table of Contents` on the left of the screen. The ordering of the layers in the `Table of Contents` will correspond to their ordering in the map. To change the symbology of your layers, right-click on the layer name and choose `Properties`. A dialogue will appear. Under the `Symbology` tab, you will find the options for coloring or visualizing your data.
 	
## Working with 2D Data:
The first shapefile you add into ArcMap sets the coordinate system for the entire document. 
![image](images/t1-04.jpg)

6. To view the `projection`, right-click on the layer name, click `Properties` and switching to the `Source` tab. 
![image](images/t1-05.jpg)
![image](images/t1-06.jpg)

7. Compare this to the `coordinate system`, which you can check by right-clicking in the data frame and selecting `Data Frame Properties`. 
![image](images/t1-07.jpg)

8. For this tutorial, we will be using the standard New York City coordinate system which you can find under `Projected Coordinate System` > `State Plane` > `NAD 1983 (2011) (US Feet)` > `NAD 1983 (2011) StatePlane New York Long Isl FIPS 3014 (US Feet)`. A warning will pop up after hitting OK, click yes on there. This is also where you can see the map's units. Change the coordinate system to this if it isn't already set to it. Whenever your map looks funny, check here first. 
![image](images/t1-08.jpg)

Now you'll notice that the map of New York looks different, and more typical of standard NYC maps.
![image](images/t1-09.jpg)

9. Next, add in the [Wifi Hotspots](https://data.cityofnewyork.us/Social-Services/NYC-Wi-Fi-Hotspot-Locations/a9we-mtpn) by clicking on the `Add Data ` button. There is no need to connect the folder again. You'll notice that the Table of Contents switches to the `List by Source` tab when you do this. 
10. To view the information in the table, right-click on the layer name and select `Open`. The attribute table contains information about geographic features. 
![image](images/t1-10.jpg)

11. Right-click on the layer name and navigate to `Display XY Data` to visualize this table on the map. The X field will be X, and the Y field will be Y automatically. When you hit OK, you'll get a warning about the table not having an Object-ID field - hit OK here. 
If the table has longitude and latitude fields, the longitude field will be X and the latitude field will be Y. If the points are placed in unexpected places, try clicking on `Edit` to change the coordinate system. Try `WGS84`, a standard global coordinate system.  
![image](images/t1-11.jpg)
![image](images/t1-12.jpg)

12. When the Wifi Hotspots are displayed as points on the map, the next step is to export this to a new shapefile. This must be done to preserve the points for future use, and to perform any operations on them. To do this, right-click on the layer name and go to `Data` > `Export Data`. 
![image](images/t1-13.jpg)

13. A dialog box will appear with the option to save the features using the sale coordinate system as the layer's source data or the data frame. We'll be saving this using the data frame's coordinate system as we applied a transformation to the data frame - this prevents you from needing to `Project` the data.
![image](images/t1-14.jpg)

14. Click on the `Browse` button beside the `Output Feature Class`.  Make sure to change the file's format from a `Geodatabase` to a `Shapefile`. Change the folder the file is being saved in by clicking on the dropdown at the top of the dialog box and be sure to rename it. Add the exported data to the map as a layer.
![image](images/t1-15.jpg)

Its good practice to remove the temporary layer with the points gotten from `Display XY Data`. 
15. To do this, right-click on the layer name and selecr `Remove Layer`.
![image](images/t1-16.jpg)

16. Add in the rest of the shapefiles - [NYC Building Footprints](https://data.cityofnewyork.us/Housing-Development/Building-Footprints/nqwf-w8eh), [Sidewalks](https://data.cityofnewyork.us/City-Government/Sidewalk/vfx9-tbb6) & [Open Space(Parks)](https://data.cityofnewyork.us/Recreation/Open-Space-Parks-/g84h-jbjm). You'll get a `Geographic Coordinate Systems` warning, just hit close on that dialog. 
The buildings shapefile is huge and will make ArcMap slow, so you can turn off the layer to make the program rub faster by unchecking the box beside its name. 
![image](images/t1-17.jpg)
![image](images/t1-18.jpg)

To isolate Morningside Heights from the Neighborhood Tabulation Areas, we will go back to the attribute table and select only the features that have a neighborhood name of Morningside Heights. 
17. Right-click on the layer name `(nynta)` and select `Open Attribute Table`. 
![image](images/t1-19.jpg)

You'll see that the `Attribute Table` contains different fields, including the `ntacode `and `ntaname`, which contain unique values for each feature. The `ntaname` field is what we'll use for the selection. 
18. In the `Attribute Table`, click on `Select by Attributes`, which is the third button from the left. 
![image](images/t1-20.jpg)

19. Double-click to select the `ntaname` field from the options on top and then click on `=` for the selection method. Click on `Get Unique Values` to populate the box on the right with the values from the selected field, `ntaname`. At this point, you can either scroll down or start typing Morningside Heights in the empty box beside `Go To:` to automatically scroll down. Doubleclick `Morningside Heights` to complete the query. 
![image](images/t1-21.jpg)

When you hit `Apply` and then `Close`, you'll see that only one neighborhood boundary is highlighted with a thick blue boundary line. If you can't see this clearly, try turning off the other layers by unchecking the box beside the layer names.
![image](images/t1-22.jpg)

20. Export this selection to a new shapefile by right-clicking on the layer name & going to `Data` > `Export Data`, same as you did with the Wifi Hotspots. You'll also select the option to use the same coordinate system as the data frame. Save it in the folder you've been working in. Add this new file to the map. 
![image](images/t1-23.jpg)

Now that Morningside Heights has been picked out, we can clip the sidewalks, parks, buildings and Wifi hotspots to this boundary in two ways.`Selecting by location` selects all the features from a layer that intersect (or have another specified relationship) with features of another layer while `clipping` overlays one layer on another and cuts off input  at the point they do not intersect with the features of the clip layer. Any issues with clipping usually arise from the projections of the two files being different. 

21. First, right-click on the layer name and select `Zoom to layer` to view the map more clearly.
![image](images/t1-24.jpg)
![image](images/t1-25.jpg)

22. To `Clip` the sidewalks to the Morningside Heights boundary, we can select `Geoprocessing` > `Clip` from the toolbar at the top of the ArcMap window. 
![image](images/t1-26.jpg)

23. Select `Input features` and `Clip features` by clicking on the dropdown arrow or the folder beside them on the right. Input features will be the sidewalks layer while clip features will be the Morningside Heights layer. 
24. Click on the Folder to the right of `Output Feature Class` to specify where the new clipped geometries will be saved. 
![image](images/t1-27.jpg)

When you hit OK, you'll have only the sidewalks in Morningside Heights clipped to that boundary in a new file. There's no need to export the data. 
![image](images/t1-28.jpg)

25. To select the Wifi Hotspots in Morningside Heights, go to `Selection` > `Select by Location` from the toolbar at the top of the ArcMap window. 
![image](images/t1-29.jpg)

26. Leave the default selection method, `select featured from`, and select Wifi hotspots as the target layer and Morningside Heights as the source layer. Also leave the default spatial selection method selected, which is `intersect the source layer feature`. Hit OK. 
![image](images/t1-30.jpg)
![image](images/t1-31.jpg)

27. After all the Wifi hotspots in Morningside Heights are selected, export to a new shapefile by right-clicking the layer and going to `Data` > `Export Data`. 
![image](images/t1-32.jpg)

28. Repeat either the `Clip` or `select by location` operations to get the parks and buildings in Morningside Heights. Don't forget to export data if you `select by location`.
![image](images/t1-33.jpg)
 	
## Laying Out and Exporting Your Map:
You can export one or more layers to CAD. 
29. To export one layer, right-click on the layer name and go to `Data` > `Export to CAD`. 
![image](images/t1-34.jpg)

30. To export multiple layers at once, you will need either the `Search` or `ArcToolbox` windows. These are accessible from the buttons at the top of the page. 
![image](images/t1-35.jpg)

31. Search for `Export to CAD` or find in the Arctoolbox under `Conversion Tools` > `To CAD`. 
![image](images/t1-36.jpg)
![image](images/t1-37.jpg)

32. When you are in the `Export to CAD` dialog box, select all the layers you want to export. The default output type is DGW_R2018 as file type, but you can change this if you need the file to be opened using an older version of CAD. Also, remember to always choose a destination location by clicking on the folder beside `Output File`; otherwise GIS will choose a path for you and it will become difficult to locate your files. 
![image](images/t1-38.jpg)

To export the map to other formats, we will need to switch from `Data View` to `Layout View`. 
33. This can be done by clicking on the icon of a page in the lower left corner of the map window as below.
![image](images/t1-39.jpg)

Next, we will make a map layout. The map window should now show you your map's data frame on a sheet of paper. You can adjust the size and location of the data frame by adjusting its bounding box. You can also right-click in the data frame and select `Page and Print Layout` to change the paper size. Uncheck `Use Printer Paper Settings` to be able to change the page width and height. You can always `Zoom to Layer` by right-clicking on a layer name.
![image](images/t1-40.jpg)
![image](images/t1-41.jpg)

A new set of tools to zoom and pan appears when you are in the `Layout View`. The `Data View` zoom and pan tools are still active and will affect the map within the data frame. To zoom and pan on the page without affecting the map, use the (page) `Zoom` and `Pan` toolbar. 
![image](images/t1-42.jpg)

34. Create a `Bookmark` to save the location and scale of the layout for the future, as switching between the Data and Layout view moves the map around. Click on `Bookmarks` > `Create Bookmark` from the toolbar at the top of the page. 
![image](images/t1-43.jpg)

35. You can add standard elements to your map through the `Insert` menu shown below. Add in a `Legend`, `North Arrow` and `Scale Bar`. 
![image](images/t1-44.jpg)

When you are finished with your map, you can export it to a variety of formats.
36. Go to `File` > `Export Map` to reach a dialog box where you can choose your export format and save your map. 
![image](images/t1-45.jpg)

37. Change the `Save as type` option to the file type ou want, such as AI and JPEG. If you're exporting to PDF or AI, make sure to switch to the `Format` tab and check `Vectorize layers with bitmap markers/fills` and check `Convert Marker Symbols to Polygons` to enable future editing. Don't forget to change the save location. 
![image](images/t1-46.jpg)