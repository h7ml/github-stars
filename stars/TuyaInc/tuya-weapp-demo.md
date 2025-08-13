---
project: tuya-weapp-demo
stars: 19
description: 涂鸦智能小程序，用小程序控制您的智能设备，即扫即用
url: https://github.com/TuyaInc/tuya-weapp-demo
---

中文版 | English

#### Note: This repository will be deprecated soon, please refer to the new repository in the Tuya Github Organization: https://github.com/tuya/tuya-weapp-demo.

Overview
--------

This Demo is for quick connection to Tuya Cloud Function, Pairing Plugin and, MQTT. New features will be updated in the future.

Get Started
-----------

If you need to embed the pairing function in your applet, you can get your ticket information by connecting to the cloud function and call the applet plugin to complete paring. Call the API for getting device information after pairing is completed

If you need to develop device control, scene linkage and automation, you can call the corresponding APIs through the cloud function.

Contact us if you need a Tuya all-in-one applet. Scan the QR code below to experience the all-in-one applet.

If no device is indicated in the device list, you can tap **Adding device** and select **Scan the QR code to pair**. You can experience the device by scanning the QR code below.

Diffuser

Air purifier

air conditioner

The curtain motor

Intelligent lamp

Demo directory
--------------

```
├── cloudfunctions             //  Cloud function directory
│   ├── ty-service             // SDK
├── miniprogram                // Applet home directory
│   ├── image                  // The gallery
│   ├── libs                   // Third-party libraries
│   ├── pages                  // The directory of a specific page
│   ├── app.js                 // Applet entry
│   ├── app.json               // Configuration file
├── project.config.json        // Project configuration file
└── README.md                  // Description file
```

Demo description
----------------

-   #### Device pairing
    
    Click the button to pair. You can select from AP pairing, QR code pairing, Bluetooth pairing, and Zigbee pairing.
    
-   #### Experience device function
    
    After adding a device, you can click the device on the switch to debug the MQTT push notification. It is recommended to use the getDeviceSpecifications function in the api.js file to get the instruction set to prevent possible inconsistencies in the DP field names. The content of the push notification will be displayed on the page after the command is sent.
    
-   #### Supported device functions
    
    The current full version Demo supports device control, push notification, adding devices (pairing), and home module.
    

Technical support
-----------------

Contact us if you have any queries.
