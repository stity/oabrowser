# threejs-atlas-viewer
This repository hosts the files for an atlas viewer application.

This is not a standalone application. You need to provide an atlas structure JSON file in the config.js file.
To achieve that you can first run the mrmlToJson script which you will find [here](https://github.com/stity/mrmlToJson).

If you are using any of these repositories :
* [spl-brain-atlas](https://github.com/stity/spl-brain-atlas)
* [spl-knee-atlas](https://github.com/stity/spl-knee-atlas)
* [spl-abdominal-atlas](https://github.com/stity/spl-abdominal-atlas)
You need to run the mrmlToJson module first.

###Demos
####Lastest
[https://stity.github.io/spl-brain-atlas/utils/three](https://stity.github.io/spl-brain-atlas/utils/three)
####Stable
[https://stity.github.io/atlas-releases/](https://stity.github.io/atlas-releases)

###To install the viewer locally :
* go in atlas repository
* add this repository as submodule with `git submodule add https://github.com/stity/threejs-atlas-viewer <path-to-submodule-directory>`
* run `bower install` in the new directory
* copy `configAtlasViewer.js` in the parent directory of the submodule (it allows git to commit the changes you make to this config file)
* fill `configAtlasViewer.js` with your own parameters
* run a server at the root of your initial repository.If can use http-server NPM package :
    * `npm install -g http-server` 
    * `http-server`
* now you can open your browser and enjoy the viewer (if you used `http-server` command, the URL will be [http://localhost:8080/path-to-submodule](http://localhost:8080/path-to-submodule))

###To build the release files (dist directory) :
* run `npm install -g gulp-cli` to install gulp
* run `npm install --dev` to install the dev dependencies
* run `gulp` or `npm build`

###Working with service workers :
A Service Worker is registred to enhance user experience by providing offline support but as it uses cache for everything, you will need to follow these steps (with Google Chrome) in case you change your local files.
* open developer tools
* check that the checkbox "disable cache" in the network panel is checked
* long push on the refresh button
* "Empty Cache and Hard Reload"