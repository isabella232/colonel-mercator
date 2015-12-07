# colonel-mercator
Gets raster pixel resolutions, and optionally snaps them to `mapnik-omnivore` tiling thresholds.
Also, generates "metatile" zooms - the tile sizes at which a given input resolution would be over a size threshold based on an "upzoom" (the resolution of zoom levels "up")

![colonel](https://cloud.githubusercontent.com/assets/5084513/11637742/fff760d8-9cd7-11e5-94c9-b0d4ed113a55.jpeg)

## Install
```
npm install colonel-mercator
npm link
```

## Usage - resolution
```
colonel-mercator resolution <raster> --maxres <float> --snap
```
### Arguments
`<raster> [path]`: an input `tiff` to get the resolution of

### Options
`--maxres [float]`: the floor at which to set resolution; if `maxres` > the file's resolution, returns `maxres`. `[DEFAULT=NONE]`
`--snap [flag]`: snap to mercator tiling thresholds `[BETA]` `[DEFAULT=FALSE]`

## Usage - metatile
```
colonel-mercator metatile <resolution> --zoombreaks '[<int>, <int>, ...]' --upzoom <int>
```

### Arguments
`<resolution> [float]`: the resolution to evaluate

### Options
`--zoombreaks [array of ints]`: the metatile sizes to create `[DEFAULT=[13, 10, 7, 4]]`

`--upzoom [int]`: the number of zoom levels up at which to derive threshold from zoombreaks

