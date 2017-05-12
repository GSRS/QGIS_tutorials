## Adding in Images - that do not have a map projection
Often we run into images that we would like to use in our GIS project, but which have not been prepared for a GIS (e.g. the file is not in a compatible format or missing map projection within the labels). This method can even be used in a pinch to help load a figure grabbed from a journal article or web site.
For these exercises, we will need to install GDAL binaries. GDAL is used for format conversion and a general library for many applications. 
To help define map projections we use some codes from http://spatialreference.org/ . Just type “Mars” on that page. You can no skip through some common Mars map projections. (e.g. IAU2000 49900).
1. Once gdal is install, on your command-line type:
    ```
    > gdalsrsinfo http://spatialreference.org/ref/iau2000/49900/
    ```
2. For a test image, download a part of a Mars shaded relief from Arizona State University.
    ```
    > wget http://www.mars.asu.edu/data/mola_color/large/mola_color_N00_210.png
    ```
    If you don’t have wget, just download from a browser.
3. Defining a projection for this file:
    ```
    > gdal_translate -a_srs "http://spatialreference.org/ref/iau2000/49900/" -a_ullr -150 30 -120 0 mola_color_N00_210.png mola_color_N00_210.tif
    ```
    * -a_srs = input map projection
    * -a_ullr is the “ul” upper left corner coordinates and the “lr” lower right corner coordinates. Which is
        * “ul” = min_long max_lat (min_X, max_Y in meters)
        * “lr” = max_long min_lat (max_X, min_Y in meters)
    * Input_image.png
    * output_image.tif (without using an output format flag it will default to a GeoTiff , *.tif)

Load the converted Tiff into Qgis. Note we are using degrees for the file. In addition, the cellsize (in degrees/pixel) will be set by gdal_translate from the range lon range and lat range and number of samples and lines respectively. To use this command to generate a file in map projected meters would be a bit tougher since we would need to know the boundaries of the “ullr” in X, Y Cartesian meters.
4. Download a global Mars example
```
> wget https://www.mars.asu.edu/data/mola_roughness/mola_roughness.png
```
```
> gdal_translate -a_srs "http://spatialreference.org/ref/iau2000/49900/" -a_ullr -180 90 180 -90 mola_roughness.png mola_roughness.tif
```
![Ungeoreferenced rasters](/images/noproj.jpg)
