**How to Make a Basic 3D Site Model**

*This tutorial will cover how to make a basic site model using both 2D and 3D features as well as elevation features*
![image](images/t4-final.jpg)

What you will learn:
* How to add data in ArcScene
* How to change the data frame's coordinate system
* How to visualize layers in 3D
* How to change base heights of layers
* How to extrude layers

This tutorial will be done in ArcScene. The data for this tutorial was generated in the [How to Make a Basic Site Map](/how_to_make_a_basic_site_map.md) and [How to Make a Basic Site Model](/how_to_make_a_basic_site_elevation_model.md) tutorials, and are all clipped to the Morningside Heights boundary:
* [Buildings](data/buildings_mh.zip)
* [Sidewalks](data/sidewalks_mh.zip)
* [Parks](data/parks_mh.zip)
* [Morningside Heights Boundary](data/mh.zip)
* [Elevation Raster](data/raster_mh.zip)
* [2D Contours](data/contour_mh.zip)
* [3D Contours](data/contour2ft_mh_3D.zip)

1. Open up ArcScene and familiarize yourself with the layout. It is quite similar to ArcMap. Add all the datasets. You do this exactly the same way as you would in ArcMap, using the `Add Data` button in the main toolbar. 
2. `Connect to Folder` and add in the building, sidewalks, parks, Morningside Heights boundary, raster, 2D Contours and 3D Contours files.
![image](images/t4-01.JPG)
![image](images/t4-02.JPG)

3. Check the `coordinate system` of the map by going to `View` > `Scene Properties`, also in the main toolbar and switching to the `Coordinate System` tab. This should be set to the standard NYC coordinate system, which is `Projected Coordinate System` > `State Plane` > `NAD 1983 (2011) (US Feet)` > `NAD 1983 (2011) StatePlane New York Long Isl FIPS 3014 (US Feet)`, change it if it is not already so. 
If you ever have issues with weird heights for features, definitely check that the data frame is in the correct coordinate system. Note also that the Linear Unit is in feet.
![image](images/t4-03.JPG)
![image](images/t4-04.JPG)

4. Explore the layers on the screen by panning around and notice that one of the contour files is 3D while the other is not. Also note that the raster, buildings, sidewalks and parks are below the 3D contour layer as they have different Z-axes.
![image](images/t4-05.JPG)

If there was no 3D contour layer available, we could visualize the 2D one 3-dimensionally by changing the base heights to its contour field. 
5. Right-click on the layer name in the `Table of Contents` and select `Properties`. In the `Layer Properties` dialogue box that appears, go to the `Base Heights` tab. 
![image](images/t4-06.JPG)

6. Select `Use a constant value or expression` under the `Elevation from features` section. 
7. Then click on the calculator beside it to open up the `Expression Builder`. 
8. Double click `CONTOUR` and hit OK to select that as the expression for the elevation. 
![image](images/t4-07.JPG)

9. Hit OK to exit layer properties, and observe that the 2D contour file is now being displayed 3-dimensionally. It might be a good idea to turn off or remove the 3D contour layer at this point. 
![image](images/t4-08.JPG)

Next, we will visualize the elevation raster in 3D by changing its `Base Height` to itself. 
10. Go into its `Layer Properties` and to the `Base Heights` tab. 
11. Select `Floating on a custom surface` in the section called `Elevation from surfaces`. 
This is automatically set to the rasterm but the drop down and folder buttons are available to change this if need be. This indicates that the values already associated with the raster's pixels are the values you'd like to use for their heights. If you would like to exaggerate or minimize the new base heights, or perform a meters-feet or feet-meters conversion, you can do so by applying a `Z Unit Conversion`. The value you type will be multiplied by the value of each pixel. 
12. Leave the default Z-unit, `1`. Click ok.
If there was no elevation raster available, you could create one from the contour lines by using the following tool: `Spatial Analyst` > `Interpolation` > `Topo to Raster`.  
![image](images/t4-09.JPG)

The result should be the original raster image visualized 3-dimensionally, with a topography corresponding to the values of the data layer's pixels. 
![image](images/t4-10.JPG)

Other than the contour lines, the vector layers are beneath this 3D raster. To fix this, we will drape them over the raster by changing their base heights to the raster.
13. It is the same process of going to `Layer Properties` then the `Base Heights` tab and selecting `Floating on a custom surface` in the section called `Elevation from surfaces`. This should be set to the raster. Do this for the buildings, sidewalks, parks and Morningside Heights boundary.
![image](images/t4-11.JPG)

Finally, we will extrude the buildings to make them 3D. 
14. Right-click on the layer name and select `Properties`. Go to the `Extrusions` tab, and check the option to `Extrude features in layer`. We will apply the extrusion by adding it to the feature's minumum height. Note that other options are available.
![image](images/t4-12.JPG)

15. Click the calculator button (on the right) to select or calculate your extrusion heights. The `fields` box on the left contains the data fields associated with this layer. You can extrude your layer based on any of these fields by clicking its name in the `fields` box. Set this to `heightroof`. When you are finished building your expression, click OK. You can always go into the layer's `attribute table` to figure out what fields are present.  
![image](images/t4-13.JPG)

16. To export the scene in a format compatible with Rhino and other programs, go to `File` > `Export Scene` > `3D`. 
17. Save your file (the only option is `VRML` format). Depending on how big your file is, this might take some time.
![image](images/t4-14.JPG)

Note: It is recommended that you only export one layer at a time, particularly when exporting topography or buildings. It is also good practice to make a selection of the area you wish to model before exporting, so you will not export large amounts of unnecessary data.
