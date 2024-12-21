---
project: screenity
stars: 13099
description: The free and privacy-friendly screen recorder with no limits 🎥
url: https://github.com/alyssaxuu/screenity
---

Screenity
=========

The free and privacy-friendly screen recorder with no limits 🎥

Get it now - it's free!

Screenity is a powerful privacy-friendly screen recorder and annotation tool to make better videos for work, education, and more. You can create stunning product demos, tutorials, presentations, or share feedback with your team - all for free.

> You can support this project (and many others) through GitHub Sponsors! ❤️

Made by Alyssa X

> ❗️ Screenity has been rebuilt from the ground up, and updated to MV3. Click here to here to learn more about why, and what's changed in the new version. Also note that **the license has changed to GPLv3**, but the older MV2 version remains MIT licensed. Make sure you read the license and the Terms of Service regarding intellectual property.

Table of contents
-----------------

-   Features
-   Self-hosting Screenity
-   Creating a development version
    -   Enabling Save to Google Drive
-   Acknowledgements

Features
--------

🎥 Make unlimited recordings of your tab, a specific area, desktop, any application, or camera  
🎙️ Record your microphone or internal audio, and use features like push to talk  
✏️ Annotate by drawing anywhere on the screen, adding text, arrows, shapes, and more  
✨ Use AI-powered camera backgrounds or blur to enhance your recordings  
🔎 Zoom in smoothly in your recordings to focus on specific areas  
🪄 Blur out any sensitive content of any page to keep it private  
✂️ Remove or add audio, cut, trim, or crop your recordings with a comprehensive editor  
👀 Highlight your clicks and cursor, and go in spotlight mode  
⏱️ Set up alarms to automatically stop your recording  
💾 Export as mp4, gif, and webm, or save the video directly to Google Drive to share a link  
⚙️ Set a countdown, hide parts of the UI, or move it anywhere  
🔒 Only you can see your videos, we don’t collect any of your data. You can even go offline!  
💙 No limits, make as many videos as you want, for as long as you want  
…and much more - all for free & no sign in needed!

Self-hosting Screenity
----------------------

You can run Screenity locally without having to install it from the Chrome Store. Here's how:

1.  Download the latest Build.zip from the releases page
2.  Load the extension by pasting `chrome://extensions/` in the address bar, and enabling developer mode.
3.  Drag the folder that contains the code (make sure it's a folder and not a ZIP file, so unzip first), or click on the "Load unpacked" button and locate the folder.
4.  That's it, you should now be able to use Screenity locally. Follow these instructions to set up the Google Drive integration.

Creating a development version
------------------------------

> ❗️ Note that the license has changed to GPLv3 for the current MV3 version (Screenity version 3.0.0 and higher). Make sure to read the license and the Terms of Service regarding intellectual property.

1.  Check if your Node.js version is >= **14**.
2.  Clone this repository.
3.  Run `npm install` to install the dependencies.
4.  Run `npm start`.
5.  Load the extension by going to `chrome://extensions/` , and enabling developer mode.
6.  Click on `Load unpacked extension`.
7.  Select the `build` folder.

### Enabling Save to Google Drive

To enable the Google Drive Upload (authorization consent screen) you must change the client\_id in the manifest.json file with your linked extension key.

You can create it accessing Google Cloud Console and selecting Create Credential > OAuth Client ID > Chrome App. To create a persistent extension key, you can follow the steps detailed here.

Libraries used
--------------

-   FFmpeg WASM for editing and encoding videos
-   Tensorflow with the Selfie Segmentation model
-   Fabric.js for drawing and annotating
-   Radix Primitives for the UI components
-   react-color for the color wheel
-   localForage to help store videos offline with IndexedDB
-   Wavesurfer.js to create audio waveforms in the popup and the editor
-   React Advanced Cropper for the cropping UI in the editor
-   fix-webm-duration to add missing metadata to WEBM files

Acknowledgements
----------------

-   Thanks to HelpKit for sponsoring this project by hosting the Screenity Help Center.
-   Thanks to Mei Xuan for helping with the Chinese translation of the extension.

If you need any help, or want to become a Screenity expert, you can browse articles and guides in the help center. You can also submit any feedback or ideas in this form, or contact through this page

Feel free to reach out to me through email at hi@alyssax.com or on Twitter if you have any questions or feedback! Hope you find this useful 💜
