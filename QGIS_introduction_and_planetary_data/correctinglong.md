## Correcting 360 Longitude Layers: nomenclature
If you happened to set a Mars map projection in QGIS (e.g. Mars Sinusoidal), you might notice that half the data disappears. This is because the nomenclature shapefiles us a 0 – 360 longitude system. While many GIS applications support this, QGIS unfortunately has issues (as do applications like Google Earth).
What to do… 
1. One option is to download the Google Earth compatible nomenclature file, which has been converted to a -180 to 180 longitude coordinate system. This would simply be to download the *.kmz (compress Keyhole mark-up language format used by Google Earth). The main issue with this format is that KML does not offer a good method to define the map projection. Thus the files, once loaded, will need to be assigned a map projection (e.g. IAU2000:49900 Mars degrees).
2. Let us also fix the download shapefile to use a -180 to 180 longitude system. This will teach us methods to create new table fields, select features, and calculate new values. Lastly, it will teach us to load a CSV table file into QGIS.
    1. First right click on the nomenclature shapefile and click “save as...”. In the next interface set CSV and set a new output file name. Let the CRS and other options default. Hit OK.
    ![Correcting 360 Longitude layers](/QGIS_introduction_and_planetary_data/images/corrlong0.jpg)
    2. Once exported, by default the CSV table will be loaded into QGIS. Right click on it and “Open Attribute Table”. This will bring up the next dialog. We need to set table to edit mode (using the far left pencil icon) . Now on the right side of the button list, click “Open Field Calculator”. Type in the field name of lon180 set as “decimal number (length = 10, precision = 4). See image below. Under the expression window type “center_lon”. You can click on the field name under “Fields and Value” in the center of the window.
    ![Correcting 360 Longitude layers](/QGIS_introduction_and_planetary_data/images/corrlong1.jpg)
    3. Now to fix the values above 180.0 degrees, first select all lon180 > 180 using the “Select by Expression” button (about center of the table buttons). We want to select all values above 180 using “lon180” > 180 in the Expression window and the hit “Select” button.
    ![Correcting 360 Longitude layers](/QGIS_introduction_and_planetary_data/images/corrlong2.jpg)
    4. In the table listing, you should find that about 1100 features of 1800 features are now selected. Let us use the “Open Field Calculator” and set “center_lon – 360” but this only using “Update existing field” using the field “lon180. See below.
    ![Correcting 360 Longitude layers](/QGIS_introduction_and_planetary_data/images/corrlong3.jpg)
    5. With the field updated, make sure to hit the “save edits” button  and then toggle off editing (pencil icon)
3. Next let us load in the updated CSV file by hitting the “add CSV layer”  .  In the next dialog, set the options below checking “CSV”, “First record has field names”, and change X field to “lon180” and Y field “center_lat”.
![Correcting 360 Longitude layers](/QGIS_introduction_and_planetary_data/images/corrlong4.jpg)
    1. When you hit “OK”, it will now pop-up the coordinate system dialog. Here is where we set the target body. In more recent versions of QGIS many of them are available within QGIS. Here you can search for “Mars” or other body for your data you are importing.
    ![Correcting 360 Longitude layers](/QGIS_introduction_and_planetary_data/images/corrlong5.jpg)
4. This nicely adds your layer to QGIS and it should be in the correct -180 to 180 longitude range. However, you will notice it does not ask for an output file name. To save this virtual layer to a file, right click and “save as…” again. This time change to “Esri Shapefile” as the output format. While we already set “Mars 2000”, it did not seem to take. Make sure to set it again for export. Fortunately, it will remember the projection once an Esri shapefile.
![Correcting 360 Longitude layers](/QGIS_introduction_and_planetary_data/images/corrlong6.jpg)
![Correcting 360 Longitude layers](/QGIS_introduction_and_planetary_data/images/corrlong7.jpg)
