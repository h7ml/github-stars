---
project: chrome-based-voice-recognition-api
stars: 10
description: An api to utilize the SpeechRecognition tool utilized by google chromes webkitSpeechRecognition in a node script.
url: https://github.com/erwidman/chrome-based-voice-recognition-api
---

> An API used to hijack chrome webkitSpeechRecognition for non-web applications.

Description
-----------

This API intends to create a binding to Chrome SpeechRecognition API for native node processes outside web environments. The use of Chrome's voice recognition as opposed to a paid cloud service offers an inexpensive, easy to install, fast alternative for small projects that don't justify the hassle of setting up a cloud service.

Caveats
-------

The original concept involved a headless chrome instance, however due to a number of issues - it does not seem reasonable to accomplish headless as it will require hacking around the chromium source code. In the meantime, the API simply opens a small chrome window.

In order for the API to operate one of the follow must be a valid environment variable pointing to the chrome executable:

-   chrome
-   chromium-browser
-   Google\\ Chrome
-   google-chrome

Usage
-----

const recog \= require('chrome-based-voice-recognition-api');

recog.launchSpeechRecognition(12000)
.then((data)\=>{
	let client \= data.client;
	recog.initSpeechRecognition({
		lang : 'en-us',
		interimResults : false,
		maxAlternatives : 1,
		infiniteListen : true
	},client);
	recog.addFilter("^lights on$",client);
	client.on('recognition',(data)\=>{
		//todo
	});
	client.on('startedListen',()\=>{
		//todo
	});
	client.on('stopedListen',()\=>{
		//todo
	})
	client.on('recognitionError',(err)\=>{
		//todo
	})
	recog.startListen(client);
});

API
---

####launchSpeechRecogition(port)

#####Description      Spins up the websocket server and chrome instance.

#####Params     port (number) : The desired port of page server

    Note : port + 1 will be used for websocket server

#####Returns     An object with two properties -

-   client : an instace of simple-websocket handling IPC
-   serv : an instance of simple-websocket/server

####initSpeechRecognition(options,client)

#####Description      Instantiates webkit speech recog in chrome.

#####Params     options : An object with settings to be applied to speech object.

    All are optional.

-   lang (string): The language to be recognized
-   interimResults (boolean) : Indication that you wish to recieve low confidence results.
-   maxAlternatives (number) : The max number of alternatives sent from recog.
-   infiniteListen (boolean) : If true, will continue listening after a hit.

    client : The instance of simple-websocket from launchSpeechRecogntion

#####Returns     An object with two properties

-   client : an instace of simple-websocket handling the IPC
-   serv : an instance of simple-websocket/server

####addGrammar(grammar,weight,client)

#####Description      Adds a grammar to an active recognition instance.

#####Params     grammar & weight : see link

    client : The instance of simple-websocket from launchSpeechRecogntion

#####Returns     none

####addFilter(expression,client)

#####Description      Adds a filter specifying what phrases will trigger a recognition event.

#####Params     expression (string): JS regex in the form of string specifyng a filter

    client : The instance of simple-websocket from launchSpeechRecogntion

#####Returns     none

####startListen(client)

#####Description      Request recog object to begin listening

#####Params

    client : The instance of simple-websocket from launchSpeechRecogntion

####Returns     none

####endListen(client)

#####Description      Request recog object to stop listening

#####Params

    client : The instance of simple-websocket from launchSpeechRecogntion

#####Returns     none
