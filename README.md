# objTo3d-tiles
Node command line tool convert obj model file to 3D Tiles, based on [obj2gltf](https://github.com/AnalyticalGraphicsInc/obj2gltf).

[Online Demonstration](https://princessgod.github.io/plc/batchedTileset.html)

>NOTE: Only support `.b3dm` for now!

## Getting Start
Clone this repository to local.

```
git clone https://github.com/PrincessGod/objTo3d-tiles.git
```

Navigate in the repository folder.

```
cd objTo3d-tiles
```

Make sure you have [Node](https://nodejs.org/en/) installed, and then

```
npm install
```

### Basic Usage

* Convert `.obj` to `.gltf`

```
node ./bin/obj23dtiles.js -i ./bin/barrel/barrel.obj  // Export barrel.gltf at same folder.
```

* Convert `.obj` to `.glb`

```
node ./bin/obj23dtiles.js -i ./bin/barrel/barrel.obj -b  // Export barrel.glb at same folder.
```

>NOTE: More detial to convert `.gltf` and `.glb` can find at [obj2gltf](https://github.com/AnalyticalGraphicsInc/obj2gltf).

* Convert `.obj` to `.b3dm` with default batch table, which have `batchId` and `name` property, and `name` is model's name.

```
node ./bin/obj23dtiles.js -i ./bin/barrel/barrel.obj --b3dm  // Export barrel.b3dm at same folder.
```

* Convert `.obj` to `.b3dm` with default batch table and export default batch table (a JSON file). Maybe get information for custom batch table.

```
node ./bin/obj23dtiles.js -i ./bin/barrel/barrel.obj --b3dm --outputBatchTable  // Export barrel.b3dm and barrel_batchTable.json at same folder.
```

* Convert `.obj` to `.b3dm` with custom batch table.

```
node ./bin/obj23dtiles.js -i ./bin/barrel/barrel.obj -c ./bin/barrel/customBatchTbale.json --b3dm // Export barrel.b3dm with custom batch table at same folder.
```

## Sample Data
Sample data under the `.bin\barrel\` folder. 

```
barrel\
    |
    - barrel.blend              --
    |                             |- Blender project file with texture.
    - barrel.png                --
    |
    - barrel.obj                --
    |                             |- Obj model files.
    - barrel.mtl                --
    |
    - customBatchTable.json     ---- Custom batchtable used in demonstration.
    |
    - output\                   ---- Export data by using upper files.
        |
        - barrel.glb
        |
        - barrel.gltf
        |
        - barrel_batchTable.json    ---- Default batch table.
        |
        - BatchedTilesets\          ---- Tileset with custom tileset.json
            |
            - tileset.json
            |
            - barrel_withDefaultBatchTable.b3dm
            |
            - barrel_withCustonBatchTable.b3dm
```

## Resources
* Online glTF viewer, make sure your glTF is correct.[Cesium](https://www.virtualgis.io/gltfviewer/),[Three.js](https://gltf-viewer.donmccurdy.com/).
* [Cesium](https://github.com/AnalyticalGraphicsInc/cesium).
* [3D Tiles](https://github.com/AnalyticalGraphicsInc/3d-tiles).
* [glTF](https://github.com/KhronosGroup/glTF)

## Credits
Great thanks to Sean Lilley([@lilleyse](https://github.com/lilleyse)) for helping and advising.

Thanks [AnalyticalGraphicsInc](https://github.com/AnalyticalGraphicsInc) provide a lot of open source project (like [Cesium](https://github.com/AnalyticalGraphicsInc/cesium) and [3D Tiles](https://github.com/AnalyticalGraphicsInc/3d-tiles)) and creat a great GIS environment.

## License
[Apache License 2.0](https://github.com/PrincessGod/objTo3d-tiles/blob/master/LICENSE)
