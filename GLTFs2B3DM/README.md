# GLTFs2B3DM

This is the heavily modified 3D Tiles Samples Generator which converts a group of GLTFs to a B3DM. Changes have been made to account for gltf models with large number of indices, meshes and primitives. The materials as generated with IFC2GLTFs will also be comaptible. The final b3dm contains a batch table hierarchy which includes information from the original ifc files (such as GUID, BATID, BimServer Dimensions and BimServer Constraint) as the properties of each object. This is done using the json (Streaming) export files from BimServer.

Please visit https://github.com/AnalyticalGraphicsInc/3d-tiles-tools/tree/master/samples-generator for the original 3d tiles sample generator code.

## Setup

From the root directory of this repo, run: `npm install`

The output 3D tile will be generated in output\Hierarchy\BatchTableHierarchy\model folder and will include the b3dm and tileset.json.
