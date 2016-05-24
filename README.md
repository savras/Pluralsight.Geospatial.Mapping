# Pluralsight.Geospatial.Mapping
Geospatial mapping tutorial from Pluralsight for Australia

# Resources
* GDAL - http://www.gdal.org/
* How to install GDAL - http://sandbox.idre.ucla.edu/sandbox/tutorials/installing-gdal-for-windows
* Shapefile for Australia - http://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1259.0.30.001July%202011?OpenDocument

# Useful commands
Convert Shapefile to GeoJSON: ogr2ogr -f GeoJSON districts.json resources/STE11aAust.shp
If the above doesn't work, go here: https://ogre.adc4gis.com/. 
The above works for me. Extract all contents of the ESRI Shape file to the same folder for ogr2ogr to process.