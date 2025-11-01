---
project: Fair
stars: 2728
description: A Flutter package used to update widget tree dynamically. Fair提供一整套Flutter动态化解决方案
url: https://github.com/wuba/Fair
---

简体中文|English

* * *

Fair is a dynamic framework designed for Flutter. Through the automatic conversion of native Dart source files by the Fair Compiler tool, the project can obtain the ability to dynamically update the Widget Tree and State.

The goal of creating Fair is to support updates through business bundles and JS distribution without the release of versions (Android, iOS, Web), similar to React Native. After integrating with Flutter Fair, you can quickly publish new pages without waiting for your app's next release date. Fair provides standard widgets, which can be used as a new dynamic page or as part of an existing Flutter page, such as typography/style modification of operation bits, full page replacement, partial replacement, etc.

Fair's UI rendering is lossless and can be restored at the pixel level. Take a look at the effect of escaping some pages of Best Flutter UI Templates:

> The project used is from https://github.com/mitesh77/Best-Flutter-UI-Templates  
> location：/example/lib/best\_flutter\_ui

🏛Architecture
--------------

🚀 Running
----------

Use Flutter Fair require few steps.

**step1：download fair project source code**

It is recommended to download fair to the local and dependencies on the relative path.

The download method is as follows:

```
git clone https://github.com/wuba/fair.git
```

**step2：Add dependency inside `pubspec.yaml`**

Assuming that the fair project and your own project are in the same folder:

# add Fair dependency
dependencies:
  fair: 3.2.1

# add build\_runner and compiler dependency
dev\_dependencies:
  build\_runner: ^2.0.0
  fair\_compiler: ^1.7.0
 
# switch "fair\_version" according to the local Flutter SDK version
# Flutter SDK 3.7.x(3.7.0、3.7.1、3.7.2、3.7.3、3.7.4、3.7.5、3.7.6、3.7.7、3.7.8、3.7.9、3.7.10) -> flutter\_3\_7\_0
# Flutter SDK 3.3.x(3.3.0、3.3.1、3.3.2、3.3.3、3.3.4、3.3.5、3.3.6、3.3.7、3.3.8、3.3.9、3.3.10) -> flutter\_3\_3\_0
# Flutter SDK 3.0.x(3.0.0、3.0.1、3.0.2、3.0.3、3.0.4、3.0.5) -> flutter\_3\_0\_0
# Flutter SDK 2.10.x(2.10.0、2.10.1、2.10.2、2.10.3) -> flutter\_2\_10\_0
# Flutter SDK 2.8.x(2.8.0、2.8.1) -> flutter\_2\_8\_0
# Flutter SDK 2.5.x(2.5.0、2.5.1、2.5.2、2.5.3) -> flutter\_2\_5\_0
# Flutter SDK 2.0.6 -> flutter\_2\_0\_6
# Flutter SDK 1.22.6 -> flutter\_1\_22\_6
dependency\_overrides:
  fair\_version:
    path: ../fair/flutter\_version/flutter\_3\_7\_0

**step3：Wrap your app with FairApp Widget**

void main() {
  WidgetsFlutterBinding.ensureInitialized();

  FairApp.runApplication(
    \_getApp(),
    plugins: {
    },
  );
}

dynamic \_getApp() \=> FairApp(
  modules: {
  },
  delegate: {
  },
  child: MaterialApp(
    home: FairWidget(
            name: 'DynamicWidget',
            path: 'assets/bundle/lib\_src\_page\_dynamic\_widget.fair.json',
            data: {"fairProps": json.encode({})}),
  ),
);

**step4：Import a dynamic widget as FairWidget**

FairWidget(
  name: 'DynamicWidget',
  path: 'assets/bundle/lib\_src\_page\_dynamic\_widget.fair.json',
  data: {"fairProps": json.encode({})}),

DevTools
--------

fair development tools

### Dart Commandline Tool faircli

create fair project

**faircli install**

dart pub global activate faircli

**create fair dynamic project**

faircli create \-n dynamic\_project\_name

**create fair carrier project**

faircli create \-k carrier \-n carrier\_project\_name

### IDEA Plugin FairTemplate

Page/Component Template Code

### DevTools flow chart

### DevTools demo

After using faircli to configure the local hot update service, open the developer options on the mobile device, select the local mode, enter the ip of the development machine, then preview fair dynamic effect

For more details, please refer to fair\_tools

Fair-Online Platform
--------------------

Fair-Online is an integrated cloud development platform for Flutter developers, from online development of Flutter, to real-time compilation and preview, packaging and publishing, and dynamic release of end-side updates, to realize the dynamic online Flutter.

Developers do not need to configure the Flutter development environment, develop and debug code online, compile and preview in real time, and what you see is what you get. Combined with the Flutter dynamic framework Fair and the hot update platform FairPushy created by the 58 open source team, Flutter online dynamics are realized.

Online experience URL: Fair-Online Platform

For more details, please refer to fair\_online

Documentation
-------------

For more details, please refer to https://fair.58.com

### Tools

Fair Cli: Fair\_CLI  
IEDA plugin: jetbrains\_plugin\_fair\_template  
Hot update platform: FAIR PUSHY

versions
--------

3.10.0
------

updateDate: 2023.08.15

-   Adapted to Flutter 3.10.0, released Fair Version 3.10
-   Fix known bugs, fix DSL parser issues

### 3.2.1

updateDate：2023.04.13

-   Fixed some issues.

### 3.2.0

updateDate：2023.04.12

-   Adjust the order of dispose calls, not above the tree, subsequent operations stop
-   Add generic FairPlugin js and dart code, reuse the same interaction logic, add example comments
-   Json parsing compatibility
-   Add exception catching and log printing when executeFunction is called with V8 engine in Android
-   Fix SliverGridDelegateWithFixedCrossAxisCount conversion error.
-   SugarMap and SugarMapEach inputs support other Sugar expressions
-   Optimize the performance of ifEqual ifEqualBool switchCase
-   Fix Domain not recognizing index and item in sugar
-   Make AOT also follow conditions before executing code
-   Fix SugarMap and SugarMapEach set input does not support other Sugar syntax
-   Abstract Domain, add IndexDomain, MapEachDomain, support nested Domains
-   New FunctionDomain generic Domain, generate corresponding parameters for function callbacks for FunctionDomain to use.
-   Added NullableIndexedWidgetBuilder, IndexedWidgetBuilder, WidgetBuilder, TransitionBuilder common Sugar support
-   Some known issues fixed

### 3.1.0

updateDate：2023.03.14

-   Upgrade analyzer library to 5.5.0;
-   Dart function to JS supports parameter passing;
-   JS Object value compatibility;
-   Remove kotlin dependencies from fair/android;
-   Add custom parsing for IconData;
-   The generation of optional positional parameters is modified to obtain pa;
-   Fixed missing OptionalPositional default values;
-   Remove the generation time from the generation.fair. dart comment;
-   Added the ignore unnecessary\_import operation;
-   Fixed incorrect assignment of Sugar.switchCase key and defaultValue;
-   binding was changed to SplayTreeMap to increase search efficiency, especially for lists, where duplicate tags are searched for a short time;
-   Exposing specialBinding so that users can override a value;
-   When the provider is added to the \_binding, the Settings set by the user prevail for quick modification;
-   Fixed the loadCoreJs package splicing problem;
-   Reduced minSdkVersion to 16;
-   runApplication supports specifying the package in which the JS resides;
-   Fixed error in calling context in the \_reload method.

### 3.0.0

updateDate：2022.11.17

-   Fix class constructor parsing exception.
-   Fair Compatible Web.
-   Bindmap logic optimization.

### 2.8.1

updateDate：2022.11.01

-   Fixed：CustomScrollView reference external function builder bug.

### 2.8.0

updateDate：2022.10.21

-   Add support of Flutter SDK 3.3.0+.
-   Add Sugar：Sugar.isNestedScrollViewHeaderSliversBuilder、Sugar.isButtonStyle、Sugar.isDuration、Sugar.popMenuButton、Sugar.sliverChildBuilderDelegate、Sugar.sliverGridDelegateWithFixedCrossAxisCount.
-   Fixed some bugs.

### 2.7.0

updateDate：2022.08.10

-   Add support of Flutter SDK 3.0.0、3.0.1、3.0.2、3.0.3、3.0.4、3.0.5.
-   Fixed some bugs.

#### Fair

-   Fair supports loading bundle files on the phone disk path;
-   Adapt to Flutter SDK 2.10.0, 2.10.1, 2.10.2, 2.10.3;
-   Dart2JS supports parsing static methods;
-   When running, the page error message prompts optimization;
-   Syntactic sugar supports parsing Model data.

### 2.6.0

updateDate：2022.07.05

#### Fair

-   Fair supports loading bundle files on the phone disk path;
-   Adapt to Flutter SDK 2.10.0, 2.10.1, 2.10.2, 2.10.3;
-   Dart2JS supports parsing static methods;
-   When running, the page error message prompts optimization;
-   Syntactic sugar supports parsing Model data.

### 2.5.0

updateDate：2022.05.31

#### Fair

Adapt to flutter SDK 2.8.0, 2.8.1  
Dart2js supports parsing singletons  
New syntax Sugar.switchCase、Sugar.colorsWithOpacity、Sugar.convertToString, etc

#### example

Comprehensively optimize the example structure and upgrade the example experience, which is more suitable for beginners.

In the source code, an example project is added to provide the standard usage of fair API.

example location：`fair/example`

### v2.4.1

updateDate：2022.05.12

Fix FairLogger import problem.  
Upgrade Analyzer to 2.3.0.

### v2.4.0

updateDate：2022.04.26

FlatBuffers supports generating bin files in a null safe environment

### v2.3.0

updateDate: 2022.04.22

#### Fair

supports null-safe  
Adapt to Flutter SDK 2.5.0, 2.5.1, 2.5.2, 2.5.3 and other versions

#### demo

Upgrade the outdated demo in the sample project  
Supplement the iOS runtime environment in the sample project

🕰2022 Roadmap
--------------

-   Major release plan
    -   null-safe version support, expected to be launched on April 22 ✅
    -   Flutter 2.8.0 version adaptation, expected to be launched in mid-May ✅
    -   Flutter 2.10.0 version adaptation, is expected to be launched in early June ✅
    -   Flutter 3.0 version adaptation ✅
    -   IDE syntax detection and hint plugin ✅
    -   Rich syntactic sugar ✅
-   Hot update platform
    -   Dart Server project construction ✅
    -   Flutter Web project construction ✅
    -   Patch/resource management ✅
    -   Project management ✅
    -   Mobile Update&Download ✅
-   Online dynamic
    -   Flutter Web project construction ✅
    -   Dart Server project construction ✅
    -   ActionEdit ✅
    -   Code editing ✅
    -   Component editing ✅
    -   Page editing ✅
    -   Engineering editor ✅
    -   Flutter effect preview ✅
    -   Fair DSL preview ✅
-   IDE plug-in
    -   Fair project generation ✅
    -   Fair template generation ✅
    -   Fair syntax detection ✅

📱Accessed APPs
---------------

  
**58阿姨**  

  
**移动经纪人**  

  
**安居拍房**  

  
**神奇保**  

  
**58商办通**  

  
**58商家版**  

  
**中华英才网**  

✨Contributors
-------------

Thanks goes to these wonderful people (emoji key):

  
**gongpengyang**  
💻

  
**qixu**  
💻

  
**陈有余**  
💻

  
**yangyang**  
💻

  
**wan**  
💻

  
**bujie**  
💻

  
**Kc**  
💻

  
**Wu**  
💻 📖

  
**Penta**  
💻 📖

  
**haijun**  
💻 📖

  
**waynesonic**  
💻

  
**paozhuanyinyu**  
💻

  
**alzzzz**  
💻 📖

  
**xiangwc**  
💻

  
**WangYk**  
💻

  
**SunWei**  
💻

  
**单鹏涛**  
💻

  
**lswc225**  
💻

  
**Goofy**  
💻

  
**itzhaoqian**  
💻

  
**Sunlight Xie**  
💻

  
**lhdycxgghb**  
💻

  
**Prome**  
💻

  
**zmtzawqlp**  
💻

  
**woshixiaohuhu**  
💻

  
**yukixut**  
💻

  
**pearone**  
💻

  
**JOYINF1189**  
💻

  
**Blues9527**  
💻

  
**miserydx**  
💻

  
**CICI Chan**  
💻

This project follows the all-contributors specification. Contributions of any kind welcome!

👏🏻Supporters
--------------

🔧Build together
----------------

Submit issues through Issue, contribute code through Pull Request, and the administrator will review the code.

Friends who are interested in Fair can join the exchange group. For technical consultation and discussion, please go to

WeChat secretary

WeChat group

License
-------

Copyright (C) 2005-present, 58.com. All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

```
* Redistributions of source code must retain the above copyright
  notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above
  copyright notice, this list of conditions and the following
  disclaimer in the documentation and/or other materials provided
  with the distribution.
* Neither the name of 58.com nor the names of its
  contributors may be used to endorse or promote products derived
  from this software without specific prior written permission.
```

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
