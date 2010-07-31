This project allows a user to load Shapefiles and DBFs into the browser with JavaScript.
Outputs as [GeoJSON](http://geojson.org/) for use with other Mapping APIs such as [OpenLayers](http://openlayers.org).

Inspired by the excellent work by Tom Carden ([http://github.com/RandomEtc/shapefile-js/](http://github.com/RandomEtc/shapefile-js/)).

### Overview

I just got this out there so nothing is minified.  See index.html for an example of order.  All files need to be in the same directory.  This will use Web Workers if the browser support exists.  Not recommended for large files, more of an experiment than anything.

### Usage

You can use it to parse shapefiles (.shp) or dBase files (.dbf) or both.  Here are some examples.

Load Shapefile Only

    var shapefile = new Shapefile("myshapefile.shp",function(data){
        // data returned
    };

Load DBF Only

    var dbf = new DBF("mydbf.dbf",function(data){
        // data returned
    };

Load Shapefile w/ DBF Attributes

    var shapefile = new Shapefile({
        shp: "myshape.dbf",
        dbf: "myshape.dbf"
    }, function(data){
        // data returned
    };

Use with OpenLayers

    var
        parser = new OpenLayer.Format.GeoJSON(),
        features,
        shapefile = new Shapefile({
            shp: "myshape.dbf",
            dbf: "myshape.dbf"
        }, function(data){
            features = parser.read(data.geojson);
        };

### Resources

I used the technical descriptions found here to parse the binary:

> [ESRI Shapefile Technical Description - PDF](http://www.esri.com/library/whitepapers/pdfs/shapefile.pdf)

> [dBase (Xbase) File Format Description](http://www.dbf2002.com/dbf-file-format.html)

### Future

I plan to implement (time permitting) some custom renderers like SVG or Canvas (besides using OpenLayers) to improve the speed.

Feel free to hack at this, submit bugs, pull requests, and make it better.  If you write a renderer, please push it back and I'll add it to the project.

