---
project: VectorMap-js
stars: 20
description: HTML5, WebGL Vector Map JavaScript library with any vector data – EsriJSON, GML, GPX, GeoJSON, KML, Vector Tile (MVT), WFS, WKT or WMS, can be beautifully rendered with CSS similar style file – StyleSJON schema. It’s an extension of OpenLayers, and fits any requirements in browsers and mobile devices. 
url: https://github.com/ThinkGeo/VectorMap-js
---

VectorMap.js
============

HTML5, WebGL Vector map JavaScript library with any vector data – EsriJSON, GML, GPX, GeoJSON, KML, Vector Tile (MVT), WFS, WKT or WMS, can be beautifully rendered with CSS similar style file – StyleJSON schema. It’s an extension of OpenLayers, and fits any requirements in browsers and mobile devices.

With Map Suite VectorMap.js, you will have full access to OpenLayers, as well as any plugins or extensions created based on OpenLayers, for example, the "3rd party libraries" published on https://openlayers.org. With the help of them, you can easily create any styled map and put it anywhere, and build a customized geocoding or routings from other providers.

Documentation:
--------------

-   Getting Started
-   Community & Support
-   API Documentation
-   Vector StyleJSON Specification
-   World Streets Vector Tile Schema
-   Wolrd Street Styles Predefined

Examples - View It Online:
--------------------------

Install
-------

> The official guide assumes intermediate level knowledge of HTML, CSS, and JavaScript, and have some experience of any front-end development editor, such as Visual Studio Code, Webstorm, Sublime Text or some similars. if you are totally new to frontend development, the easiest way to try out this library which is the "Hello World" example on CodePen. Feel free to open it in another tab and follow along as we go through some features.

### CDN

Load from CDN in your project:

<!-- style sheet for vectormap.js -->
<link rel\="stylesheet" href\="https://cdn.thinkgeo.com/vectormap-js/3.0.0/vectormap.css"\></link\>
	
<!-- latest minified version of vectormap.js -->
<script src\="https://cdn.thinkgeo.com/vectormap-js/3.0.0/vectormap.js"\></script\>

### NPM

-   Install the package:

```
npm i vectormap-js
```

Development Version

```
npm i vectormap-js-dev
```

-   Include it to your page:

<!-- style sheet for vectormap.js -->
<link rel\="stylesheet" href\="path/to/dist/vectormap.css"\></link\>
	
<!-- latest minified version of vectormap.js -->
<script src\="path/to/dist/vectormap.js"\></script\>

How to use
----------

Set up a basic map with VectorMap.js in 6 steps (here take Visual Studio Code for example).

**Step 1**. Create a html page with name "index.html "

**Step 2**. In the `<head>`of your HTML page, import the vectormap.js and related css file.

<!-- style sheet for vectormap.js -->
<link rel\="stylesheet" href\="https://cdn.thinkgeo.com/vectormap-js/3.0.0/vectormap.css"\></link\>
	
<!-- latest minified version of vectormap.js -->
<script src\="https://cdn.thinkgeo.com/vectormap-js/3.0.0/vectormap.js"\></script\>

**Step 3**. In the `<body>` of your HTML page, add a div with "id=`"map"`".

<div id\="map" style\="width:800px;height:600px;"\></div\>

**Step 4**. At the bottom of the html page, add a JavaScript section to create an instance of map control with one vector layer created.

<script\>
    var worldstreetsStyle = "https://cdn.thinkgeo.com/worldstreets-styles/3.0.0/light.json";    
    var worldstreets = new ol.mapsuite.VectorTileLayer(worldstreetsStyle, 
        {
            apiKey:'your-ThinkGeo-Cloud-Service-key'
        });
    let map =  new ol.Map({                         
        layers: \[worldstreets\],
        target: 'map',
        view: new ol.View({
            center: ol.proj.fromLonLat(\[\-96.79620, 32.79423\]),
            zoom: 4,
        }),
	renderer: 'webgl'
    });
</script\>

**NOTE:**

-   **ThinkGeo Cloud Service key**

Access to ThinkGeo Cloud services, including Vector Tile data, requires an `API Key` that connects API requests to your account, Please check here on how to create your own `ThinkGeo Cloud Service key` **FOR FREE**.

-   World Streets Styles

`World Streets Style` is a syntax of map styling language, similar to CSS. It's define the styles of your vector data. `Map Suite World Streets Styles` is professionally designed map styles from ThinkGeo experts, you can use it in your application without any changes, if you are consuming the Vector Tile data from ThinkGeo Cloud Service.

**Step 5 (Option)**. If `Map Suite World Streets Styles` is referenced in your demo, please load **ThinkGeo Map Icons** as an requirement, as all icons are drawn with. Once the Icon Fonts have been completely downloaded, the `initMapFuntion` will be called to init map.

```
<script src="https://cdn.thinkgeo.com/vectormap-icons/3.0.0/webfontloader.js"></script>
<script>
    WebFont.load({
        custom: {
            families: ["vectormap-icons"],
            urls: ["https://cdn.thinkgeo.com/vectormap-icons/3.0.0/vectormap-icons.css"]
        },
        active: initMapFuntion
    });
</script>
```

After all the above steps completed, your HTML page should be:

<!DOCTYPE html\>
<html\>
    <head\>
        <title\>Vector World Map</title\>
        <meta charset\="utf-8"\>
        <meta name\="viewport" content\="width=device-width, initial-scale=1"\>
        <!-- style sheet for vectormap.js -->
        <link rel\="stylesheet" href\="https://cdn.thinkgeo.com/vectormap-js/3.0.0/vectormap.css"\></link\>
        
        <!-- latest minified version of vectormap.js -->
       <script src\="https://cdn.thinkgeo.com/vectormap-js/3.0.0/vectormap.js"\></script\>

        <!-- option: Map Suite World Streets Styles -->
        <script src\="https://cdn.thinkgeo.com/vectormap-icons/3.0.0/webfontloader.js"\></script\>
        <script\>
            WebFont.load({
                custom: {
                    families: \["vectormap-icons"\],
                    urls: \["https://cdn.thinkgeo.com/vectormap-icons/3.0.0/vectormap-icons.css"\]
                }
            });
        </script\>
    </head\>
    <body\>
        <div id\="map" style\="width:800px;height:600px;"\></div\>
        <script\>
            var worldstreetsStyle \= "https://cdn.thinkgeo.com/worldstreets-styles/3.0.0/light.json";    
            var worldstreets \= new ol.mapsuite.VectorTileLayer(worldstreetsStyle, 
            {
                apiKey:'your-ThinkGeo-Cloud-Service-key'      // please go to https://cloud.thinkgeo.com to create
            });
            let map \=  new ol.Map({                        
                layers: \[worldstreets\],
                target: 'map',
                view: new ol.View({
                    center: ol.proj.fromLonLat(\[\-96.79620, 32.79423\]),
                    zoom: 4,
                }),
		renderer: 'webgl'
            });
        </script\>
    </body\>
</html\>

**Step 6**. Run the page and a beautiful map is there.

ThinkGeo Map Icons
------------------

**ThinkGeo Map Icons** is a pack of more than 200 beautifully crafted Open Source icons for common mapping.

Vector Data Supported
---------------------

Besides loading the traditional KML, GeoJSON, bitmap tiles etc., **`VectorMap.js`** can work with Vector Tiles.

Map Suite Cloud Service provides a free vector tile service (\*.mvt) based on open data from OpenStreetMap, Natural Earth and some other data providers, with global coverage updated continuously. - sign up for an API Key for free.

Styling
-------

Map Suite vector styling schema - Vector StyleJSON is designed for you to specify data sources, layers and how to define and apply styles to layers. Please check the demo from "Predefined open source styles" or check related documentation at https://thinkgeo.gitbooks.io/map-suite-stylejson-specification/content/.

Browser Support
---------------

**VectorMap.js** is officially supported and tested on the last two versions of these browsers:

-   **Mac OS**: Chrome, Firefox, and Safari
-   **Windows**: Chrome, Firefox, IE11, and IE Edge
-   **iOS**: Safari, Chrome, Firefox
-   **Android**: Chrome

**VectorMap.js** should also run in any brower with HTML5 support.

License
-------

**VectorMap.js** is licensed under the Apache 2.0.
