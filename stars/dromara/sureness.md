---
project: sureness
stars: 878
description: Dromara Sureness A efficient security framework focus on protection of API. 
url: https://github.com/dromara/sureness
---

Dromara Sureness | 中文文档
=======================

> A efficient security framework that focus on the protection of REST API.

**Home Page: sureness.dromara.org**

**Code Hosting**

| **GitCode** | **Gitee** |**GitHub** |

Introduction
------------

**Dromara Sureness** is a efficient open-source security framework that focus on the protection of REST API.

-   Provide authentication and authorization, based on RBAC.
-   No specific framework dependency (supports Javalin, Spring Boot, Quarkus, Ktor, Micronaut and more).
-   Supports dynamic modification of permissions.
-   Supports WebSockets and HTTP containers (Servlet and JAX-RS).
-   Supports JWT, Basic Auth, Digest Auth, and can custom auth methods.
-   High performance with Dictionary Matching Tree.
-   Good extension interface, demos and documentation.

##### Why Is High Performance

##### Framework Sample Support

-   Sureness integration **Spring Boot** sample(configuration file scheme) sample-bootstrap
-   Sureness integration **Spring Boot** sample(database scheme) sample-tom
-   Sureness integration **Quarkus** sample sample-quarkus
-   Sureness integration **Javalin** sample sample-javalin
-   Sureness integration **Ktor** sample sample-ktor
-   Sureness integration **Spring Webflux** sample sample-spring-webflux
-   Sureness integration **Micronaut** sample sample-micronaut
-   Sureness integration **Jfinal** sample sample-jfinal
-   Sureness integration **Solon** sample sample-solon
-   Sureness integration **Spring Gateway** sample sample-spring-gateway
-   Sureness integration **Zuul** sample sample-zuul
-   Sureness integration Session sample sureness-session
-   Sureness integration Redis Session cache sample sureness-redis-session
-   More samples todo

Security Framework Compare
--------------------------

##### Sureness VS Shiro VS Spring Security

~

Sureness

Shiro

Spring Security

**Multi Framework Support**

support

support need modify

not support

**REST API**

support

support need modify

support

**Websocket**

support

not support

not support

**Path Match**

dictionary matching tree

ant match

ant match

**Annotation Support**

support

support

support

**Servlet**

support

support

support

**JAX-RS**

support

not support

not support

**Dynamic Permissions**

support

support need modify

support need modify

**Performance**

fast

slower

slower

**Learning Curve**

simple

simple

steep

##### Benchmark

**Benchmark test shows Sureness to lose 0.026ms performance compared to frameless application, Shiro lose 0.088ms, Spring Security lose 0.116ms.**  
**In contrast, Sureness basically does not consume performance, and the performance (TPS loss) is 3 times that of Shiro and 4 times that of Spring Security.**  
**The performance gap will be further widened as the api matching chain increases.** Detail see Benchmark Test

Quick Start
-----------

#### Some Conventions

-   Based RBAC, User-Role-Resource.
-   We treat API requests as a resource, resource format like `requestUri===httpMethod`.  
    That is the request uri + request method(`post,get,put,delete...`) is considered as a resource as a whole.  
    `eg: /api/v2/book===get`
-   User belongs some Role -- Role owns Resource -- User can access the resource.

Resource path matching see: URI Match

#### Add Sureness In Your Project

When use maven or gradle build project, add coordinate

```
<dependency>
    <groupId>com.usthe.sureness</groupId>
    <artifactId>sureness-core</artifactId>
    <version>1.1.0</version>
</dependency>
```

```
compile group: 'com.usthe.sureness', name: 'sureness-core', version: '1.1.0'
```

#### Use the Default Configuration to Configure Sureness

The default configuration -`DefaultSurenessConfig` uses the document datasource `sureness.yml` as the auth datasource.  
It supports JWT auth, Basic auth, Digest authentication.

```
@Bean
public DefaultSurenessConfig surenessConfig() {
    return new DefaultSurenessConfig();
}
```

#### Load Auth Config DataSource

Sureness authentication requires us to provide our own account data, role permission data, etc. These data may come from text, relational databases, non-relational databases, annotations, etc.  
We provide interfaces `SurenessAccountProvider`, `PathTreeProvider` for user implement to load data from the dataSource where they want.

-   `SurenessAccountProvider` - Account datasource provider interface.
-   `PathTreeProvider` - Resource uri-role datasource provider interface.

Default Document DataSource Config - `sureness.yml`, see: Default Document DataSource  
Annotation DataSource Config Detail - `AnnotationLoader`, see: Annotation DataSource

If the configuration resource data comes from text, please refer to Sureness integration Spring Boot sample(configuration file scheme)  
If the configuration resource data comes from dataBase, please refer to Sureness integration Spring Boot sample(database scheme)

#### Add an Interceptor Intercepting All Requests

The essence of Sureness is to intercept all rest requests for authenticating and authorizing.  
The interceptor can be a filter or a Spring interceptor, it intercepts all request to check them.

```
SubjectSum subject = SurenessSecurityManager.getInstance().checkIn(servletRequest)
```

#### Implement Auth Exception Handling Process

Sureness uses exception handling process:

-   If auth success, method - `checkIn` will return a `SubjectSum` object containing user information.
-   If auth failure, method - `checkIn` will throw different types of auth exceptions.

Users need to continue the subsequent process based on these exceptions.(eg: return the request response)

Here we need to customize the exceptions thrown by `checkIn`, passed directly when auth success, catch exception when auth failure and do something:

```
try {
    SubjectSum subject = SurenessSecurityManager.getInstance().checkIn(servletRequest);
} catch (ProcessorNotFoundException | UnknownAccountException | UnsupportedSubjectException e4) {
    // Create subject error related execption 
} catch (DisabledAccountException | ExcessiveAttemptsException e2 ) {
    // Account disable related exception
} catch (IncorrectCredentialsException | ExpiredCredentialsException e3) {
    // Authentication failure related exception
} catch (UnauthorizedException e5) {
    // Authorization failure related exception
} catch (SurenessAuthenticationException | SurenessAuthorizationException e) {
    // other sureness exception
}
```

Detail see: Default Sureness Auth Exception

**Have Fun**

Advanced Use
------------

Sureness supports custom subject, custom subjectCreator, custom processor and more.

Before advanced custom extension, let's first understand the general process of Sureness:

As in the above process, Subject is created by SubjectCreate according to the request body, and different authentication processors process the supported Subjects.

Sureness provides the following common interfaces as extension points:

-   `Subject`: Authenticated authorized user's account interface, provide the account's username,password, request resources, roles, etc.
-   `SubjectCreate`: Create subject interface, provider create method.
-   `Processor`: Process subject interface, where happen authentication and authorization.
-   `PathTreeProvider`: Resource data provider, it can load data from txt or database,etc.
-   `SurenessAccountProvider`: Account data provider, it can load data from txt or database,etc.

Refer to Extension Point for the extended documentation.

1.  **Custom Subject**

`Implment Subject, add custom subject content`  
`Implment SubjectCreate to create custom subject`  
`Implment Processor to support custom subject`

See Custom Subject

1.  **Custom SubjectCreator**

`Implment SubjectCreate to create your custom subject`

See Custom SubjectCreator

1.  **Custom Processor**

`A subject also can support by different processor, so we can custom processor to support custom subject` `Implment Processor, set which subject can support and implment processing details`

See Custom Processor

1.  **Custom Datasource**

`Implment PathTreeProvider, load in DefaultPathRoleMatcher`  
`Implment SurenessAccountProvide, load in processor`

See Custom Datasource

Detail please refer to Sureness integration Spring Boot sample(database scheme)

Contributing
------------

Very welcome to Contribute this project, go further and better with Sureness.

Components of Repository:

-   Sureness's kernel code--Sureness-core
-   Sureness integration Spring Boot sample(configuration file scheme)--sample-bootstrap
-   Sureness integration Spring Boot sample(database scheme)-sample-tom
-   Sample projects using Sureness in each framework(Javalin,Ktor,Quarkus)--samples

See CONTRIBUTING

Friend's Links
--------------

-   **`HertzBeat`** An open-source, real-time monitoring system with custom-monitor and agentLess: Github
-   **`JustAuth`** A Java library of third-party authorized login: Github
-   **`MaxKey`** Leading-Edge Enterprise-Class open source IAM Identity and Access management product: Github
-   **`PhalApi`** PHP Api Framework: Website

Join discussion
---------------

QQ Group: 390083213  
Github Discussion  
Gitter Channel

  

License
-------

`Apache License, Version 2.0`

Thanks
------
