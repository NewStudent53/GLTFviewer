# threejs-viewer
A repo to quickly display any model (fbx & gltf format with compression) using Three.js.
- GLTF supports gltf-pack, gltf-pipeline and Blender exports.
- gltf-pack compression uses vertex quantisation, gltf-pipeline uses DRACO compression

### Installation
1. Clone the repo.
2. Run `npm install` to install all the dependencies
3. Use `npm run dev` to compile the project in development mode
4. Use `npm run build` to compile the project in production mode
5. Open `index.html` using Live Server

## Notes
- index.html - Display the FBX model (by default) on the full page.
  - Source files:
    - app.js - (default script) Displays FBX Model
    - app2.js - Displays GLTF Model
    - app.scss
  - Output files: _Generated by Webpack after you compile the project_
    - bundle.js
    - main.css
  - Everything is written inside an exportable class named `Sketch` so it can be easily imported using ES6+ syntax.
  - **To view GLTF model**, change `entry` in `webpack.config.js` to `app2.js` and then compile the project using `npm run dev`.
  - In case your model is compressed with Blender or gltf-pipeline, DRACO compression is applied over the model so make sure you include the `draco-files` folder in your project.
  - In case your model is compressed with gltf-pack, it uses mesh quantisation to compress the model so make sure you correctly import the MeshoptDecoder from three module.
  - All animations are played by default if provided in the GLTF.
  - The model is displayed in MeshNormalMaterial, so in case normals are not provided, the model will be solid black.
