---
project: kalidoface-3d
stars: 478
description: Face and Body Tracking for VRM 3D models on the web.
url: https://github.com/yeemachine/kalidoface-3d
---

Kalidoface 3D - Face and Full-Body tracking for Vtubing on the web!
===================================================================

A sequal to **Kalidoface** which supports Live2D avatars, **Kalidoface 3D** is a web app that brings support for 3D Vtuber avatars. It now features more dynamic camera angles, and even full-body tracking options using the latest Mediapipe human pose detection models. Add the web app to your homescreen to use it in standalone full screen or even use it in OBS as a browser object directly.

### Use your own VRM 3D models

Kalidoface 3D works with **VRM 3D models**. Just drag and drop your own .vrm files to add your Vtuber character. Might support other types of 3D human models if they're easy to implement.  
  
Models are saved locally so you won't need to reupload them next visit!

### Call a friend

Share your **6 digit code** with a friend to start a private **voice call** using virtual avatars! Now updated with new selfie and first person camera modes.

### Upload custom background

Upload image backgrounds, or use the included **chroma key colors** for keying in special software such as OBS. You can also upload resizeable **gif stickers** to use as props for your videos/streams. Uploaded images are also saved locally for the next time you visit!

### Add resizeable stickers

Add **image/gif** stickers that you can resize and use as props for videos or streaming.

All sample VRM models are not mine and credit should go to the creators on Vroid Hub.

### OBS Integration

To use Kalidoface directly in a Browser object in OBS, you need the `-use-fake-ui-for-media-stream` and `--allow-file-access-from-files` flags enabled. This is used to get access to the webcam and to allow custom This can be done through a terminal/command prompt. Below is a sample to get it running on mac. Just add the 2 prompts right after the path to your OBS application.

```
/Applications/OBS.app/Contents/MacOS/OBS -use-fake-ui-for-media-stream --allow-file-access-from-files
```

### Standalone Tracking Library

Interested in making your own Vtuber app? **Kalidoface** is a JS library that solves for face, full body, and hand tracking.
