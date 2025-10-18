---
project: Authenticator
stars: 4144
description: Authenticator generates 2-Step Verification codes in your browser.
url: https://github.com/Authenticator-Extension/Authenticator
---

Authenticator
=============

> Authenticator generates 2-Step Verification codes in your browser.

Available for Chrome, Firefox, and Microsoft Edge
-------------------------------------------------

### Safari Edition

A Safari edition of Authenticator is available on the App Store. We do not provide official support for the Safari edition.

Build Setup
-----------

# install development dependencies
npm install
# compile
npm run \[chrome, firefox, prod\]

To reproduce a build:

npm ci
npm run prod

To reproduce a build for Safari, please follow contribution guidance in Authenticator-Extension/Authen

Development (Chrome)
--------------------

# install development dependencies
npm install
# compiles the Chrome extension to the \`./test/chrome\` directory
npm run dev:chrome
# load the unpacked extension from the \`./test/chrome/ directory in Chrome

Note that Windows users should download a tool like Git Bash or Cygwin to build.

Acknowledgment
--------------

We would like to extend our heartfelt thanks to Laurent, the Chief Information Security Officer (CISO) of the University of Luxembourg, for the invaluable support and contribution to this project. During the development process, the CISO team provided critical security recommendations that helped us identify and address potential vulnerabilities, significantly enhancing the security and reliability of the project.

We especially want to acknowledge the University of Luxembourg's information security team for their selfless contribution, which not only facilitated the progress of this project but also had a positive impact on the broader open-source community. We recognize that the success of open-source software depends heavily on collaboration and support from various stakeholders, and the involvement of the University of Luxembourg has allowed us to offer a more secure and dependable product to a wider audience.

We understand that while open-source software is free, maintaining and improving these projects requires significant resources. The University of Luxembourg’s information security team has demonstrated their strong commitment to the open-source community, contributing not just within their university but to users and developers globally. We hope this acknowledgment will help them continue to secure the support and resources necessary to further advance open-source initiatives.

Once again, we express our sincere gratitude to the University of Luxembourg's CISO team for their valuable advice and assistance.
