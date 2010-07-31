This project allows a user to load Shapefiles and DBFs into the browser with JavaScript.
Outputs as [GeoJSON](http://geojson.org/) for use with other Mapping APIs such as [OpenLayers](http://openlayers.org).

Inspired by the excellent work by Tom Carden ([http://github.com/RandomEtc/shapefile-js/](http://github.com/RandomEtc/shapefile-js/)).

### Usage

I just got this out there so nothing is minified.  See index.html for an example of order.  All files need to be in the same directory.  This will use Web Workers if the browser support otherwise.  Not recommended for large files, more of an experiment than anything.

### Usage

You can use it to parse shapefiles (.shp) or dBase files (.dbf) or both.  Here are some examples.

Load Shapefile Only

> var shapefile = new Shapefile("myshapefile.shp",function(data){
>     // data returned
> }

Load DBF Only

> var dbf = new DBF("mydbf.dbf",function(data){
>     // data returned
> }

Load Shapefile w/ DBF Attributes

> var shapefile = new Shapfile({
>     shp: "myshape.dbf",
>     dbf: "myshape.dbf"
> }, function(data){
>     // data returned
> }