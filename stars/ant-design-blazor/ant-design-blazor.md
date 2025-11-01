---
project: ant-design-blazor
stars: 6123
description: 🌈A rich set of enterprise-class UI components based on Ant Design and Blazor.
url: https://github.com/ant-design-blazor/ant-design-blazor
---

Ant Design Blazor
=================

A rich set of enterprise-class UI components based on Ant Design and Blazor.

English | 简体中文

✨ Features
----------

-   🌈 Enterprise-class UI designed for web applications.
-   📦 A set of high-quality Blazor components out of the box.
-   💕 Supports WebAssembly-based client-side and SignalR-based server-side UI event interaction.
-   🎨 Supports Progressive Web Applications (PWA).
-   🛡 Build with C#, a multi-paradigm static language for an efficient development experience.
-   🌍 Internationalization support for dozens of languages.
-   🎁 Seamless integration with existing ASP.NET Core MVC and Razor Pages projects.

🌈 Online Examples
------------------

WebAssembly static hosting on:

-   Document site
-   Enterprise system dashboard

🖥 Environment Support
----------------------

-   Supports .NET Core 3.1 / .NET 5 / .NET 6 / .Net 7 / .NET 8 / .NET 9 .
-   Supports WebAssembly static file deployment.
-   Supports 4 major browsers engines, and Internet Explorer 11+ (Blazor Server only)
-   Supports .NET MAUI / WPF / Windows Forms and other Blazor Hybrid workloads.
-   Supports Electron and other Web standards-based environments.

> Due to WebAssembly restriction, Blazor WebAssembly doesn't support IE browser, but Blazor Server supports IE 11† with additional polyfills. See official documentation.

> From .NET 5, IE 11 is no longer officially supported. See Blazor: Updated browser support. Unofficial support is provided by Blazor.Polyfill community project.

💿 Current Version
------------------

-   Release:
    
-   Nightly:
    
    _Download our latest nightly builds_
    

🎨 Design Specification
-----------------------

Regularly synchronize with Official Ant Design specifications, you can check the sync logs online.

Therefore, you can use the custom theme styles of Ant Design directly.

**Before the 1.0 release, we will only sync antd 4.x styles.**

📦 Installation Guide
---------------------

### Prerequirement

-   Install .NET Core SDK 3.1.300 or later, .NET 8 is even better.

### Option 1: Create a new project from the dotnet new template

We have provided the `dotnet new` template to create a Boilerplate project out of the box：

-   Install the template
    
    $ dotnet new --install AntDesign.Templates
    
-   Create the Boilerplate project with the template
    
    $ dotnet new antdesign -o MyAntDesignApp
    

Options for the template：

Options

Description

Type

Default

`-f` | `--full`

If specified, generates all pages of Ant Design Pro

bool

false

`-ho` | `--host`

Specify the hosting model

'webapp' | 'wasm' | 'server'

'webapp'

`--styles`

Whether use NodeJS and Less to compile your custom themes.

`css` | `less`

`css`

`--no-restore`

If specified, skips the automatic restore of the project on create

bool

false

### Option 2: Import Ant Design Blazor into an existing project

-   Go to the project folder of the application and install the Nuget package reference
    
    $ dotnet add package AntDesign
    
-   Register the services in `Program.cs`
    
    builder.Services.AddAntDesign();
    
    or `Startup.cs`
    
    services.AddAntDesign();
    
-   Add namespace in `_Imports.razor`
    
    @using AntDesign
    
-   Introduce CSS and JS files in appropriate places. The WebApp project was introduced in App.razor, and the WebAssembly project was introduced in index.html
    
      <link href\="\_content/AntDesign/css/ant-design-blazor.css" rel\="stylesheet"\>
      <script src\="\_content/AntDesign/js/ant-design-blazor.js"\></script\>
    
-   To display the pop-up component dynamically, you need to add the `<AntContainer />` component in `App.razor`.
    
    -   For Blazor WebApp, you also need to specify render mode to `<Routes />` for interactivity.
    
    <Routes @rendermode="RenderMode.InteractiveAuto" />            <-- specify the rendermode ✨
    + <AntContainer @rendermode="RenderMode.InteractiveAuto" />    <-- add this component ✨
    
    -   For legacy blazor apps just add a line of code:
    
    <Router AppAssembly="@typeof(MainLayout).Assembly">
        <Found Context="routeData">
            <RouteView RouteData="routeData" DefaultLayout="@typeof(MainLayout)" />
        </Found>
        <NotFound>
            <LayoutView Layout="@typeof(MainLayout)">
                <Result Status="404" />
            </LayoutView>
        </NotFound>
    </Router>
    
    +  <AntContainer />   <-- add this component ✨
    
-   Finally, it can be referenced in the `.razor` component!
    
    <Button Type\="@ButtonType.Primary"\>Hello World!</Button\>
    

🔨 Development
--------------

### Gitpod

Click the button below to start a new workspace for development for free.

### Local

-   Install .NET Core SDK 9.0.100 or later.
    
-   Install Node.js (only for building style files and interoperable TypeScript files)
    
-   Clone to local development
    
    $ git clone https://github.com/ant-design-blazor/ant-design-blazor.git
    $ cd ant-design-blazor
    $ npm install
    $ dotnet build ./site/AntDesign.Docs.Build/AntDesign.Docs.Build.csproj
    $ npm start
    
-   Visit https://localhost:5001 in your supported browser and check local development documentation for details.
    
    > Visual Studio 2022 is recommended for development.
    

🔗 Links
--------

-   Ant Design Blazor Documentation
-   Official Blazor Documentation
-   MS Learn for Blazor Tutorial

🗺 Roadmap
----------

Check out this issue to learn about our development plans for the 1.0 release.

You can also find the latest news about the features we will implement in the future with antd5.0 style.

🤝 Contributing
---------------

If you would like to contribute, feel free to create a Pull Request, or give us Bug Report.

💕 Donation
-----------

This project is an MIT-licensed open source project. In order to achieve better and sustainable development of the project, we expect to gain more backers. We will use the proceeds for community operations and promotion. You can support us in any of the following ways:

-   OpenCollective
-   Wechat
-   Alipay

We will put the detailed donation records on the backer list.

❓ Community Support
-------------------

If you encounter any problems in the process, feel free to ask for help via following channels. We also encourage experienced users to help newcomers.

-   
-   Scan QR Code with DingTalk

Contributors
------------

This project exists thanks to all the people who contribute.

Code of Conduct
---------------

This project has adopted the code of conduct defined by the Contributor Covenant to clarify expected behavior in our community. For more information see the .NET Foundation Code of Conduct.

☀️ License
----------

.NET Foundation
---------------

This project is supported by the .NET Foundation.
