## More layers for testing
### CTX footprints and images
```
> wget http://ode.rsl.wustl.edu/mars/datafile/derived_products/coverageshapefiles/mars/mro/ctx/edr/mars_mro_ctx_edr_c0a.zip
```
#### Goals for this data set
* Use rendering effects (transparency and multiply) to show density of images. 
* Filter certain types of images that meet a certain criteria (e.g. Phase_angle > 30).
* Set and action to hyperlink the EXTURL2 field. (define an action, and set “open” on this field).
* Download several CTX images (below) and use gdalbuildvrt – to build a virtual mosaic.
* For more GDAL tips see: https://isis.astrogeology.usgs.gov/IsisSupport/index.php?topic=2172.0

    CTX Processing (access to ISIS3 processing): Follow the tutorial for USGS’s Map Projection on the Web (POW). https://astrocloud.wr.usgs.gov/

    Pre-processed CTX Images (by ASU): CTX GeoTiffs found on this stie are GIS-ready. You can find links to these images using EXTURL2 field in the CTX footprints above. 
