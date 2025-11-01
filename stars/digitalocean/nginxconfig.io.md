---
project: nginxconfig.io
stars: 28279
description: ⚙️ NGINX config generator on steroids 💉
url: https://github.com/digitalocean/nginxconfig.io
---

  

### ⚙️ NGINX configuration generator on steroids 💉

The only tool you'll ever need to configure your NGINX server.  
**do.co/nginxconfig »**  
  
Report a bug · Request a feature

  

✨ NGINX Config
==============

NGINX is so much more than just a webserver. You already knew that, probably.

We love NGINX, because:

-   Low memory usage
-   High concurrency
-   Asynchronous event-driven architecture
-   Load balancing
-   Reverse proxying
-   FastCGI support with caching (PHP)
-   Amazing fast handling of static files
-   TLS/SSL with SNI

A lot of features with corresponding configuration directives. You can deep dive into the NGINX documentation right now OR you can use this tool to check how NGINX works, observe how your inputs are affecting the output, and **generate the best config for your specific use-case** (in parallel you can also still use the docs).

🚀 Usage
--------

`GOTO` **`do.co/nginxconfig`**

**Features:** HTTPS, HTTP/2, IPv6, certbot, HSTS, security headers, SSL profiles, OCSP resolvers, caching, gzip, brotli, fallback routing, reverse proxy, www/non-www redirect, CDN, PHP (TCP/socket, WordPress, Drupal, Magento, Joomla), Node.js support, Python (Django) server, etc.

👨‍💻 Author
------------

### Rewrite & Maintenance

**Matt (IPv4) Cowley <me@mattcowley.co.uk\> (https://mattcowley.co.uk)**

-   GitHub: @MattIPv4

### Original version

**Bálint Szekeres <balint@szekeres.me\> (https://balint.szekeres.me)**

-   GitHub: @0xB4LINT
-   LinkedIn: @0xB4LINT

▶️ Development
--------------

1.  Clone the repository
    
    git clone https://github.com/digitalocean/nginxconfig.io.git
    
2.  Install NPM packages
    
    npm ci
    
3.  Run the development server _(with file watchers)_
    
    npm run dev
    
4.  Open the development site **localhost:8080**
    
5.  Lint your code _(eslint & stylelint)_
    
    npm test
    
6.  Build for production _(to the `dist` directory)_
    
    npm run build
    

🤝 Contributing
---------------

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

⚒️ Built With
-------------

-   Vue.js - Template handling & app generation
-   Bulma - Base styling, customised by do-bulma
-   Prism - Bash & NGINX syntax highlighting

📚 Resources
------------

-   Mozilla SSL Configuration Generator v5
-   Mozilla SSL Configuration Generator
-   OWASP TLS Cipher String Cheat Sheet
-   Nginx Optimization: understanding sendfile, tcp\_nodelay and tcp\_nopush
-   NGINX Tuning For Best Performance
-   Hardening Your HTTP Security Headers
-   h5bp/server-configs-nginx
-   Diffie-Hellman DSA-like parameters
-   hstspreload.org
-   Optimal value for nginx worker\_connections

⭐️ Show your support
--------------------

Give a ⭐️ if this project helped you!

📝 License
----------

Copyright © 2020 DigitalOcean, Inc <contact@digitalocean.com\> (https://www.digitalocean.com).  
This project is licensed under the MIT license.
