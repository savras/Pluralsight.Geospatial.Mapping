# Pluralsight.Geospatial.Mapping
Geospatial mapping tutorial from Pluralsight for Australia

# Resources
* GDAL - http://www.gdal.org/
* How to install GDAL - http://sandbox.idre.ucla.edu/sandbox/tutorials/installing-gdal-for-windows
* Shapefile for Australia - http://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1259.0.30.001July%202011?OpenDocument
* Another Shapefil source - https://www.flickr.com/places/info/2344706

# Useful commands
* Convert Shapefile to GeoJSON: ogr2ogr -f GeoJSON aus.json resources/STE11aAust.shp
The above works for me. Extract all contents of the ESRI Shape file to the same folder for ogr2ogr to process. Start ogr2ogr from the installation folder
F:\Program Files\GDAL\bin\gdal. 
Add the location F:\Program Files\GDAL\bin\; to the System Path environment variable. 
If it doesn't work, go here: http://www.mapshaper.org/.

* Clipping Shapefile to W.A. : ogr2ogr -f GeoJSON aus-clipped.json 1259030001_ste11aaust_shape/STE11aAust.shp -clipsrc 112.9211, -35.1348, 129.0019, -13.6895
Bounding box values gotten from https://www.flickr.com/places/info/2344706

* Filtering Shapefile to W.A. : ogr2ogr -f GeoJSON aus-filtered.json 1259030001_ste11aaust_shape/STE11aAust.shp -where "STATE_CODE='5'"

* Adding D3 projection: topojson -o topo-aus-projected.json --projection='width = 960, height = 600, d3.geo.albersUsa() .scale(1280) .translated([width / 2, height / 2])' wa.json
More info: http://enjalot.github.io/intro-d3/maptime/geo/
Projections : https://github.com/d3/d3/wiki/Geo-Projections