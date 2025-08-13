---
project: AutoMate
stars: 292
description: Swift framework containing a set of helpful XCTest extensions for writing UI automation tests
url: https://github.com/PGSSoft/AutoMate
---

  

**AutoMate** • AppBuddy • Templates • ModelGenie

AutoMate
========

`AutoMate` is a Swift framework containing a set of helpful `XCTest` extensions for writing UI automation tests. It provides strongly typed, extensible wrapper around launch arguments and environment variables, which can be used for language, locale and keyboard type configuration on the device. With the `AutoMate-AppBuddy` it can also disable animations in the application and manage events, reminders and contacts.

Installation
------------

There are three convinient ways to install AutoMate:

-   using CocoaPods with Podfile:
    
     pod 'AutoMate'
    
-   using Carthage and add a line to `Cartfile.private`:
    
    ```
     github "PGSSoft/AutoMate"
    ```
    
    `Cartfile.private` should be used because AutoMate framework will be used by UI Tests target only not by the tested application.
    
-   using Swift Package Manager, either via Xcode or in `Package.swift`:
    
     .package(url: "https://github.com/PGSSoft/AutoMate", from: "1.8.0"),
    

Usage
-----

Full documentation is available at https://pgssoft.github.io/AutoMate/.

1.  Create a new UI test case class.
    
2.  Import `AutoMate` framework to UI tests files:
    
    import AutoMate
    
3.  Use `TestLauncher` in the `setup()` method to configure application settings and launch the application:
    
    let app \= XCUIApplication()
    TestLauncher(options: \[
        SystemLanguages(\[.English, .German\]),
        SystemLocale(language: .English, country: .Canada),
        SoftwareKeyboards(\[.EnglishCanada, .GermanGermany\])
    \]).configure(app).launch()
    
4.  Use AutoMate's extensions in your tests. For example:
    
    func testSomething() {
        let app \= XCUIApplication()
        let button \= app.button.element
    
        // helper for waiting until element is visible
        waitForVisibleElement(button, timeout: 20)
        button.tap()
    
        // isVisible - helper to check that element both exists and is hittable
        XCTAssertFalse(button.isVisible)
    }
    

Features (or ToDo)
------------------

-   Set keyboards
-   Set locale
-   Set languages
-   Custom arguments
-   Custom keyboards, locales and languages
-   `XCTest` extensions
-   Added CoreData launch arguments
-   Disable UIView animations (with `AutoMate-AppBuddy`)
-   Strong-typed helpers: locators, page object templates (with `AutoMate-Templates`)
-   Base XCTestCase template (with `AutoMate-Templates`)
-   Most permissions alerts (like: `LocationWhenInUseAlert`, `CalendarAlert`, `PhotosAlert`) (with `AutoMate-ModelGenie`)
-   Managing events, reminders and contacts (with `AutoMate-AppBuddy`)
-   Companion library for the application (`AutoMate-AppBuddy`)
-   Improve launch options type safety
-   Smart coordinates
-   Check if application is running in UI test environment (with `AutoMate-AppBuddy`)
-   Stubbing network requests
-   Stubbing contacts, events and reminders
-   Taking screenshots
-   Clearing application data
-   Stubbing notifications

Example application
-------------------

Repository contains example application under `AutoMateExample` directory. Structure of the application is simple, but the project contains extensive suite of UI tests to showcase capabilities of the library.

Development
-----------

Full documentation is available at https://pgssoft.github.io/AutoMate/.

If you want to provide your custom launch argument or launch environment you have to implement `LaunchOption` protocol or one of its extensions, such as `LaunchArgumentWithSingleValue`:

enum CustomParameter: String, LaunchArgumentWithSingleValue, LaunchArgumentValue {
    var key: String {
        return "AppParameter"
    }
    case value1
    case value2
}

Then, you can pass it to the `TestBuilder`:

let launcher \= TestLauncher(options: \[
    CustomParameter.value1
\])

Contributing
------------

Bug reports and pull requests are welcome on GitHub at https://github.com/PGSSoft/AutoMate.

License
-------

The project is available as open source under the terms of the MIT License.

About
-----

The project maintained by software development agency PGS Software. See our other open-source projects or contact us to develop your product.

Follow us
---------
