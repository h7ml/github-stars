---
project: lvgl
stars: 21086
description: Embedded graphics library to create beautiful UIs for any MCU, MPU and display type. 
url: https://github.com/lvgl/lvgl
---

**English** | 中文 | Português do Brasil | 日本語 | עברית

  

 

Light and Versatile Graphics Library
====================================

   

   

  

Website | Docs | Forum | Demos | Services

  

📒 Overview
-----------

**Mature and Well-known**  
LVGL is the most popular free and open source embedded graphics library to create beautiful UIs for any MCU, MPU and display type. It's supported by industry leading vendors and projects like  Arm, STM32, NXP, Espressif, Nuvoton, Arduino, RT-Thread, Zephyr, NuttX, Adafruit and many more.

**Feature Rich**  
It has all the features to create modern and beautiful GUIs: 30+ built-in widgets, a powerful style system, web inspired layout managers, and a typography system supporting many languages. To integrate LVGL into your platform, all you need is at least 32kB RAM and 128 kB Flash, a C compiler, a frame buffer, and at least an 1/10 screen sized buffer for rendering.

**Services**  
Our team is ready to help you with graphics design, UI implementation and consulting services. Contact us if you need some support during the development of your next GUI project.

🚀 Features
-----------

**Free and Portable**

-   A fully portable C (C++ compatible) library with no external dependencies.
-   Can be compiled to any MCU or MPU, with any (RT)OS.
-   Supports monochrome, ePaper, OLED or TFT displays, or even monitors. Displays
-   Distributed under the MIT license, so you can easily use it in commercial projects too.
-   Needs only 32kB RAM and 128 kB Flash, a frame buffer, and at least an 1/10 screen sized buffer for rendering.
-   OS, External memory and GPU are supported but not required.

**Widgets, Styles, Layouts and more**

-   30+ built-in Widgets:  Button, Label, Slider, Chart, Keyboard, Meter, Arc, Table and many more.
-   Flexible Style system with  ~100 style properties to customize any part of the widgets in any state.
-   Flexbox and Grid\-like layouts engines to automatically size and position the widgets in a responsive way.
-   Texts are rendered with UTF-8 encoding supporting CJK, Thai, Hindi, Arabic, Persian writing systems.
-   Word wrapping, kerning, text scrolling, sub-pixel rendering, Pinyin-IME Chinese input, Emojis in texts.
-   Rendering engine supporting animations, anti-aliasing, opacity, smooth scrolling, shadows, image transformation, etc  
-   Supports Mouse, Touchpad, Keypad, Keyboard, External buttons, Encoder Input devices.
-   Multiple display support.

**Binding and Build Support**

-   MicroPython Binding exposes LVGL API
-   PikaScript Binding python on MCU lighter and easier.
-   No custom build system is used. You can build LVGL as you build the other files of your project.
-   Support for Make and CMake is included out of the box.
-   Develop on PC and use the same UI code on embedded hardware.
-   Convert the C UI code to HTML file with our Emscripten port.

**Docs, Tools, and Services**

-   Detailed Documentation with 100+ simple examples
-   Services such as User interface design, Implementation and Consulting to make UI development simpler and faster.

❤️ Sponsor
----------

If LVGL saved you a lot of time and money or you just had fun using it, consider Supporting its Development.

**How do we spend the donations?**  
Our goal is to provide financial compensation for people who do the most for LVGL. It means not only the maintainers but anyone who implements a great feature should get a payment from the accumulated money. We use the donations to cover our operational costs like servers and related services.

**How to donate?**  
We use GitHub Sponsors where you can easily send one time or recurring donations. You can also see all of our expenses in a transparent way.

**How to get paid for your contribution?**  
If someone implements or fixes an issue labeled as Sponsored he or she will get a payment for that work. We estimate the required time, complexity and importance of the issue and set a price accordingly. To jump in just comment on a Sponsored issue saying "Hi, I'd like to deal with it. This is how I'm planning to fix/implement it...". A work is considered ready when it's approved and merged by a maintainer. After that you can submit and expense at opencollective.com and you will receive the payment in a few days.

**Organizations supporting LVGL**  

**Individuals supporting LVGL**  

📦 Packages
-----------

LVGL is available as:

-   Arduino library
-   PlatformIO package
-   Zephyr library
-   ESP-IDF(ESP32) component
-   NXP MCUXpresso component
-   NuttX library
-   RT-Thread RTOS
-   CMSIS-Pack
-   RIOT OS package

🤖 Examples
-----------

See some examples of creating widgets, using layouts and applying styles. You will find C and MicroPython code, and links to try out or edit the examples in an online MicroPython editor.

For more examples check out the Examples folder.

### Hello world label

C code

/\*Change the active screen's background color\*/
lv\_obj\_set\_style\_bg\_color(lv\_screen\_active(), lv\_color\_hex(0x003a57), LV\_PART\_MAIN);

/\*Create a white label, set its text and align it to the center\*/
lv\_obj\_t \* label \= lv\_label\_create(lv\_screen\_active());
lv\_label\_set\_text(label, "Hello world");
lv\_obj\_set\_style\_text\_color(label, lv\_color\_hex(0xffffff), LV\_PART\_MAIN);
lv\_obj\_align(label, LV\_ALIGN\_CENTER, 0, 0);

MicroPython code | Online Simulator

\# Change the active screen's background color
scr \= lv.screen\_active()
scr.set\_style\_bg\_color(lv.color\_hex(0x003a57), lv.PART.MAIN)

\# Create a white label, set its text and align it to the center
label \= lv.label(lv.screen\_active())
label.set\_text("Hello world")
label.set\_style\_text\_color(lv.color\_hex(0xffffff), lv.PART.MAIN)
label.align(lv.ALIGN.CENTER, 0, 0)

  

### Button with Click Event

C code

lv\_obj\_t \* button \= lv\_button\_create(lv\_screen\_active());                   /\*Add a button to the current screen\*/
lv\_obj\_center(button);                                             /\*Set its position\*/
lv\_obj\_set\_size(button, 100, 50);                                  /\*Set its size\*/
lv\_obj\_add\_event\_cb(button, button\_event\_cb, LV\_EVENT\_CLICKED, NULL); /\*Assign a callback to the button\*/

lv\_obj\_t \* label \= lv\_label\_create(button);                        /\*Add a label to the button\*/
lv\_label\_set\_text(label, "Button");                             /\*Set the labels text\*/
lv\_obj\_center(label);                                           /\*Align the label to the center\*/
...

void button\_event\_cb(lv\_event\_t \* e)
{
  printf("Clicked\\n");
}

MicroPython code | Online Simulator

def button\_event\_cb(e):
  print("Clicked")

\# Create a Button and a Label
button \= lv.button(lv.screen\_active())
button.center()
button.set\_size(100, 50)
button.add\_event\_cb(button\_event\_cb, lv.EVENT.CLICKED, None)

label \= lv.label(button)
label.set\_text("Button")
label.center()

  

### Checkboxes with Layout

C code

lv\_obj\_set\_flex\_flow(lv\_screen\_active(), LV\_FLEX\_FLOW\_COLUMN);
lv\_obj\_set\_flex\_align(lv\_screen\_active(), LV\_FLEX\_ALIGN\_CENTER, LV\_FLEX\_ALIGN\_START, LV\_FLEX\_ALIGN\_CENTER);

lv\_obj\_t \* cb;
cb \= lv\_checkbox\_create(lv\_screen\_active());
lv\_checkbox\_set\_text(cb, "Apple");
lv\_obj\_add\_event\_cb(cb, event\_handler, LV\_EVENT\_ALL, NULL);

cb \= lv\_checkbox\_create(lv\_screen\_active());
lv\_checkbox\_set\_text(cb, "Banana");
lv\_obj\_add\_state(cb, LV\_STATE\_CHECKED);
lv\_obj\_add\_event\_cb(cb, event\_handler, LV\_EVENT\_ALL, NULL);

cb \= lv\_checkbox\_create(lv\_screen\_active());
lv\_checkbox\_set\_text(cb, "Lemon");
lv\_obj\_add\_state(cb, LV\_STATE\_DISABLED);
lv\_obj\_add\_event\_cb(cb, event\_handler, LV\_EVENT\_ALL, NULL);

cb \= lv\_checkbox\_create(lv\_screen\_active());
lv\_obj\_add\_state(cb, LV\_STATE\_CHECKED);
lv\_obj\_add\_state(cb, LV\_STATE\_DISABLED);
lv\_checkbox\_set\_text(cb, "Melon\\nand a new line");
lv\_obj\_add\_event\_cb(cb, event\_handler, LV\_EVENT\_ALL, NULL);

MicroPython code | Online Simulator

def event\_handler(e):
    code \= e.get\_code()
    obj \= e.get\_target\_obj()
    if code \== lv.EVENT.VALUE\_CHANGED:
        txt \= obj.get\_text()
        if obj.get\_state() & lv.STATE.CHECKED:
            state \= "Checked"
        else:
            state \= "Unchecked"
        print(txt + ":" + state)

lv.screen\_active().set\_flex\_flow(lv.FLEX\_FLOW.COLUMN)
lv.screen\_active().set\_flex\_align(lv.FLEX\_ALIGN.CENTER, lv.FLEX\_ALIGN.START, lv.FLEX\_ALIGN.CENTER)

cb \= lv.checkbox(lv.screen\_active())
cb.set\_text("Apple")
cb.add\_event\_cb(event\_handler, lv.EVENT.ALL, None)

cb \= lv.checkbox(lv.screen\_active())
cb.set\_text("Banana")
cb.add\_state(lv.STATE.CHECKED)
cb.add\_event\_cb(event\_handler, lv.EVENT.ALL, None)

cb \= lv.checkbox(lv.screen\_active())
cb.set\_text("Lemon")
cb.add\_state(lv.STATE.DISABLED)
cb.add\_event\_cb(event\_handler, lv.EVENT.ALL, None)

cb \= lv.checkbox(lv.screen\_active())
cb.add\_state(lv.STATE.CHECKED | lv.STATE.DISABLED)
cb.set\_text("Melon")
cb.add\_event\_cb(event\_handler, lv.EVENT.ALL, None)

  

### Styling a Slider

C code

lv\_obj\_t \* slider \= lv\_slider\_create(lv\_screen\_active());
lv\_slider\_set\_value(slider, 70, LV\_ANIM\_OFF);
lv\_obj\_set\_size(slider, 300, 20);
lv\_obj\_center(slider);

/\*Add local styles to MAIN part (background rectangle)\*/
lv\_obj\_set\_style\_bg\_color(slider, lv\_color\_hex(0x0F1215), LV\_PART\_MAIN);
lv\_obj\_set\_style\_bg\_opa(slider, 255, LV\_PART\_MAIN);
lv\_obj\_set\_style\_border\_color(slider, lv\_color\_hex(0x333943), LV\_PART\_MAIN);
lv\_obj\_set\_style\_border\_width(slider, 5, LV\_PART\_MAIN);
lv\_obj\_set\_style\_pad\_all(slider, 5, LV\_PART\_MAIN);

/\*Create a reusable style sheet for the INDICATOR part\*/
static lv\_style\_t style\_indicator;
lv\_style\_init(&style\_indicator);
lv\_style\_set\_bg\_color(&style\_indicator, lv\_color\_hex(0x37B9F5));
lv\_style\_set\_bg\_grad\_color(&style\_indicator, lv\_color\_hex(0x1464F0));
lv\_style\_set\_bg\_grad\_dir(&style\_indicator, LV\_GRAD\_DIR\_HOR);
lv\_style\_set\_shadow\_color(&style\_indicator, lv\_color\_hex(0x37B9F5));
lv\_style\_set\_shadow\_width(&style\_indicator, 15);
lv\_style\_set\_shadow\_spread(&style\_indicator, 5);
4
/\*Add the style sheet to the slider's INDICATOR part\*/
lv\_obj\_add\_style(slider, &style\_indicator, LV\_PART\_INDICATOR);

/\*Add the same style to the KNOB part too and locally overwrite some properties\*/
lv\_obj\_add\_style(slider, &style\_indicator, LV\_PART\_KNOB);

lv\_obj\_set\_style\_outline\_color(slider, lv\_color\_hex(0x0096FF), LV\_PART\_KNOB);
lv\_obj\_set\_style\_outline\_width(slider, 3, LV\_PART\_KNOB);
lv\_obj\_set\_style\_outline\_pad(slider, \-5, LV\_PART\_KNOB);
lv\_obj\_set\_style\_shadow\_spread(slider, 2, LV\_PART\_KNOB);

MicroPython code | Online Simulator

\# Create a slider and add the style
slider \= lv.slider(lv.screen\_active())
slider.set\_value(70, lv.ANIM.OFF)
slider.set\_size(300, 20)
slider.center()

\# Add local styles to MAIN part (background rectangle)
slider.set\_style\_bg\_color(lv.color\_hex(0x0F1215), lv.PART.MAIN)
slider.set\_style\_bg\_opa(255, lv.PART.MAIN)
slider.set\_style\_border\_color(lv.color\_hex(0x333943), lv.PART.MAIN)
slider.set\_style\_border\_width(5, lv.PART.MAIN)
slider.set\_style\_pad\_all(5, lv.PART.MAIN)

\# Create a reusable style sheet for the INDICATOR part
style\_indicator \= lv.style\_t()
style\_indicator.init()
style\_indicator.set\_bg\_color(lv.color\_hex(0x37B9F5))
style\_indicator.set\_bg\_grad\_color(lv.color\_hex(0x1464F0))
style\_indicator.set\_bg\_grad\_dir(lv.GRAD\_DIR.HOR)
style\_indicator.set\_shadow\_color(lv.color\_hex(0x37B9F5))
style\_indicator.set\_shadow\_width(15)
style\_indicator.set\_shadow\_spread(5)

\# Add the style sheet to the slider's INDICATOR part
slider.add\_style(style\_indicator, lv.PART.INDICATOR)
slider.add\_style(style\_indicator, lv.PART.KNOB)

\# Add the same style to the KNOB part too and locally overwrite some properties
slider.set\_style\_outline\_color(lv.color\_hex(0x0096FF), lv.PART.KNOB)
slider.set\_style\_outline\_width(3, lv.PART.KNOB)
slider.set\_style\_outline\_pad(\-5, lv.PART.KNOB)
slider.set\_style\_shadow\_spread(2, lv.PART.KNOB)

  

### English, Hebrew (mixed LTR-RTL) and Chinese texts

C code

lv\_obj\_t \* ltr\_label \= lv\_label\_create(lv\_screen\_active());
lv\_label\_set\_text(ltr\_label, "In modern terminology, a microcontroller is similar to a system on a chip (SoC).");
lv\_obj\_set\_style\_text\_font(ltr\_label, &lv\_font\_montserrat\_16, 0);
lv\_obj\_set\_width(ltr\_label, 310);
lv\_obj\_align(ltr\_label, LV\_ALIGN\_TOP\_LEFT, 5, 5);

lv\_obj\_t \* rtl\_label \= lv\_label\_create(lv\_screen\_active());
lv\_label\_set\_text(rtl\_label,"מעבד, או בשמו המלא יחידת עיבוד מרכזית (באנגלית: CPU - Central Processing Unit).");
lv\_obj\_set\_style\_base\_dir(rtl\_label, LV\_BASE\_DIR\_RTL, 0);
lv\_obj\_set\_style\_text\_font(rtl\_label, &lv\_font\_dejavu\_16\_persian\_hebrew, 0);
lv\_obj\_set\_width(rtl\_label, 310);
lv\_obj\_align(rtl\_label, LV\_ALIGN\_LEFT\_MID, 5, 0);

lv\_obj\_t \* cz\_label \= lv\_label\_create(lv\_screen\_active());
lv\_label\_set\_text(cz\_label,
                  "嵌入式系统（Embedded System），\\n是一种嵌入机械或电气系统内部、具有专一功能和实时计算性能的计算机系统。");
lv\_obj\_set\_style\_text\_font(cz\_label, &lv\_font\_source\_han\_sans\_sc\_16\_cjk, 0);
lv\_obj\_set\_width(cz\_label, 310);
lv\_obj\_align(cz\_label, LV\_ALIGN\_BOTTOM\_LEFT, 5, \-5);

MicroPython code | Online Simulator

ltr\_label \= lv.label(lv.screen\_active())
ltr\_label.set\_text("In modern terminology, a microcontroller is similar to a system on a chip (SoC).")
ltr\_label.set\_style\_text\_font(lv.font\_montserrat\_16, 0);

ltr\_label.set\_width(310)
ltr\_label.align(lv.ALIGN.TOP\_LEFT, 5, 5)

rtl\_label \= lv.label(lv.screen\_active())
rtl\_label.set\_text("מעבד, או בשמו המלא יחידת עיבוד מרכזית (באנגלית: CPU - Central Processing Unit).")
rtl\_label.set\_style\_base\_dir(lv.BASE\_DIR.RTL, 0)
rtl\_label.set\_style\_text\_font(lv.font\_dejavu\_16\_persian\_hebrew, 0)
rtl\_label.set\_width(310)
rtl\_label.align(lv.ALIGN.LEFT\_MID, 5, 0)

font\_hans\_sans\_16\_cjk \= lv.font\_load("S:../../assets/font/lv\_font\_source\_han\_sans\_sc\_16\_cjk.fnt")

cz\_label \= lv.label(lv.screen\_active())
cz\_label.set\_style\_text\_font(font\_hans\_sans\_16\_cjk, 0)
cz\_label.set\_text("嵌入式系统（Embedded System），\\n是一种嵌入机械或电气系统内部、具有专一功能和实时计算性能的计算机系统。")
cz\_label.set\_width(310)
cz\_label.align(lv.ALIGN.BOTTOM\_LEFT, 5, \-5)

▶️ Get started
--------------

This list will guide you to get started with LVGL step-by-step.

**Get Familiar with LVGL**

1.  Check the Online demos to see LVGL in action (3 minutes).
2.  Read the Introduction page of the documentation (5 minutes).
3.  Get familiar with the basics on the Quick overview page (15 minutes).

**Start to Use LVGL**

1.  Set up a Simulator (10 minutes).
2.  Try out some Examples.
3.  Port LVGL to a board. See the Porting guide or check out the ready-to-use Projects.

**Become a Pro**

1.  Read the Main-Modules page to get a better understanding of the library (2-3 hours)
2.  Check the documentation of the Widgets to see their features and usage

**Get Help and Help Others**

1.  If you have questions go to the Forum
2.  Read the Contributing guide to see how you can help to improve LVGL (15 minutes)

🤝 Services
-----------

LVGL LLC was established to provide a solid background for LVGL library and to offer several type of services to help you in UI development. With 15+ years of experience in the user interface and graphics industry we can help you the bring your UI to the next level.

-   **Graphics design** Our in-house graphics designers are experts in creating beautiful modern designs which fit to your product and the resources of your hardware.
-   **UI implementation** We can also implement your UI based on the design you or we have created. You can be sure that we will make the most out of your hardware and LVGL. If a feature or widget is missing from LVGL, don't worry, we will implement it for you.
-   **Consulting and Support** We can support you with consulting as well to avoid pricey and time consuming mistakes during the UI development.
-   **Board certification** For companies who are offering development boards, or production ready kits we do board certification which shows how board can run LVGL.

Check out our Demos as reference. For more information take look at the Services page.

Contact us and tell how we can help.

🌟 Contributing
---------------

LVGL is an open project and contribution is very welcome. There are many ways to contribute from simply speaking about your project, through writing examples, improving the documentation, fixing bugs or even hosting your own project under the LVGL organization.

For a detailed description of contribution opportunities visit the Contributing section of the documentation.

More than 300 people already left their fingerprint in LVGL. Be one them! See you here! 🙂

... and many other.
