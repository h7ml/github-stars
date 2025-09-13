---
project: fingerprintjs
stars: 25441
description: The most advanced browser fingerprinting library.
url: https://github.com/fingerprintjs/fingerprintjs
---

FingerprintJS is a source-available, client-side, browser fingerprinting library that queries browser attributes and computes a hashed visitor identifier from them. Unlike cookies and local storage, a fingerprint stays the same in incognito/private mode and even when browser data is purged.

FingerprintJS is available under a BSL license for non-production purposes.

_FingerprintJS is different from Fingerprint Identification, our more detailed and accurate commercial product. See below for more information._

Demo
----

Visit https://fingerprintjs.github.io/fingerprintjs to see your visitor identifier.

Now, try visiting the same page in private / incognito mode and notice how the visitor identifier remains the **same**!

Getting Started
---------------

<script\>
  // Initialize the agent at application startup.
  // If you're using an ad blocker or Brave/Firefox, this import will not work.
  // Please use the NPM package instead: https://t.ly/ORyXk
  const fpPromise \= import('https://openfpcdn.io/fingerprintjs/v4')
    .then(FingerprintJS \=> FingerprintJS.load())

  // Get the visitor identifier when you need it.
  fpPromise
    .then(fp \=> fp.get())
    .then(result \=> {
      // This is the visitor identifier:
      const visitorId \= result.visitorId
      console.log(visitorId)
    })
</script\>

Run this code

### Resources

📕 API Reference

⚛️ Sample usage with React on the StackBlitz platform

🔑 FingerprintJS Licensing

Limitations
-----------

### Accuracy

Since FingerprintJS processes and generates the fingerprints from within the browser itself, the accuracy is limited (40% - 60%). For example, when 2 different users send requests using identical (i.e. same version, same vendor, same platform), browsers, FingerprintJS will not be able to tell these two browsers apart, primarily because the attributes from these browsers will be identical.

### Security

Because of how the fingerprints are processed and generated from within the browser itself, they are vulnerable to spoofing and reverse engineering.

Industry-leading accuracy with Fingerprint Identification
---------------------------------------------------------

The main difference between FingerprintJS and Fingerprint Identification lies in the number of attributes collected from the browser, how they are processed, and the accuracy in identifying visitors.

Fingerprint Identification is a **closed-source**, **commercial** device intelligence platform designed to prevent fraud and improve user experiences. It's an enhanced version of FingerprintJS and has been fully re-designed to solve the most challenging identification use cases. Its source is not available in this or any other public repository.

Unlike FingerprintJS, Fingerprint Identification is able to achieve **industry-leading accuracy** because it processes the browser attributes on the server and also analyzes vast amounts of auxiliary data (e.g. IP addresses, time of visit patterns, URL changes, etc.). Because of these advanced matching techniques, Fingerprint Identification is able to reliably deduplicate different visitors that have identical devices.

Fingerprint Identification is available for Web, Android, iOS, and other platforms. You can easily get started by signing up for a free, unlimited 14-day trial.

Check out our comparison table for a detailed breakdown of the differences between FingerprintJS and Fingerprint Identification.

### Fingerprint Identification resources

🍿 Fingerprint Identification live demo

📕 Fingerprint Identification documentation

▶️ Video: Use Fingerprint Identification to prevent multiple signups by same user

⏱️ How to upgrade from FingerprintJS to Fingerprint Identification in 30 seconds

Migrating to v4
---------------

Migrating from

Migration Guide

Documentation

**v3**

Migrating from v3 to v4

v3 documentation

**v2**

Migrating from v2 to v4

v2 documentation

**v1**

Migrating from v1 to v4

v1 documentation

Version policy
--------------

See the compatibility policy for the API and visitor identifiers in the version policy guide.

Supported browsers
------------------

The library supports all popular browsers. See more details and learn how to run the library in old browsers in the browser support guide.

Where to get support
--------------------

Using Issues and Discussions publicly will help the community and other users with similar issues.

You can also join our Discord server to ask questions, share feedback, and connect with other developers.

If you require private support for FingerprintJS, please email us at oss-support@fingerprint.com.

Contributing
------------

See the Contribution guidelines to learn how to contribute to the project or run the project locally. Please read it carefully before making a pull request.
