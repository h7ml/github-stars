---
project: crypto-firewall
stars: 20
description: 🎁 Securing your crypto journey, one block at a time.
url: https://github.com/chartingshow/crypto-firewall
---

📈 Charting Show: Crypto Firewall ✅
===================================

Crypto Firewall: Your Digital Shield in the Cryptocurrency Ecosystem

This security-centric repository offers a comprehensive suite of resources and tools designed to fortify your cryptocurrency trading activities and systems. We provide:

-   Cutting-edge best practices
-   Robust scripts and configurations
-   In-depth security guides

Our primary focus is on:

1.  Blocking browser-based crypto mining and cryptojacking attempts
2.  Thwarting banking and crypto malware
3.  Identifying and preventing access to phishing websites and malicious apps
4.  Disrupting hackers' command-and-control (C2) server communications

The Crypto Firewall project is committed to enhancing your safety in the volatile crypto landscape, helping you avoid scams and protect your valuable digital assets. By implementing our strategies, you can trade with confidence and peace of mind.

If you discover a false positive or need to add a new block, then feel free to raise an Issue or a Pull request to **add/remove** them to the lists.

  

Important

**Disclaimer:** New websites are being created all the time to steal cryptocurrencies from users, this is a cat and mouse game and these filter lists are not intended to be a complete solution! User discretion is advised, care and diligence of cyber security to avoid scams are recommended.

Table of Contents 📑
--------------------

-   Installation
    -   Browser Blocking
        -   Recommended Choice
        -   Other Browser Choices
    -   Ad Blockers
        -   Manifest V3: How Google Chrome's Update Affects Ad-Blockers
    -   Perimeter Blocking
    -   Crypto Annoyances (Optional Step)
    -   Operating System Blocking
        -   Hosts based blocking
-   Basic usage
-   Recommended versions
    -   Stable Versions
        -   Lite Version
        -   Full Version
        -   Mega Version
    -   Unstable Beta Version
-   Free DNS / Hosting blocking
-   Bad Browser Extensions & Package Names blocking
-   Autonomous System Number (ASN) blocking
-   IP blocking
    -   Custom IP Block Lists
-   Email blocking
-   Nuisance and scam calling telephone numbers blocking
-   Fraudulent cryptocurrency wallet addresses
-   Fraudulent cryptocurrency mining pool addresses
-   OFAC sanctioned digital currency addresses
    -   How do we define sanctions data?
-   Modules
-   Issues
-   Changelog
-   If you like the Charting Show project
    -   Sponsors
    -   Backers
-   Contributions, Feature Requests and Feedback
-   Requesting icon
-   Security
-   Semantic Versioning
-   Legal
-   Copyright and License
    -   Many Thanks to all the `Stargazers` who have supported this project with stars

Installation ❤️
---------------

Choose where to deploy the crypto firewall at the browser level, operating system level, and/or network perimeter - for layered, comprehensive protection.

### Browser Blocking 🌟

Install an ad blocker in your desktop or mobile browser that uses the Adblock Plus' filter list:

#### Recommended Choice ⭐

Brave Browser offers built-in ad and tracker blocking, making it an excellent choice for enhanced privacy and security.

-   **Brave Desktop Browser Instructions Guide** - Provides robust privacy features, including a built-in ad blocker and Tor integration for anonymous browsing.
    
-   **Brave Mobile Browser Instructions Guide** - Offers similar privacy protections on mobile devices.
    

#### Other Browser Choices ✨

Explore additional secure browsers like Firefox, Opera and Carbon Browser, each offering unique features such as ad-blocking, privacy enhancements and cryptocurrency support.

-   **AdBlock Browser Instructions Guide** - Is a fast, secure, and ad-free web browser developed by the Adblock Plus team.
    
-   **Opera Browser** - Includes ad blocking by default since Opera 50.
    
-   **Chrome Browser** - Includes Manifest V3 by default limiting adblocker rules to only 30,000. Is the most popular browser used on the internet.
    
-   **Vivaldi Browser Instructions Guide** - Browse with desktop-style tabs, block ads and trackers, and sync data between devices safely.
    

### Ad Blockers ☀️

You can use these blocklists with popular adblockers like uBlock Origin, AdAway, Blokada, AdBlock Plus and others to block malicious crypto-related domains and trackers.

-   **AdAway Instructions Guide** - Is a free and open-source ad-blocking application for the Android mobile operating system.
    
-   **AdBlock Instructions Guide** - Is a user-supported browser extension that lets you surf the web ad-free.
    
-   **AdBlock Plus Instructions Guide** - Popular ad-blocking extension for various browsers.
    
-   **AdGuard Instructions Guide** - Comprehensive ad and tracker blocking solution.
    
-   **Blokada Android Instructions Guide** and **Blokada iOS Instructions Guide** - Block ads and trackers in apps and games, comes with a fast and private DNS and VPN.
    
-   **DNS66 Instructions Guide** - Is a DNS-based host blocker for Android.
    
-   **uBlock Origin (Manifest V2) Instructions Guide** - Efficient, wide-spectrum content blocker.
    
-   **uBlock Origin Lite (Manifest V3) Instructions Guide** - Is a _permission-less_ MV3-based content blocker.
    

#### Manifest V3: How Google Chrome's Update Affects Ad-Blockers 🇬

Google Chrome's Manifest V3, rolled out in June 2024, will significantly impact ad-blockers and other browser extensions. This update limits extensions to 30,000 rules, far below the 300,000 rules many ad-blockers currently use to function effectively. The change from the webRequest API to the declarativeNetRequest API will reduce ad-blockers' flexibility and ability to update rules in real-time.

While some ad-blockers like AdGuard, uBlock Origin Lite and Ghostery have adapted to Manifest V3, users may notice decreased effectiveness in blocking ads. This move has sparked controversy, with critics arguing it gives Google more control over extensions and potentially benefits its advertising business. As a result, some users are considering alternative browsers like Firefox, which has committed to continuing support for Manifest V2.

### Perimeter Blocking 🔓

You may use the hosts file with below applications to block these miners on whole networks. Simply add the link to the above hosts file in each system.

-   **Bind RPZ Instructions Guide** - Is a DNS firewall feature supported by BIND. It allows rewriting or blocking DNS responses for specific domains based on a configured policy - like redirecting `malware-site.com` to `127.0.0.1`.
    
-   **Bind Zone Instructions Guide** - Is simply a DNS zone file - it defines DNS records (A, MX, CNAME, etc.) for a domain or set of domains, usually for authoritative DNS services.
    
-   **Blocky Instructions Guide** - Is a DNS proxy and ad-blocker for the local network written in Go.
    
-   **Dnscrypt-Proxy Instructions Guide** - Is a flexible DNS proxy, with support for modern encrypted DNS protocols such as DNSCrypt v2, DNS-over-HTTPS, Anonymized DNSCrypt and ODoH (Oblivious DoH).
    
-   **Dnsmasq Android Instructions Guide** and **Dnsmasq Linux Instructions Guide** and **Dnsmasq Mac OS Instructions Guide** and **Dnsmasq Windows Instructions Guide** - Provides network infrastructure for small networks: DNS, DHCP, router advertisement and network boot.
    
-   **NextDNS Instructions Guide** - Protects you from all kinds of security threats, blocks ads and trackers on websites and in apps and provides a safe and supervised Internet for kids - on all devices and on all networks.
    
-   **pfSense with pfBlockerNG Instructions Guide** - Provides firewall capabilities by allowing users to filter both inbound and outbound traffic using IP and DNS blocklists.
    
-   **Pi-hole Instructions Guide** - Provides a Linux network-level advertisement and Internet tracker blocking application which acts as a DNS sinkhole and optionally a DHCP server, intended for use on a private network.
    
-   **Snort3 Instructions Guide** - Is a high-performance, open-source network intrusion detection and prevention system (IDS/IPS) that analyzes traffic in real time to detect and block malicious activity.
    
-   **Suricata Linux & Mac OS Instructions Guide** and **Suricata Windows Instructions Guide** - Is an open-source intrusion detection system (IDS) and intrusion prevention system (IPS) developed by the Open Information Security Foundation (OISF).
    
-   **Suricata SNI Linux Instructions Guide** and **Suricata SNI Mac OS Instructions Guide** and **Suricata SNI Windows Instructions Guide** - Refers to Suricata's ability to inspect TLS (encrypted) traffic and extract the Server Name Indication (SNI) - the domain name requested during HTTPS connections-enabling visibility and filtering of encrypted traffic based on domain names.
    

### Crypto Annoyances (Optional Step) 🚀

This filter list blocks cryptocurrency-related annoyances and unwanted content by removing URL tracking parameters (like `utm_`) and cookie banners, hiding promoted social media posts, eliminating TradingView popups / notifications / telemetry, stripping compliance banners from exchanges (Binance, Coinbase, etc.) and cleaning up crypto sites (CoinGecko, CoinMarketCap) by removing ads, banners and promotional feeds-resulting in a streamlined browsing experience free of distractions and tracking.

-   **Block Crypto Annoyances Filter List** - Increase productivity by removing cryptocurrency-related annoyances and unwanted content.

### Operating System Blocking 🌟

For system-wide protection, consider modifying your device's hosts file:

-   **Linux Hosts File Instructions Guide** - Edit the hosts file to block unwanted domains at the system level.
    
-   **MacOS Hosts File Instructions Guide** - Modify the hosts file to prevent access to specific websites and services.
    
-   **Windows Hosts File Instructions Guide** - Update the hosts file to block connections to undesired IP addresses.
    

#### Hosts based blocking 💢

For the blocking based on the HOSTS file use the below link:

-   https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/hosts-domains-only.txt
-   https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/hosts-domains-and-ips.txt

Here's a simple guide on how to access your hosts file on Linux, macOS and Windows.

Basic usage 🔥
--------------

For a thorough explanation on how to add the to your adblocker, open one of the help guides found in this folder:

-   https://github.com/chartingshow/crypto-firewall/tree/master/docs

Recommended versions ✅
----------------------

The firewall is known to reduce performance slightly and this is why we have several **different** versions.

Here's a suggested guide based on cpu processors:

-   **Intel i3** - use `full` version (if you experience bad performance then try `lite` version instead).
    
-   **Intel i5** - use `full` version (if you experience bad performance then try `lite` version instead).
    
-   **Intel i7** - use `mega` version (if you experience bad performance then try `full` version instead).
    
-   **Intel i9** - use `beta` or `mega` versions (if you experience bad performance then try `full` version instead).
    
-   **AMD Ryzen 3** - use `lite` version (if you experience bad performance then try `full` version instead).
    
-   **AMD Ryzen 5** - use `full` version (if you experience bad performance then try `lite` version instead).
    
-   **AMD Ryzen 7** - use `mega` version (if you experience bad performance then try `full` version instead).
    
-   **AMD Ryzen 9** - use `beta` or `mega` versions (if you experience bad performance then try `full` version instead).
    

Here's a suggested guide based on device:

-   **Laptop** or **Computer** - use `beta` or `mega` versions (if you experience bad performance then try `full` version instead).
-   **Tablet** - use `mega` or `full` versions (if you experience bad performance then try `full` version instead).
-   **Powerful Smartphone** - use `full` version (if you experience bad performance then try `lite` version instead).
-   **Low-End Smartphone** - use `lite` version.

### Stable Versions 🏆

#### Lite Version

The `Lite` version **excludes all the modules**.

There are two methods to install into your adblocker:

1.  Click the link below:

-   https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/lite-version.txt&title=Crypto%20Fireall%20Lite%20Version

1.  Copy and paste the link in the settings of the ad-blocker:

-   https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/lite-version.txt

#### Full Version

The `Full` version **contains all the modules (except the crypto annoyances (stable), domains (stable), subdomains (stable), urls (stable) and adverts-filters (unstable) modules)**.

There are two methods to install into your adblocker:

1.  Click the link below:

-   https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/full-version.txt&title=Crypto%20Fireall%20Full%20Version

1.  Copy and paste the link in the settings of the ad-blocker:

-   https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/full-version.txt

#### Mega Version

The `Mega` version **contains all the modules (except adverts-filters (unstable) module)**.

There are two methods to install into your adblocker:

1.  Click the link below:

-   https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/mega-version.txt&title=Crypto%20Fireall%20Mega%20Version

1.  Copy and paste the link in the settings of the ad-blocker:

-   https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/mega-version.txt

### Unstable Beta Version ⚠️

The `Beta` version **contains all the stable and unstable modules**.

> To help the repo grow, please feel free to **report any bugs!**

There are two methods to install into your adblocker:

1.  Click the link below:

-   https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/beta-version.txt&title=Crypto%20Fireall%20Beta%20Version

1.  Copy and paste the link in the settings of the ad-blocker:

-   https://raw.githubusercontent.com/chartingshow/crypto-firewall/master/src/blacklists/beta-version.txt

Free DNS / Hosting blocking 🆓
------------------------------

This repo blocks specific free dns / hosting services, that are completely saturated with hosting malware and viruses. This is to reduce the size of the filter lists and increase the performance. A list of services currently blocked can be found in the folder here:

-   Free DNS/Hosting Filter List

Bad Browser Extensions & Package Names blocking 👨‍💻
-----------------------------------------------------

Malicious browser extensions pose critical risks by enabling cybercriminals to hijack browsing sessions, steal sensitive credentials and establish persistent access. These threats often masquerade as legitimate tools while exfiltrating cookies, authentication tokens and financial data.

Malicious apps are a method of manipulating users into downloading malware that allows cybercriminals to steal personal information, including login credentials or payment information. It's also possible that they can even take control of a user's device. A list of bad browser extensions and malicious package names currently blocked can be found in the following folder:

-   Bad Browser Extensions & Package Names Folder

Autonomous System Number (ASN) blocking 🗃️
-------------------------------------------

An Autonomous System Number (ASN) is a globally unique 16-digit identification number assigned by the Internet Assigned Numbers Authority (IANA) to Autonomous Systems (AS). ASNs are crucial for routing within networks and exchanging routing information with other Internet Service Providers. Autonomous systems numbered one to 64511 are available by IANA for global use. The 64512 to 65535 series is reserved for private and reserved purposes.

An Autonomous System Number (ASN) can also be blocked, be aware that ASN's contain a load of ip addresses assigned to them. You can add them to a firewall of your choice.

The ASN block list can be found here:

-   ASN Filter List

IP blocking 🌐
--------------

IP Addresses can also be blocked, these contain things such as command-and-control (C2) servers for crypto malware etc. You can add them to a firewall of your choice.

The IP block list can be found here:

-   IP Filter List
-   IP Filter AdBlock List

For a thorough explanation on how to add block an ip address in your firewall, you can open one of the help guides found in this folder:

-   https://github.com/chartingshow/crypto-firewall/tree/master/docs

### Custom IP Block Lists 📋

These custom IP address filter lists block specific malware and can be found in the folder:

-   https://github.com/chartingshow/crypto-firewall/tree/master/src/blacklists/custom-ip-block-lists

> The reason why these custom lists aren't in the main IP filter list is because these IP addresses maybe shared and used for public access or hosting multiple domains! These custom IP address filter lists are for advanced users who can customize them in order to not block their access or applications.

Email blocking 📧
-----------------

Email addresses can be blocked, our email block list contains known Crypto scammers, Ransomware, Sextortion and Blackmail email addresses.

The Email block list can be found here:

-   Email Filter List

To learn how to protect yourself from Sextortion emails, see here:

-   https://github.com/chartingshow/crypto-firewall/blob/master/docs/scams/how-to-protect-yourself-from-sextortion-scams.md

How to Identify a Ransomware Email Attack, see here:

-   https://github.com/chartingshow/crypto-firewall/blob/master/docs/scams/how-to-identify-a-ransomware-email-attack.md

Nuisance and scam calling telephone numbers blocking ☎️
-------------------------------------------------------

It's essential to note that tech support scammers often use spoofed or fake numbers to disguise their true location and identity. These numbers may appear legitimate, but they are actually being used to perpetuate fraudulent activities.

Remember, if you receive a suspicious call or message claiming to be from technical support, hang up immediately and do not provide any personal or financial information. Report the incident to the relevant authorities and take steps to secure your device.

A list of spam blocking mobile apps can be found here:

-   Mobile Apps To Block Spam Calls

Fraudulent cryptocurrency wallet addresses 🕵️
----------------------------------------------

Avoid sending cryptocurrency to bad actors and scammers, a list of bad blockchain wallet addresses can be found here in this folder:

-   Wallets Filter List

Fraudulent cryptocurrency mining pool addresses 🦈
--------------------------------------------------

Avoid joining bad cryptocurrency mining pools, a list of bad blockchain mining pool addresses can be found here in this folder:

-   Mining Pools Filter List

OFAC sanctioned digital currency addresses 🚫
---------------------------------------------

OFAC publishes lists of individuals and companies owned or controlled by, or acting for or on behalf of, targeted countries. It also lists individuals, groups and entities, such as terrorists and narcotics traffickers designated under programs that are not country-specific. OFAC may add **digital currency addresses** to the SDN List to alert the public of specific **digital currency identifiers** associated with a blocked person.

The OFAC Sanctioned Digital Currency Addresses lists can be found in this folder:

-   OFAC Filter List

### How do we define sanctions data?

Sanctioned entities refer to entities listed on economic/trade embargo lists, such as by the US, EU, or UN, with which anyone subject to those jurisdictions is prohibited from dealing. Currently, this includes the Specially Designated Nationals (SDN) list of the US Department of the Treasury's Office of Foreign Assets Control (OFAC).

You can search the full list of OFAC Specially Designated Nationals in OFAC's sanctions database.

Modules ⚙️
----------

This repo contains various filter list modules, which users can check out in the following folders:

-   Abuse Filter List
-   Ad Server Filter List
-   Adverts Filter List
-   Botnet Filter List
-   Domain Filter List
-   Fake News Filter List
-   Fraud Filter List
-   Malicious Filter List
-   Malware Filter List
-   Phishing Filter List
-   Phishing Other Filter List
-   PUP Filter List
-   Pig Butchering Filter List
-   Ransomware Filter List
-   Scam Filter List
-   Subdomain Filter List
-   Tracking Filter List **(Note: This filter list blocks javascript files found on many websites and stop things from working correctly)**
-   Url Filter List
-   URLhaus Filter List

* * *

_Mining (Opt-in **and** opt-out) will be blocked by default. If you see that mining is important, you would have to whitelist the website you actually want to support._

Issues 🔨
---------

If you face any issue, you can create a new issue in the `Issues` tab and we will be glad to help you out!

Changelog 🏆
------------

Please see CHANGELOG for more information what has changed recently.

If you like the Charting Show project 💗💗💗
--------------------------------------------

If you like Charting Show you can support the project's improvements and development of new features with a donation to our collective.

👉 https://opencollective.com/chartingshow

### Sponsors ✨

Support us by becoming a sponsor. Your logo will show up here with a link to your website. \[Become a sponsor\]

### Backers ✨

Thank you to all our backers! 🙏 \[Become a backer\]

Contributions, Feature Requests and Feedback ✨
----------------------------------------------

This project exists thanks to all the people who contribute.

We are actively inviting new contributors! To start, please read the contribution guide.

This project is only possible thanks to the work of many dedicated volunteers. Everyone is encouraged to help in ways large and small. Here are a few ways you can help:

-   Read the current content and help us fix any spelling mistakes or grammatical errors.
-   Choose an existing issue on GitHub and submit a pull request to fix it.
-   Open a new issue to report an opportunity for improvement.

If you find any bugs in the code or have any improvements in mind then feel free to generate a pull request.

Requesting icon 🎁
------------------

When you want to request a icon please feel feel to create a issue. See our contribution guidelines for more information.

Security 💥
-----------

If you discover any security related issues, please open an issue! We will try and sort it out asap.

Semantic Versioning 🎁
----------------------

This package uses: Semantic Versioning.

Legal 🔨
--------

All logos and trademarks are the property of their respective owners.

Copyright and License 📄
------------------------

Copyright (c) Charting Show. All rights reserved.

Everyone is permitted to copy and distribute copies of Charting Show, but changing and hard forking are not allowed.

### Many Thanks to all the `Stargazers` who have supported this project with stars(⭐)

⬆ back to top

Made with ❤️ for the Decentralized World.
