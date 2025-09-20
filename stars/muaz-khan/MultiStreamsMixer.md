---
project: MultiStreamsMixer
stars: 453
description: MultiStreamsMixer is a JavaScript library that allows you pass multiple streams (e.g. screen+camera or multiple-cameras) and get single stream.
url: https://github.com/muaz-khan/MultiStreamsMixer
---

MultiStreamsMixer.js | LIVE DEMO
================================

-   Mix Multiple Cameras or Videos
-   Mix Multiple Microphones or Audios (Mp3/Wav/Ogg)
-   Mix Multiple Screens or Screen+Video
-   Mix Canvas 2D Animation + Camera + Screen
-   and **GET SINGLE STREAM!!**

All Demos
=========

1.  **Main Demo:** https://www.webrtc-experiment.com/MultiStreamsMixer/
2.  Record Multiple Cameras
3.  Record Camera+Screen

> Pass multiple streams (e.g. screen+camera or multiple-cameras) and get single stream.

Link the library
================

<script src\="https://www.webrtc-experiment.com/MultiStreamsMixer.js"\></script\>

Or link specific build:

-   https://github.com/muaz-khan/MultiStreamsMixer/releases

Or install using NPM:

npm install multistreamsmixer

And import/require:

const MultiStreamsMixer \= require('multistreamsmixer');
import MultiStreamsMixer from 'multistreamsmixer';

How to mix audios?
==================

const audioMixer \= new MultiStreamsMixer(\[microphone1, microphone2\]);

// record using MediaRecorder API
const recorder \= new MediaRecorder(audioMixer.getMixedStream());

// or share using WebRTC
rtcPeerConnection.addStream(audioMixer.getMixedStream());

How to mix screen+camera?
=========================

screenStream.fullcanvas \= true;
screenStream.width \= screen.width; // or 3840
screenStream.height \= screen.height; // or 2160 

cameraStream.width \= parseInt((20 / 100) \* screenStream.width);
cameraStream.height \= parseInt((20 / 100) \* screenStream.height);
cameraStream.top \= screenStream.height \- cameraStream.height;
cameraStream.left \= screenStream.width \- cameraStream.width;

const mixer \= new MultiStreamsMixer(\[screenStream, cameraStream\]);

rtcPeerConnection.addStream(mixer.getMixedStream());

mixer.frameInterval \= 1;
mixer.startDrawingFrames();

btnStopStreams.onclick \= function() {
    mixer.releaseStreams();
};

btnAppendNewStreams.onclick \= function() {
    mixer.appendStreams(\[anotherStream\]);
};

btnStopScreenSharing.onclick \= function() {
    // replace all old streams with this one
    // it will replace only video tracks
    mixer.resetVideoStreams(\[cameraStreamOnly\]);
};

How to mix multiple cameras?
============================

const mixer \= new MultiStreamsMixer(\[camera1, camera2\]);

rtcPeerConnection.addStream(mixer.getMixedStream());

mixer.frameInterval \= 1;
mixer.startDrawingFrames();

API
===

1.  `getMixedStream`: (function) returns mixed MediaStream object
2.  `frameInterval`: (property) allows you set frame interval
3.  `startDrawingFrames`: (function) start mixing video streams
4.  `resetVideoStreams`: (function) replace all existing video streams with new ones
5.  `releaseStreams`: (function) stop mixing streams
6.  `appendStreams`: (function) append extra/new streams (anytime)

TypeScript / Angular
====================

import { MultiStreamsMixer } from 'yourPath/MultiStreamsMixer';
let mixer \= new MultiStreamsMixer(\[stream1,stream2\]);
mixer.appendStreams(stream3);
let mixed \= mixer.getMixedStream();

P.S: pollyfills are removed (except for `AudioContext`) use adapter instead.

Access `<canvas>` or `<video>` using `querySelector`
====================================================

var canvas \= document.querySelector('canvas.multi-streams-mixer');
var videos \= document.querySelectorAll('video.multi-streams-mixer');

canvas.style.opacity \= .1;

API
===

// default elementClass is "multi-streams-mixer"
var instance \= new MultiStreamsMixer(arrayOfMediaStreams, elementClass);

MultiStreamsMixer.prototype \= {
	// get readonly MediaStream
	getMixedStream: function() {},

	// add more streams
	appendStreams: function(arrayOfMediaStreams) {},

	// replace with set of your own streams
	resetVideoStreams: function(arrayOfMediaStreams) {},

	// clear all the data
	clearRecordedData: function() {}
};

License
-------

MultiStreamsMixer.js is released under MIT licence . Copyright (c) Muaz Khan.
