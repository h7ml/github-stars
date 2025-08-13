---
project: c-shopping
stars: 2342
description: A beautiful shopping platform developed with Next.js, tailored for various devices including Desktop, Tablet, and Phone. 基于Nextjs开发同时适配Desktop、Tablet、Phone多种设备的精美购物平台
url: https://github.com/huanghanzhilian/c-shopping
---

C-Shopping v1.0.0
=================

README.md
---------

-   en English
-   zh\_CN Simplified Chinese

Hello, everyone! Welcome to C-Shopping, a journey into the world of e-commerce unveiling the technological wonders. I am "Ji Xiaopeng," the open-source author of C-Shopping, and today, I will introduce you to an open-source e-commerce platform based on the latest technologies. Let's explore together!

**Project Live Demo Links:**

-   Docker Deployment Address: http://shop.huanghanlian.com/
-   Vercel Address: https://c-shopping-three.vercel.app/

Project gateway: https://github.com/huanghanzhilian/c-shopping.

**React Native mobile app application:**

Project gateway: https://github.com/huanghanzhilian/c-shopping-rn.

If you find this helpful, please give me a Star. It will be a great encouragement.

* * *

Project Background
------------------

**Background:**

-   Traditional front-end UI frameworks have long been constrained by fixed forms (limited by traditional UI frameworks), leading to visual fatigue. When developing highly customized projects, there is often a sense of powerlessness.
-   Excellent web projects with multi-device adaptation are rare, with high learning and maintenance costs.
-   As projects become complex, dealing with multiple API calls in components can become complicated. For example, managing multiple loading and error states can lead to a declaration of numerous states. Issues like request cancellation and request race conditions are also prone to being overlooked.
-   As the project complexity grows, the development and maintenance of styles become extensive and cumbersome.

**Intent:**

Address the issues mentioned in the background.

**Objective:**

Build a complete, well-designed ecosystem suitable for the web.

* * *

Firstly, let's delve into the technology behind C-Shopping. I have adopted a series of cutting-edge technologies, including Next.js, Tailwind CSS, Headless UI, Redux-Toolkit-RTK Query, JWT, and Docker, among others. This ensures that this project is not only efficient but also highly scalable. We are committed to addressing some pain points of traditional e-commerce platforms: lack of aesthetics, inadequate adaptation to different devices, and a monotonous interface, among others. By adopting the latest technologies and design principles, C-Shopping creates a fully responsive technical development experience for users.

C-Shopping prioritizes user experience. Our interface is not only beautiful but also responsive, allowing users to enjoy shopping easily on any device. The personal center and order management functions also make your shopping experience more personalized and convenient.

* * *

Project Highlights
------------------

One of the highlights of C-Shopping is the adoption of a series of advanced technologies, including Next.js, Tailwind CSS, Headless UI, Redux-Toolkit-RTK Query, etc., providing users with an ultimate performance and experience. We not only focus on aesthetics but also strive for excellence in technology.

**Next.js Driven Lightning-Fast Experience**

C-Shopping uses Next.js, meaning not only is the webpage loading speed incredibly fast, but it also supports server-side rendering, providing an unprecedented level of smoothness.

🎨 **Tailwind CSS Stylish Design**

By using Tailwind CSS, C-Shopping injects a sense of style. Each interface is exquisite, making shopping a visual feast.

🔧 **Headless UI Freedom and Flexibility**

C-Shopping opts for the Headless UI style, giving users more freedom during the shopping process. No longer confined to traditional UI frameworks, it opens more doors for customization.

🔐 **JWT Security Without Worries**

Security is paramount! JWT is used for user authentication, providing the strongest guarantee for your shopping behavior, allowing you to shop with confidence.

🐳 **Docker Perfect Deployment**

C-Shopping embraces Docker, making project deployment incredibly simple. Containerization allows the entire project to run seamlessly in different environments.

🔄 **Redux Toolkit and RTK Query State Management Art**

C-Shopping uses Redux Toolkit and RTK Query, making state management more relaxed and enjoyable. You can better track data flow in the application, ensuring the stability of the shopping experience.

* * *

Feature Demo
------------

Now, let's take a look at some basic features of C-Shopping. From clear navigation and product displays to convenient search and shopping cart features, every detail has been carefully designed to provide users with a pleasant shopping experience.

**User-side**

Module

Desktop devices

Mobile devices

Home

Secondary Category

Third-level Category

Product Details

Login

Register

Search

Shopping Cart

Checkout

User Profile

My Orders

My Reviews

Address Management

Recent Visits

**Admin-side**

Module

Desktop devices

Mobile devices

Login

Admin Center

User Management

Category Management

Category Management Tree

Specification Management

Product Management

Order Management

Review Management

Slider Management

Banner Management

* * *

Project Structure
-----------------

🏗️ **C-Shopping Project Structure:**

**Key structure explanation:**

-   📁 **app**: Main code of the application
    
    -   📁 **main**: Main application components
        -   📁 **client-layout**: Common layout pages for the user side
        -   📁 **empty-layout**: Common blank layout pages
        -   📁 **admin**: Admin pages
        -   📄 **layout.js**: Main layout configuration
        -   📁 **profile**: User profile page
    -   📄 **StoreProvider.js**: Global state management provider
    -   📁 **api**: API request-related routes
        -   📁 **auth**: User authentication API
        -   📁 **banner**: Advertisement banner API
        -   📁 **category**: Product category API
        -   ...
-   📁 **components**: Reusable React components
    
-   📁 **helpers**: Helper functions and tools
    
    -   📁 **api**: API request-related helper functions
    -   📄 **auth.js**: Helper functions related to user authentication
    -   ...
-   📁 **hooks**: Custom React hooks
    
-   📁 **models**: Data model definitions
    
-   📁 **public**: Static resources, such as images, fonts, etc.
    
-   📁 **store**: Configuration related to Redux state management
    
    -   📁 **services**: RTK Query
    -   📁 **slices**: Redux Toolkit
-   📁 **styles**: Style files
    
-   📁 **utils**: General utilities
    
-   ...
    

This structure is designed to make the project organized, easy to maintain, and scalable. Each section is divided based on

functionality and responsibilities, making it easier for team members to understand and collaborate.

* * *

Deployment and Usage
--------------------

**Development Environment**

1.  Clone or download the repository by running the following command in the terminal:
    
    ```
    git clone https://github.com/huanghanzhilian/c-shopping.git
    ```
    
2.  Install project dependencies using npm or yarn:
    
    ```
    npm install
    ```
    
    or
    
    ```
    yarn
    ```
    
3.  Please create a new `.env` file from `.env.example` file in the project root directory to define the required environment variables. This step is crucial (for image upload to OSS):
    
    ```
    NEXT_PUBLIC_ACCESS_TOKEN_SECRET=<your token secret>
    NEXT_PUBLIC_ALI_REGION=<your ali endpoint>
    NEXT_PUBLIC_ALI_BUCKET_NAME=<your ali bucket name>
    NEXT_PUBLIC_ALI_ACCESS_KEY=<your ali access key>
    NEXT_PUBLIC_ALI_SECRET_KEY=<your ali secret key>
    NEXT_PUBLIC_ALI_ACS_RAM_NAME=<your ali acs:ram name>
    NEXT_PUBLIC_ALI_FILES_PATH=<your ali files pathname>
    ```
    
4.  Install MongoDB on your local machine.
    
5.  Run the project:
    
    ```
    npm run dev 
    ```
    
6.  Register an account:
    
    ```
    http://localhost:3000/register
    ```
    
7.  After creating an account, find your account in the database and modify the `root` field to true and the `role` field to admin. This grants you access to all admin dashboard features:
    
    ```
    mongo
    ```
    
    ```
    use choiceshop
    ```
    
    ```
    db.users.update({name:"admin"},{$set:{role:"admin"}})
    db.users.update({name:"admin"},{$set:{root:true}})
    ```
    
    Administrator entrance: http://localhost:3000/admin
    
8.  In MongoDB, create the root category:
    
    ```
    mongo
    ```
    
    ```
    use choiceshop
    ```
    
    ```
    db.categories.insert({
        "name" : "Featured Items",
        "slug" : "choiceshop",
        "image" : "http://huanghanzhilian-test.oss-cn-beijing.aliyuncs.com/shop/upload/image//icons/zHle_bmdM_dhu2K938MMM.webp",
        "colors" : {
            "start" : "#EF394E",
            "end" : "#EF3F55"
        },
        "level" : 0
    })
    ```
    

**Docker Deployment**

The project root directory is already configured with Docker Compose. After installing Docker, simply run the deployment:

```
docker compose up -d --build
```

* * *

Contact Me
----------

I am a technology explorer, a eager learner, and a problem solver.  
我是一个技术的探索者，一个渴望学习的人，一个解决问题的人。

-   Email: h1319639755@gmail.com
-   Twitter: 继小鹏
-   Github: Github
-   Blog: 继小鹏
-   我的中文渠道:
    -   微博：继小鹏1
    -   微信公众号：「继小鹏的博客」
    -   掘金：继小鹏
    -   知乎：继小鹏
    -   即刻：继小鹏
    -   bilibili：继小鹏

### WeChat Official Account | My WeChat

Follow our WeChat Official Account for more information. Feel free to provide any feedback or suggestions by opening an issue or leaving a message on the Official Account. You're also welcome to add me on WeChat for further communication.

My WeChat Official Account

My WeChat

* * *

License
-------

MIT

Copyright (c) 2024 Jipeng Huang

* * *

Call to Action
--------------

C-Shopping is an open-source project, and we welcome more developers to join our community. You can find the project source code on our GitHub repository, suggest improvements, or contribute to development.

If you're interested in the project, feel free to join our community and contribute to the project's growth.
