---
project: nsfwjs
stars: 8616
description: NSFW detection on the client-side via TensorFlow.js
url: https://github.com/infinitered/nsfwjs
---

Client-side indecent content checking
-------------------------------------

A simple JavaScript library to help you quickly identify unseemly images; all in the client's browser. NSFWJS isn't perfect, but it's pretty accurate (~90% with small and ~93% with midsized model)... and it's getting more accurate all the time.

Why would this be useful? Check out the announcement blog post.

NOTE
----

If you're trying to access the Cloudfront hosted model and are running into an error, it's likely due to the fact that the model has been moved to a new location. Please take a look at our Host your own model section. We will be returning the model after some hotlinkers have been dealt with.

**Table of Contents**
---------------------

-   QUICK: How to use the module
-   Library API
    -   `load` the model
    -   Caching
    -   `classify` an image
-   Production
-   Install
    -   Host your own model
-   Run the Examples
    -   Tensorflow.js in the browser
    -   Browserify
    -   React Native
    -   Node JS App
    -   NSFW Filter
-   Learn TensorFlow.js
-   More!
    -   Open Source
    -   Need the experts? Hire Infinite Red for your next project
-   Contributors

The library categorizes image probabilities in the following 5 classes:

-   `Drawing` - safe for work drawings (including anime)
-   `Hentai` - hentai and pornographic drawings
-   `Neutral` - safe for work neutral images
-   `Porn` - pornographic images, sexual acts
-   `Sexy` - sexually explicit images, not pornography

> _The demo is a continuous deployment source - Give it a go: http://nsfwjs.com_

QUICK: How to use the module
----------------------------

With `async/await` support:

import \* as nsfwjs from "nsfwjs";

const img \= document.getElementById("img");

// If you want to host models on your own or use different model from the ones available, see the section "Host your own model".
const model \= await nsfwjs.load();

// Classify the image
const predictions \= await model.classify(img);
console.log("Predictions: ", predictions);

Without `async/await` support:

import \* as nsfwjs from "nsfwjs";

const img \= document.getElementById("img");

// If you want to host models on your own or use different model from the ones available, see the section "Host your own model".
nsfwjs
  .load()
  .then(function (model) {
    // Classify the image
    return model.classify(img);
  })
  .then(function (predictions) {
    console.log("Predictions: ", predictions);
  });

Library API
-----------

### `load` the model

Before you can classify any image, you'll need to load the model.

const model \= nsfwjs.load(); // Default: "MobileNetV2"

You can use the optional first parameter to specify which model you want to use from the three that are bundled together. Defaults to: `"MobileNetV2"`. This supports tree-shaking on supported bundlers like Webpack, so you will only be loading the model you are using.

const model \= nsfwjs.load("MobileNetV2Mid"); // "MobileNetV2" | "MobileNetV2Mid" | "InceptionV3"

You can also use same parameter and load the model from your website/server, as explained in the Host your own model section. Doing so could reduce the bundle size for loading the model by approximately 1.33 times (33%) since you can directly use the binary files instead of the base64 that are bundled with the package. i.e. The `"MobileNetV2"` model bundled into the package is 3.5MB instead of 2.6MB for hosted binary files. This would only make a difference if you are loading the model every time (without Caching) on the client-side browser since on the server-side, you'd only be loading the model once at the server start.

Model MobileNetV2 - 224x224

const model \= nsfwjs.load("/path/to/mobilenet\_v2/");

If you're using a model that needs an image of dimension other than 224x224, you can pass the size in the options parameter.

Model MobileNetV2Mid - Graph

/\* You may need to load this model with graph type \*/
const model \= nsfwjs.load("/path/to/mobilenet\_v2\_mid/", { type: 'graph' });

If you're using a graph model, you cannot use the infer method, and you'll need to tell model load that you're dealing with a graph model in options.

Model InceptionV3 - 299x299

const model \= nsfwjs.load("/path/to/inception\_v3/", { size: 299 });

### Caching

If you're using in the browser and you'd like to subsequently load from indexed db or local storage (NOTE: model size may be too large for local storage!) you can save the underlying model using the appropriate scheme and load from there.

const initialLoad \= await nsfwjs.load(
  "/path/to/different/model/" /\*, { ...options }\*/
);
await initialLoad.model.save("indexeddb://exampleModel");
const model \= await nsfwjs.load("indexeddb://exampleModel" /\*, { ...options }\*/);

**Parameters**

Initial Load:

1.  URL or path to folder containing `model.json`.
2.  Optional object with size or type property that your model expects.

Subsequent Load:

1.  IndexedDB path.
2.  Optional object with size or type property that your model expects.

**Returns**

-   Ready to use NSFWJS model object

**Troubleshooting**

-   On the tab where the model is being loaded, inspect element and navigate to the the "Application" tab. On the left pane under the "Storage" section, there is a subsection named "IndexedDB". Here you can view if the model is being saved.

### `classify` an image

This function can take any browser-based image elements (`<img>`, `<video>`, `<canvas>`) and returns an array of most likely predictions and their confidence levels.

// Return top 3 guesses (instead of all 5)
const predictions \= await model.classify(img, 3);

**Parameters**

-   Tensor, Image data, Image element, video element, or canvas element to check
-   Number of results to return (default all 5)

**Returns**

-   Array of objects that contain `className` and `probability`. Array size is determined by the second parameter in the `classify` function.

Production
----------

Tensorflow.js offers two flags, `enableProdMode` and `enableDebugMode`. If you're going to use NSFWJS in production, be sure to enable prod mode before loading the NSFWJS model.

import \* as tf from "@tensorflow/tfjs";
import \* as nsfwjs from "nsfwjs";
tf.enableProdMode();
//...
let model \= await nsfwjs.load(\`${urlToNSFWJSModel}\`);

**NOTE:** Consider downloading and hosting the model yourself before moving to production as explained in the Host your own model section. This could potentially improve the initial load time of the model. Furthermore, consider Caching the model, if you are using it in the browser.

Install
-------

NSFWJS is powered by TensorFlow.js as a peer dependency. If your project does not already have TFJS you'll need to add it.

# peer dependency
$ yarn add @tensorflow/tfjs
# install NSFWJS
$ yarn add nsfwjs

For script tags include all the bundles as shown here. Then simply access the nsfwjs global variable. This requires that you've already imported TensorFlow.js as well.

### Host your own model

The magic that powers NSFWJS is the NSFW detection model. By default, the models are bundled into this package. But you may want to host the models on your own server to reduce bundle size by loading them as raw binary files or to host your own custom model. If you want to host your own version of the model files, you can do so by following the steps below. You can then pass the relative URL to your hosted files in the `load` function along with the `options` if necessary.

Here is how to install the default model on a website:

1.  Download the project by either downloading as zip or cloning `git clone https://github.com/infinitered/nsfwjs.git`. **_If downloading as zip does not work use cloning._**
2.  Extract the `models` folder from the root of the project and drop it in the `public` directory of your web application to serve them as static files along side your website. (You can host it anywhere such as on a s3 bucket as long as you can access it via URL).
3.  Retrieve the URL and put it into `nsfwjs.load()`. For example: `nsfwjs.load(https://yourwebsite.com/models/mobilenet_v2/model.json)`.

Run the Examples
----------------

### Tensorflow.js in the browser

The demo that powers https://nsfwjs.com/ is available in the `examples/nsfw_demo` folder.

To run the demo, run `yarn prep` which will copy the latest code into the demo. After that's done, you can `cd` into the demo folder and run with `yarn start`.

### Browserify

A browserified version using nothing but promises and script tags is available in the `minimal_demo` folder.

<script src\="/path/to/model/directory/model.min.js"\></script\>
<script src\="/path/to/model/directory/group1-shard1of2.min.js"\></script\>
<script src\="/path/to/model/directory/group1-shard2of2.min.js"\></script\>
<script src\="/path/to/bundle/nsfwjs.min.js"\></script\>

You should host the `nsfwjs.min.js` file and all the model bundles that you want to use alongside your project, and reference them using the `src` attribute in the script tags.

### React Native

The NSFWJS React Native app

Loads a local copy of the model to reduce network load and utilizes TFJS-React-Native. Blog Post

### Node JS App

Using NPM, you can also use the model on the server side.

$ npm install nsfwjs
$ npm install @tensorflow/tfjs-node

const axios \= require("axios"); //you can use any http client
const tf \= require("@tensorflow/tfjs-node");
const nsfw \= require("nsfwjs");
async function fn() {
  const pic \= await axios.get(\`link-to-picture\`, {
    responseType: "arraybuffer",
  });
  const model \= await nsfw.load(); // To load a local model, nsfw.load('file://./path/to/model/')
  // Image must be in tf.tensor3d format
  // you can convert image to tf.tensor3d with tf.node.decodeImage(Uint8Array,channels)
  const image \= await tf.node.decodeImage(pic.data, 3);
  const predictions \= await model.classify(image);
  image.dispose(); // Tensor memory must be managed explicitly (it is not sufficient to let a tf.Tensor go out of scope for its memory to be released).
  console.log(predictions);
}
fn();

Here is another full example of a multipart/form-data POST using Express, supposing you are using JPG format.

const express \= require("express");
const multer \= require("multer");
const jpeg \= require("jpeg-js");

const tf \= require("@tensorflow/tfjs-node");
const nsfw \= require("nsfwjs");

const app \= express();
const upload \= multer();

let \_model;

const convert \= async (img) \=> {
  // Decoded image in UInt8 Byte array
  const image \= await jpeg.decode(img, { useTArray: true });

  const numChannels \= 3;
  const numPixels \= image.width \* image.height;
  const values \= new Int32Array(numPixels \* numChannels);

  for (let i \= 0; i < numPixels; i++)
    for (let c \= 0; c < numChannels; ++c)
      values\[i \* numChannels + c\] \= image.data\[i \* 4 + c\];

  return tf.tensor3d(values, \[image.height, image.width, numChannels\], "int32");
};

app.post("/nsfw", upload.single("image"), async (req, res) \=> {
  if (!req.file) res.status(400).send("Missing image multipart/form-data");
  else {
    const image \= await convert(req.file.buffer);
    const predictions \= await \_model.classify(image);
    image.dispose();
    res.json(predictions);
  }
});

const load\_model \= async () \=> {
  \_model \= await nsfw.load();
};

// Keep the model in memory, make sure it's loaded only once
load\_model().then(() \=> app.listen(8080));

// curl --request POST localhost:8080/nsfw --header 'Content-Type: multipart/form-data' --data-binary 'image=@/full/path/to/picture.jpg'

You can also use `lovell/sharp` for preprocessing tasks and more file formats.

### NSFW Filter

**NSFW Filter** is an open source web extension for Google Chrome that uses NSFWJS for filtering out NSFW images.

Check out the project here.

Learn TensorFlow.js
-------------------

Learn how to write your own library like NSFWJS with my O'Reilly book "Learning TensorFlow.js" available on O'Reilly and Amazon.

More!
-----

An FAQ page is available.

More about NSFWJS and TensorFlow.js - https://youtu.be/uzQwmZwy3yw

The model was trained in Keras over several days and 60+ Gigs of data. Be sure to check out the model code which was trained on data provided by Alexander Kim's nsfw\_data\_scraper.

### Open Source

NSFWJS, as open source, is free to use and always will be ❤️. It's MIT licensed, and we'll always do our best to help and quickly answer issues. If you'd like to get a hold of us, join our community slack.

### Need the experts? Hire Infinite Red for your next project

If your project's calling for the experts in all things React Native, Infinite Red’s here to help! Our experienced team of software engineers have worked with companies like Microsoft, Zoom, and Mercari to bring even some of the most complex projects to life.

Whether it’s running a full project or training a team on React Native, we can help you solve your company’s toughest engineering challenges – and make it a great experience at the same time. Ready to see how we can work together? Send us a message

Contributors
------------

Thanks goes to these wonderful people (emoji key):

  
**Gant Laborde**  
💬 📝 💻 💡 🤔 🚇 👀 ⚠️

  
**Jamon Holmgren**  
📖 🤔 💻 🖋

  
**Mazen Chami**  
📖 💻 👀 ⚠️

  
**Jeff Studenski**  
🎨

  
**Frank von Hoven III**  
📖 🤔

  
**Sandesh Soni**  
💻

  
**Sean Nam**  
📖

  
**Gilbert Emerson**  
💻

  
**Oleksandr Kozlov**  
🚇 ⚠️ 💻

  
**Morgan**  
💻 🤔

  
**Michel Hua**  
💻 📖

  
**Kevin VanGelder**  
💻 📖

  
**Jesse Nicholson**  
🔣 🤔

  
**camhart**  
📖

  
**Cameron Burkholder**  
🎨

  
**qwertyforce**  
📖

  
**Yegor <3**  
💻 ⚠️

  
**Navendu Pottekkat**  
📖

  
**Vladislav**  
💻 📖

  
**Nacht**  
💻

  
**kateinkim**  
💻 📖

  
**jan**  
📖

  
**Rohan Mukherjee**  
💬 🚇 🚧 💻

  
**Hasitha Wickramasinghe**  
💻 📖 💡 🤔 🚇 ⚠️

This project follows the all-contributors specification. Contributions of any kind welcome!
