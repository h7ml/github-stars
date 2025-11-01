---
project: lvgl
stars: 21790
description: Embedded graphics library to create beautiful UIs for any MCU, MPU and display type. 
url: https://github.com/lvgl/lvgl
---

**English** | 中文 | Português do Brasil | 日本語 | עברית

  

 

Light and Versatile Graphics Library
====================================

  

   

  

Website | LVGL Pro Editor | Docs | Forum | Demos | Services

  

### Table of Contents

Overview  
Features  
Platform Support  
LVGL Pro Editor  
Commercial Services  
Integrating LVGL  
Examples  
Contributing

  

📒 Overview
-----------

**LVGL** is a free and open-source UI library that enables you to create graphical user interfaces for any MCUs and MPUs from any vendor on any platform.

**Requirements**: LVGL has no external dependencies, which makes it easy to compile for any modern target, from small MCUs to multi-core Linux-based MPUs with 3D support. For a simple UI, you need only ~100kB RAM, ~200–300kB flash, and a buffer size of 1/10 of the screen for rendering.

**To get started**, pick a ready-to-use VSCode, Eclipse, or any other project and try out LVGL on your PC. The LVGL UI code is fully platform-independent, so you can use the same UI code on embedded targets too.

**LVGL Pro** is a complete toolkit to help you build, test, share, and ship UIs faster. It comes with an XML Editor where you can quickly create and test reusable components, export C code, or load the XMLs at runtime. Learn more here.

💡 Features
-----------

**Free and Portable**

-   A fully portable C (C++ compatible) library with no external dependencies.
-   Can be compiled for any MCU or MPU, with any (RT)OS. Make, CMake, and simple globbing are all supported.
-   Supports monochrome, ePaper, OLED, or TFT displays, or even monitors. Displays
-   Distributed under the MIT license, so you can easily use it in commercial projects too.
-   Needs only 32kB RAM and 128kB Flash, a frame buffer, and at least a 1/10 screen-sized buffer for rendering.
-   OS, external memory, and GPU are supported but not required.

**Widgets, Styles, Layouts, and More**

-   30+ built-in Widgets: Button, Label, Slider, Chart, Keyboard, Meter, Arc, Table, and many more.
-   Flexible Style system with ~100 style properties to customize any part of the widgets in any state.
-   Flexbox and Grid\-like layout engines to automatically size and position the widgets responsively.
-   Text is rendered with UTF-8 encoding, supporting CJK, Thai, Hindi, Arabic, and Persian writing systems.
-   Data bindings to easily connect the UI with the application.
-   Rendering engine supports animations, anti-aliasing, opacity, smooth scrolling, shadows, image transformation, etc.
-   Powerful 3D rendering engine to show glTF models with OpenGL.
-   Supports Mouse, Touchpad, Keypad, Keyboard, External buttons, Encoder Input devices.
-   Multiple display support.

📦️ Platform Support
--------------------

LVGL has no external dependencies, so it can be easily compiled for any devices and it's also available in many package managers and RTOSes:

-   Arduino library
-   PlatformIO package
-   Zephyr library
-   ESP-IDF(ESP32) component
-   NXP MCUXpresso component
-   NuttX library
-   RT-Thread RTOS
-   CMSIS-Pack
-   RIOT OS package

🚀 LVGL Pro Editor
------------------

LVGL Pro is a complete toolkit to build, test, share, and ship embedded UIs efficiently.

It consists of four tightly related tools:

1.  **XML Editor**: The heart of LVGL Pro. A desktop app to build components and screens in XML, manage data bindings, translations, animations, tests, and more. Learn more about the XML Format and the Editor.
2.  **Online Viewer**: Run the Editor in your browser, open GitHub projects, and share easily without setting up a developer environment. Visit https://viewer.lvgl.io.
3.  **CLI Tool**: Generate C code and run tests in CI/CD. See the details here.
4.  **Figma Plugin**: Sync and extract styles directly from Figma. See how it works here.

Together, these tools let developers build UIs efficiently, test them reliably, and collaborate with team members and customers.

Learn more at https://pro.lvgl.io

🤝 Commercial Services
----------------------

LVGL LLC provides several types of commercial services to help you with UI development. With 15+ years of experience in the user interface and graphics industry, we can help bring your UI to the next level.

-   **Graphics design**: Our in-house graphic designers are experts in creating beautiful modern designs that fit your product and the capabilities of your hardware.
-   **UI implementation**: We can implement your UI based on the design you or we have created. You can be sure that we will make the most of your hardware and LVGL. If a feature or widget is missing from LVGL, don't worry, we will implement it for you.
-   **Consulting and Support**: We also offer consulting to help you avoid costly and time-consuming mistakes during UI development.
-   **Board certification**: For companies offering development boards or production-ready kits, we provide board certification to show how the board can run LVGL.

Check out our Demos as references. For more information, take a look at the Services page.

Contact us and tell us how we can help.

🧑‍💻 Integrating LVGL
----------------------

Integrating LVGL is very simple. Just drop it into any project and compile it as you would compile other files. To configure LVGL, copy `lv_conf_template.h` as `lv_conf.h`, enable the first `#if 0`, and adjust the configs as needed. (The default config is usually fine.) If available, LVGL can also be used with Kconfig.

Once in the project, you can initialize LVGL and create display and input devices as follows:

#include "lvgl/lvgl.h" /\*Define LV\_LVGL\_H\_INCLUDE\_SIMPLE to include as "lvgl.h"\*/

#define TFT\_HOR\_RES 320
#define TFT\_VER\_RES 240

static uint32\_t my\_tick\_cb(void)
{
    return my\_get\_millisec();
}

static void my\_flush\_cb(lv\_display\_t \* disp, const lv\_area\_t \* area, uint8\_t \* px\_map)
{
    /\*Write px\_map to the area->x1, area->x2, area->y1, area->y2 area of the
     \*frame buffer or external display controller. \*/
}

static void my\_touch\_read\_cb(lv\_indev\_t \* indev, lv\_indev\_data\_t \* data)
{
   if(my\_touch\_is\_pressed()) {
       data\->point.x \= touchpad\_x;
       data\->point.y \= touchpad\_y;
       data\->state \= LV\_INDEV\_STATE\_PRESSED;
   } else {
       data\->state \= LV\_INDEV\_STATE\_RELEASED;
   }
}

void main(void)
{
    my\_hardware\_init();

    /\*Initialize LVGL\*/
    lv\_init();

    /\*Set millisecond-based tick source for LVGL so that it can track time.\*/
    lv\_tick\_set\_cb(my\_tick\_cb);

    /\*Create a display where screens and widgets can be added\*/
    lv\_display\_t \* display \= lv\_display\_create(TFT\_HOR\_RES, TFT\_VER\_RES);

    /\*Add rendering buffers to the screen.
     \*Here adding a smaller partial buffer assuming 16-bit (RGB565 color format)\*/
    static uint8\_t buf\[TFT\_HOR\_RES \* TFT\_VER\_RES / 10 \* 2\]; /\* x2 because of 16-bit color depth \*/
    lv\_display\_set\_buffers(display, buf, NULL, sizeof(buf), LV\_DISPLAY\_RENDER\_MODE\_PARTIAL);

    /\*Add a callback that can flush the content from \`buf\` when it has been rendered\*/
    lv\_display\_set\_flush\_cb(display, my\_flush\_cb);

    /\*Create an input device for touch handling\*/
    lv\_indev\_t \* indev \= lv\_indev\_create();
    lv\_indev\_set\_type(indev, LV\_INDEV\_TYPE\_POINTER);
    lv\_indev\_set\_read\_cb(indev, my\_touch\_read\_cb);

    /\*The drivers are in place; now we can create the UI\*/
    lv\_obj\_t \* label \= lv\_label\_create(lv\_screen\_active());
    lv\_label\_set\_text(label, "Hello world");
    lv\_obj\_center(label);

    /\*Execute the LVGL-related tasks in a loop\*/
    while(1) {
        lv\_timer\_handler();
        my\_sleep\_ms(5);         /\*Wait a little to let the system breathe\*/
    }
}

🤖 Examples
-----------

You can check out more than 100 examples at https://docs.lvgl.io/master/examples.html

The Online Viewer also contains tutorials to easily learn XML: https://viewer.lvgl.io/

### Hello World Button with an Event

C code

static void button\_clicked\_cb(lv\_event\_t \* e)
{
  printf("Clicked\\n");
}

\[...\]

lv\_obj\_t \* button \= lv\_button\_create(lv\_screen\_active());
lv\_obj\_center(button);
lv\_obj\_add\_event\_cb(button, button\_clicked\_cb, LV\_EVENT\_CLICKED, NULL);

lv\_obj\_t \* label \= lv\_label\_create(button);
lv\_label\_set\_text(label, "Hello from LVGL!");

In XML with LVGL Pro

<screen\>
	<view\>
		<lv\_button align\="center"\>
			<event\_cb callback\="button\_clicked\_cb" />
			<lv\_label text\="Hello from LVGL!" />
		</lv\_button\>
	</view\>
</screen\>

### Styled Slider with Data-binding

C code

static void my\_observer\_cb(lv\_observer\_t \* observer, lv\_subject\_t \* subject)
{
	printf("Slider value: %d\\n", lv\_subject\_get\_int(subject));
}

\[...\]

static lv\_subject\_t subject\_value;
lv\_subject\_init\_int(&subject\_value, 35);
lv\_subject\_add\_observer(&subject\_value, my\_observer\_cb, NULL);

lv\_style\_t style\_base;
lv\_style\_init(&style\_base);
lv\_style\_set\_bg\_color(&style\_base, lv\_color\_hex(0xff8800));
lv\_style\_set\_bg\_opa(&style\_base, 255);
lv\_style\_set\_radius(&style\_base, 4);

lv\_obj\_t \* slider \= lv\_slider\_create(lv\_screen\_active());
lv\_obj\_center(slider);
lv\_obj\_set\_size(slider, lv\_pct(80), 16);
lv\_obj\_add\_style(slider, &style\_base, LV\_PART\_INDICATOR);
lv\_obj\_add\_style(slider, &style\_base, LV\_PART\_KNOB);
lv\_obj\_add\_style(slider, &style\_base, 0);
lv\_obj\_set\_style\_bg\_opa(slider, LV\_OPA\_50, 0);
lv\_obj\_set\_style\_border\_width(slider, 3, LV\_PART\_KNOB);
lv\_obj\_set\_style\_border\_color(slider, lv\_color\_hex3(0xfff), LV\_PART\_KNOB);
lv\_slider\_bind\_value(slider, &subject\_value);

lv\_obj\_t \* label \= lv\_label\_create(lv\_screen\_active());
lv\_obj\_align(label, LV\_ALIGN\_CENTER, 0, \-30);
lv\_label\_bind\_text(label, &subject\_value, "Temperature: %d °C");

In XML with LVGL Pro

<screen\>
	<styles\>
		<style name\="style\_base" bg\_opa\="100%" bg\_color\="0xff8800" radius\="4" />
		<style name\="style\_border" border\_color\="0xfff" border\_width\="3" />
	</styles\>

	<view\>
		<lv\_label bind\_text\="value" bind\_text-fmt\="Temperature: %d °C" align\="center" y\="\-30" />
		<lv\_slider align\="center" bind\_value\="value" style\_bg\_opa\="30%"\>
			<style name\="style\_base" />
			<style name\="style\_base" selector\="knob" />
			<style name\="style\_base" selector\="indicator" />
			<style name\="style\_border" selector\="knob" />
		</lv\_slider\>
	</view\>
</screen\>

### Checkboxes in a Layout

C code

/\*Create a new screen and load it\*/
lv\_obj\_t \* scr \= lv\_obj\_create(NULL);
lv\_screen\_load(scr);

/\*Set a column layout\*/
lv\_obj\_set\_flex\_flow(scr, LV\_FLEX\_FLOW\_COLUMN);
lv\_obj\_set\_flex\_align(scr, LV\_FLEX\_ALIGN\_SPACE\_EVENLY, /\*Vertical alignment\*/
  					   LV\_FLEX\_ALIGN\_START,	       /\*Horizontal alignment in the track\*/
  					   LV\_FLEX\_ALIGN\_CENTER);      /\*Horizontal alignment of the track\*/

/\*Create 5 checkboxes\*/
const char \* texts\[5\] \= {"Input 1", "Input 2", "Input 3", "Output 1", "Output 2"};
for(int i \= 0; i < 5; i++) {
  lv\_obj\_t \* cb \= lv\_checkbox\_create(scr);
  lv\_checkbox\_set\_text(cb, texts\[i\]);
}

/\*Change some states\*/
lv\_obj\_add\_state(lv\_obj\_get\_child(scr, 1), LV\_STATE\_CHECKED);
lv\_obj\_add\_state(lv\_obj\_get\_child(scr, 3), LV\_STATE\_DISABLED);

In XML with LVGL Pro

<screen\>
	<view
		flex\_flow="column"
		style\_flex\_main\_place="space\_evenly"
		style\_flex\_cross\_place="start"
		style\_flex\_track\_place="center"
	>
		<lv\_checkbox text\="Input 1"/>
		<lv\_checkbox text\="Input 2"/>
		<lv\_checkbox text\="Input 3" checked\="true"/>
		<lv\_checkbox text\="Output 1"/>
		<lv\_checkbox text\="Output 2" disabled\="true"/>
   </view\>
</screen\>

🌟 Contributing
---------------

LVGL is an open project, and contributions are very welcome. There are many ways to contribute, from simply speaking about your project, writing examples, improving the documentation, fixing bugs, or even hosting your own project under the LVGL organization.

For a detailed description of contribution opportunities, visit the Contributing section of the documentation.

More than 600 people have already left their fingerprint on LVGL. Be one of them! See you here! 🙂

... and many more.
