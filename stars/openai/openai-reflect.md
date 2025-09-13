---
project: openai-reflect
stars: 162
description: Physical AI Assistant that illuminates your life
url: https://github.com/openai/openai-reflect
---

Caution

This is a demo/hackathon project. This code is provided _as-is_ without any warranty or guarantees. It has not been extensively reviewed for security, reliability, or fitness for any purpose. Use at your own risk.

**Reflect** is a hardware AI Assistant that was built during a OpenAI hackathon. Currently it is built to target espressif devices, but we hope to expand its capabilites if users find it useful. The following were some of the ideas/inspirations during the project.

video demonstration of the device.

* * *

**Communicate naturally**

-   sound, light and color, avoid screens

**Phone is your key**

-   device has no state, all info is on phone

**Reflect on yesterday**

-   ask about events in your calendar

**Prepare for tomorrow**

-   you have a test tomorrow, want to study?

**Assistant to keep you in flow**

-   play music while studying, ask quick questions

**Location Aware**

-   unique behavior in kitchen/office...

**Designed to modify**

-   should be easy to modify/try new things

**Cheap**

-   make it available to as many as possible

### Supported Devices

We hope to expand this list. Reflect was written for a specific device to start, but if it is useful we want to add more.

#### Microcontrollers

-   M5Stack CoreS3 ESP32S3 loT Development Kit

#### Lights

-   LIFX Color A19

### Installing

##### Setup esp-idf

```
git clone -b v5.5 --recursive https://github.com/espressif/esp-idf.git
cd esp-idf
./install.sh esp32s3
. ~/esp-idf/export.sh
```

### Install Code to Device

```
. ~/esp-idf/export.sh
idf.py flash
```

### Using

The device creates a WiFi Access Point named `reflect`. Join this network and then open http://192.168.4.1 to start a session.

If you connected successfully you will see two audio elements on the page. One for Realtime API audio and one for audio from the device. You can unmute these audio elements to for debugging.

### Video

477656058-d56fcb7a-5807-43f1-b314-070e2629bd39.mp4
