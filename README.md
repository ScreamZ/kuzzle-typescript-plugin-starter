# 🚀 A starter kit for kuzzle.io with typescript.

# How does it works ?

This plugin starter use a `src` folder that contain typescript sources.
Typescript file are compiled in the `build` folder which is mounted in the docker instance.

**Note :** Once in the build folder, relative references are resolved from here. Do not put any non-.ts file inside the src folder they won't be copied..

Kuzzle will read for `package.json` `main` property which redirect to `build/index.js`, our compiled code.

## How to use ?
**Requirements :**
- docker-compose
- yarn or npm (any yarn command can be replaced by npm)

### Development mode 

First boot the typescript watcher, then boot docker-compose instance.

1. `yarn install`
2. `yarn run dev` 
3. Then run `docker-compose up`

### Production release

You can use the command `yarn run build`,  this will build a optimized bundle in the build directory.

This starter automatically watch for changes and apply them on your kuzzle instance thanks to PM2 and typescript watch mode.