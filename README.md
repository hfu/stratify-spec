# stratify-spec
The specification for stratify.js, the code for creating a [vector-tile-spec](https://github.com/mapbox/vector-tile-spec/) tile from a GeoJSON tile

## background
To convert a GeoJSON tile to a vector-tile-spec tile, we need to specify layers respective features belongs to. 

For this process is dependent on the data schema, this specification defines a convension to inject such process.

I got this idea while developing [binarian](https://github.com/hfu/binarian/).

## basics
stratify.js provides a function that returns the first paramenter of [vtpbf](https://github.com/mapbox/vt-pbf).fromGeojsonVt() taking a GeoJSON of a tile. 

The first parameter of vtpbf.fromGeojsonVt() is [an object mapping layer names to geojson-vt-created vector tile objects](https://github.com/mapbox/vt-pbf/blob/master/index.js#L24).

## use example
```node
const modify = require('./stratify.js')
/// ...
  vtpbf.fromGeojsonVt(stratify(geojson))
/// ...
```

## define example
```node
// stratify.js
module.exports = geojson => {
  return {default: geojson}
}
```

## actual use of this specifications
todo
