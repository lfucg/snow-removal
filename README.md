# Web map to show snow removal priority streets in Lexington, KY

### Filter the features

* Open shapefile in QGIS
* Open attributes table
* Select features using an expression "WHERE snow IS NOT NULL"
* Select all
* Save Selection as new layer
* Save layer as snow-priority-specified.geojson

### Create TopoJSON file from shapefile

[TopoJSON](https://github.com/mbostock/topojson) is an extension of GeoJSON that encodes topology so the dataset loads more quickly over a network.

```
topojson -o snow-plan-specified.topo.json --simplify-proportion .5 --properties snow snow-priority-specified.geojson
```

Big thanks to Chris Doerge and the GIS team at LFUCG for providing the data and helping to understand it.

