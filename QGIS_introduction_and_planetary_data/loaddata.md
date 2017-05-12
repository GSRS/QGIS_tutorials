## Planetary Nomenclature: load some data
You will find maybe GIS-ready data sets from the planetary community and PDS holdings. The IAU sponsored Gazetteer for Planetary Nomenclature is one such site.
1. Download the Planetary names for Mars (in GIS shapefile format). The filename is MARS_nomenclature.zip -- https://planetarynames.wr.usgs.gov/GIS_Downloads
2. Once downloaded, use the browser window or “add vector” icon   (and browse to the file), you will notice QGIS can load the “zip” shapefile without extracting all the individual files. This is really more of a convenience feature but a nice touch.
3. Notice when using a QGIS project the projection is automatically set to the first layer added – in our case IAU2000:49900 (Mars in degrees). For more on these code see: http://bit.ly/IAU2000
![Loading Planetary Nomenclature](/QGIS_introduction_and_planetary_data/images/nomenc.jpg)
