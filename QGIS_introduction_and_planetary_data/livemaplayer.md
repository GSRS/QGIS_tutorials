## Adding a WMS (live map layer)
The WMS standard still has some planetary issues (meaning the standard was written for Earth and thus while planetary works we need to trick it sometimes). QGIS support for WMS can also be a little wonky. Do not give up it can work really well. To find many layers see: http://bit.ly/AstroWMS . To see some other resources outside of USGS see: http://bit.ly/PlanetaryGIS .
1. First Copy this WMS get capabilities link: https://planetarymaps.usgs.gov/cgi-bin/mapserv?map=/maps/mars/mars_simp_cyl.map&service=WMS&request=GetCapabilities
You can copy different URL from this page (get capabilities link).
2. Now click on the add WMS button . In the next dialog, click “new”.
![wms](/QGIS_introduction_and_planetary_data/images/wms1.jpg)
3. This will show this next dialog. Type a name and paste in the URL. Hit “OK”.
![wms](/QGIS_introduction_and_planetary_data/images/wms2.jpg)
4. Now select “Connect” and select a single layer (e.g. MOLA_bw) and click Add (only once) and then Close.
![wms](/QGIS_introduction_and_planetary_data/images/wms3.jpg)
![wms](/QGIS_introduction_and_planetary_data/images/wms4.jpg)

### WMS Discussion:
WMS support will need further testing but when a WMS fails you may need to default back to EPSG:4326 (WGS 84) or even start a new QGIS and load it first.
The planetary codes available in QGIS were added from help from Arizona State University. They also support an open source WMS engine called Lunaserv, which also supports theses planetary codes. These codes have been successfully testing in PostGRES and Rasterman and we hope to add support for these code in mapserver and geoserver.
