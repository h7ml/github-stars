---
project: androidx
stars: 5704
description: Development environment for Android Jetpack extension libraries under the androidx namespace. Synchronized with Android Jetpack's primary development branch on AOSP.
url: https://github.com/androidx/androidx
---

Android Jetpack
===============

Jetpack is a suite of libraries, tools, and guidance to help developers write high-quality apps easier. These components help you follow best practices, free you from writing boilerplate code, and simplify complex tasks, so you can focus on the code you care about.

Jetpack comprises the `androidx.*` package libraries, unbundled from the platform APIs. This means that it offers backward compatibility and is updated more frequently than the Android platform, making sure you always have access to the latest and greatest versions of the Jetpack components.

Our official AARs and JARs binaries are distributed through Google Maven.

You can learn more about using it from Android Jetpack landing page.

Contribution Guide
==================

For contributions via GitHub, see the GitHub Contribution Guide.

Note: The contributions workflow via GitHub is currently experimental - only contributions to the following projects are being accepted at this time:

-   Activity
-   AppCompat
-   Biometric
-   Collection
-   Compose Runtime
-   Core
-   DataStore
-   Fragment
-   Lifecycle
-   Navigation
-   Paging
-   Room
-   WorkManager

Code Review Etiquette
---------------------

When contributing to Jetpack, follow the code review etiquette.

Accepted Types of Contributions
-------------------------------

-   Bug fixes - needs a corresponding bug report in the Android Issue Tracker
-   Each bug fix is expected to come with tests
-   Fixing spelling errors
-   Updating documentation
-   Adding new tests to the area that is not currently covered by tests
-   New features to existing libraries if the feature request bug has been approved by an AndroidX team member.

We **are not** currently accepting new modules.

Checking Out the Code
---------------------

Head over to the onboarding docs to learn more about getting set up and the development workflow!

### Continuous integration

Our continuous integration system builds all in progress (and potentially unstable) libraries as new changes are merged. You can manually download these AARs and JARs for your experimentation.

Password and Contributor Agreement before making a change
---------------------------------------------------------

Before uploading your first contribution, you will need setup a password and agree to the contribution agreement:

Generate a HTTPS password: https://android-review.googlesource.com/new-password

Agree to the Google Contributor Licenses Agreement: https://android-review.googlesource.com/settings/new-agreement

Getting reviewed
----------------

-   After you run repo upload, open r.android.com
-   Sign in into your account (or create one if you do not have one yet)
-   Add an appropriate reviewer (use git log to find who did most modifications on the file you are fixing or check the OWNERS file in the project's directory)

Handling binary dependencies
----------------------------

AndroidX uses git to store all the binary Gradle dependencies. They are stored in `prebuilts/androidx/internal` and `prebuilts/androidx/external` directories in your checkout. All the dependencies in these directories are also available from `google()`, or `mavenCentral()`. We store copies of these dependencies to have hermetic builds. You can pull in a new dependency using our importMaven tool.
