## Ignoring regions of data 
#### How the polygon .shp files where made
1. Use NWS GIS Viewer Query Tool to create polygon shapes of desired regions.
    - Query > create polygon > draw verticies > display WKT
    - An alternative would’ve been to use ArcGIS or some other GIS tool but the NWS GIS actually runs on Esri’s ArcGIS platform and is usable in the browser.
https://viewer.weather.noaa.gov/general#layers=1+40090+41706+41705+41704+41703+41701+41702+41698&x=19.24415&y=39.95575&z=4&panel=query

2. Copy WKT ( in EPSG 4326 / WGS 84) for each polygon and save them to file “WKT_polygons.txt”

3. Polygons_from_txt function creates list of shapely.geometry.Polygon objects from WKT text file
    - Shapely is a popular library for manipulating and analyzing geometric objects in Python
    
#### Using the polygon .shp files
4. to_mask function to generates array of Booleans that indicates whether to mask or not for each data point 

## Dependencies: shapely, numpy, xarray
