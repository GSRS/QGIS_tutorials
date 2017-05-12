## QGIS - 3D Views
In a new QGIS project, under Plug-ins, Manage…, search for “3D”. Turn on the “Qgis2threejs” plug-in. From this site: http://hrscview.fu-berlin.de/cgi-bin/ion-p?page=product2.ion&code=&image=0360_0000 download DEM: H0360_0000_DA4.IMG.
```
> wget ftp://psa.esac.esa.int/pub/mirror/MARS-EXPRESS/HRSC/MEX-M-HRSC-5-REFDR-DTM-V1.0/DATA/0360/H0360_0000_DA4.IMG
```
With a DEM loaded into QGIS, zoom into an area such that all the display area is covered by data. Check the projection in the lower-right. It should be set to “USER”. This is imporatant since the X,Y Cartesian system will be in meters which matches the elevation pixel values. This allows the routine to more easily set the exxageration. Now click the Qgis2threejs icon. Test using settings below.
![3D plugin](/QGIS_introduction_and_planetary_data/images/3dview1.jpg)
![3D plugin](/QGIS_introduction_and_planetary_data/images/3dview2.jpg)
Note this is a simple webpage that can be easily hosted online. This tool will never render the surface as well as tools like Blender but it is quick and simple. If you have an image loaded, it will us that for the texture also. In the web interface, play with custom plane. It will let you add-in flat plane which can move up and down in elevation (to show a water body to constant height across a mountain.
3D resources: http://planetarygis.blogspot.com/2017/03/dem-raster-to-3d-ply-format.html
### Goals for DEMs
* Create contours and label them
* Create a hillshade from a DEM.
* Colorize the DEM using the style tab under the layer’s properties
* Create a 3D model for printing (see experimental plug-ins).
