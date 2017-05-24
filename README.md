# mapboxgl-d3-playground

Some examples on how to combine [Mapbox GL JS](https://www.mapbox.com/mapbox-gl-js/api/) and [d3.js](https://d3js.org/) for creating interactive geovisualizations.


## When you should use D3 with Mapbox GL JS

- If you want to keep your code clean: mapbox for map rendering, d3 for data handling and data visualization, CSS for styling.
- If you want to animate or transform your geovisualization easily without struggling with Mapbox's interminable data structures
- If you want to transition between the map and other views (small multiples, schematic data representations, etc.)

## Limitations

Using points is not a big deal. But rendering large or complex shapes with d3 will slow down your map transitions when zooming, panning, etc. (for each map update event, the map has to reproject all shape coordinates to the new map state). Some workarounds are:

- Simplify the shapes before rendering them with tools like [mapshaper](http://mapshaper.org/) or libs like [turf.js](http://turfjs.org/)
- Hide the d3 shapes on map move, so as they don't have to be updated for each "map move". On release, update the shapes to the current map state, and show them again (example coming soon).
– If you work with huge vector or raster data, consider using map tiles instead of d3.


## Demos

1. [Native Mapbox GL JS point mapping](http://dev.jorditost.com/mapboxgl-d3-playground/01-mapbox-points.html)
2. [Simple Mapbox GL JS - d3 connection with d3 point mapping (without updates)](http://dev.jorditost.com/mapboxgl-d3-playground/02-mapbox-d3-points.html)
3. [d3 mapping with map and point interaction](http://dev.jorditost.com/mapboxgl-d3-playground/01-mapbox-points.html)
4. [d3 shape/polygon mapping](http://dev.jorditost.com/mapboxgl-d3-playground/04-mapbox-d3-shapes.html)
5. [Toggling and transitioning between map and non-map views](http://dev.jorditost.com/mapboxgl-d3-playground/05-toggle-views.html)
