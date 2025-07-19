---
project: pangolin
stars: 12882
description: Tunneled Reverse Proxy Server with Identity and Access Control and Dashboard UI
url: https://github.com/fosrl/pangolin
---

#### Secure gateway to your private networks

_Pangolin tunnels your services to the internet so you can access anything from anywhere._

##### Website | Install Guide | Contact Us

**Start testing Pangolin at pangolin.fossorial.io**

Pangolin is a self-hosted tunneled reverse proxy server with identity and access control, designed to securely expose private resources on distributed networks. Acting as a central hub, it connects isolated networks — even those behind restrictive firewalls — through encrypted tunnels, enabling easy access to remote services without opening ports.

Key Features
------------

### Reverse Proxy Through WireGuard Tunnel

-   Expose private resources on your network **without opening ports** (firewall punching).
-   Secure and easy to configure private connectivity via a custom **user space WireGuard client**, Newt.
-   Built-in support for any WireGuard client.
-   Automated **SSL certificates** (https) via LetsEncrypt.
-   Support for HTTP/HTTPS and **raw TCP/UDP services**.
-   Load balancing.
-   Extend functionality with existing Traefik plugins, such as CrowdSec and Geoblock.
    -   **Automatically install and configure Crowdsec via Pangolin's installer script.**
-   Attach as many sites to the central server as you wish.

### Identity & Access Management

-   Centralized authentication system using platform SSO. **Users will only have to manage one login.**
-   **Define access control rules for IPs, IP ranges, and URL paths per resource.**
-   TOTP with backup codes for two-factor authentication.
-   Create organizations, each with multiple sites, users, and roles.
-   **Role-based access control** to manage resource access permissions.
-   Additional authentication options include:
    -   Email whitelisting with **one-time passcodes.**
    -   **Temporary, self-destructing share links.**
    -   Resource specific pin codes.
    -   Resource specific passwords.
    -   Passkeys
-   External identity provider (IdP) support with OAuth2/OIDC, such as Authentik, Keycloak, Okta, and others.
    -   Auto-provision users and roles from your IdP.

Use Cases
---------

### Manage Access to Internal Apps

-   Grant users access to your apps from anywhere using just a web browser. No client software required.

### Developers and DevOps

-   Expose and test internal tools and dashboards like **Grafana**. Bring localhost or private IPs online for easy access.

### Secure API Gateway

-   One application load balancer across multiple clouds and on-premises.

### IoT and Edge Devices

-   Easily expose **IoT devices**, **edge servers**, or **Raspberry Pi** to the internet for field equipment monitoring.

Deployment Options
------------------

### Fully Self Hosted

Host the full application on your own server or on the cloud with a VPS. Take a look at the documentation to get started.

> Many of our users have had a great experience with RackNerd. Depending on promotions, you can get a **VPS with 1 vCPU, 1GB RAM, and ~20GB SSD for just around $12/year**. That's a great deal!

### Pangolin Cloud

Easy to use with simple pay as you go pricing. Check it out here.

-   Everything you get with self hosted Pangolin, but fully managed for you.

### Hybrid & High Availability

Managed control plane, your infrastructure

-   We manage database and control plane.
-   You self-host lightweight exit-node.
-   Traffic flows through your infra.
-   We coordinate failover between your nodes or to Cloud when things go bad.

If interested, contact us.

### Full Enterprise On-Premises

Contact us for a full distributed and enterprise deployments on your infrastructure controlled by your team.

Project Development / Roadmap
-----------------------------

We want to hear your feature requests! Add them to the discussion board.

Licensing
---------

Pangolin is dual licensed under the AGPL-3 and the Fossorial Commercial license. For inquiries about commercial licensing, please contact us at numbat@fossorial.io.

Contributions
-------------

Looking for something to contribute? Take a look at issues marked with help wanted.

Please see CONTRIBUTING in the repository for guidelines and best practices.

Please post bug reports and other functional issues in the Issues section of the repository.
