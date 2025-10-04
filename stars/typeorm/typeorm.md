---
project: typeorm
stars: 35842
description: ORM for TypeScript and JavaScript. Supports MySQL, PostgreSQL, MariaDB, SQLite, MS SQL Server, Oracle, SAP Hana, WebSQL databases. Works in NodeJS, Browser, Ionic, Cordova and Electron platforms.
url: https://github.com/typeorm/typeorm
---

  
  
  
  

TypeORM is an ORM that can run in Node.js, Browser, Cordova, Ionic, React Native, NativeScript, Expo, and Electron platforms and can be used with TypeScript and JavaScript (ES2021). Its goal is to always support the latest JavaScript features and provide additional features that help you to develop any kind of application that uses databases - from small applications with a few tables to large-scale enterprise applications with multiple databases.

TypeORM supports more databases than any other JS/TS ORM: Google Spanner, Microsoft SqlServer, MySQL/MariaDB, MongoDB, Oracle, Postgres, SAP HANA and SQLite, as well we derived databases and different drivers.

TypeORM supports both Active Record and Data Mapper patterns, unlike all other JavaScript ORMs currently in existence, which means you can write high-quality, loosely coupled, scalable, maintainable applications in the most productive way.

TypeORM is highly influenced by other ORMs, such as Hibernate, Doctrine and Entity Framework.

Features
--------

-   Supports both DataMapper and ActiveRecord (your choice).
-   Entities and columns.
-   Database-specific column types.
-   Entity manager.
-   Repositories and custom repositories.
-   Clean object-relational model.
-   Associations (relations).
-   Eager and lazy relations.
-   Unidirectional, bidirectional, and self-referenced relations.
-   Supports multiple inheritance patterns.
-   Cascades.
-   Indices.
-   Transactions.
-   Migrations and automatic migrations generation.
-   Connection pooling.
-   Replication.
-   Using multiple database instances.
-   Working with multiple database types.
-   Cross-database and cross-schema queries.
-   Elegant-syntax, flexible and powerful QueryBuilder.
-   Left and inner joins.
-   Proper pagination for queries using joins.
-   Query caching.
-   Streaming raw results.
-   Logging.
-   Listeners and subscribers (hooks).
-   Supports closure table pattern.
-   Schema declaration in models or separate configuration files.
-   Supports MySQL / MariaDB / Postgres / CockroachDB / SQLite / Microsoft SQL Server / Oracle / SAP Hana / sql.js.
-   Supports MongoDB NoSQL database.
-   Works in Node.js / Browser / Ionic / Cordova / React Native / NativeScript / Expo / Electron platforms.
-   TypeScript and JavaScript support.
-   ESM and CommonJS support.
-   Produced code is performant, flexible, clean, and maintainable.
-   Follows all possible best practices.
-   CLI.

And more...

With TypeORM, your models look like this:

import { Entity, PrimaryGeneratedColumn, Column } from "typeorm"

@Entity()
export class User {
    @PrimaryGeneratedColumn()
    id: number

    @Column()
    firstName: string

    @Column()
    lastName: string

    @Column()
    age: number
}

And your domain logic looks like this:

const userRepository \= MyDataSource.getRepository(User)

const user \= new User()
user.firstName \= "Timber"
user.lastName \= "Saw"
user.age \= 25
await userRepository.save(user)

const allUsers \= await userRepository.find()
const firstUser \= await userRepository.findOneBy({
    id: 1,
}) // find by id
const timber \= await userRepository.findOneBy({
    firstName: "Timber",
    lastName: "Saw",
}) // find by firstName and lastName

await userRepository.remove(timber)

Alternatively, if you prefer to use the `ActiveRecord` implementation, you can use it as well:

import { Entity, PrimaryGeneratedColumn, Column, BaseEntity } from "typeorm"

@Entity()
export class User extends BaseEntity {
    @PrimaryGeneratedColumn()
    id: number

    @Column()
    firstName: string

    @Column()
    lastName: string

    @Column()
    age: number
}

And your domain logic will look this way:

const user \= new User()
user.firstName \= "Timber"
user.lastName \= "Saw"
user.age \= 25
await user.save()

const allUsers \= await User.find()
const firstUser \= await User.findOneBy({
    id: 1,
})
const timber \= await User.findOneBy({
    firstName: "Timber",
    lastName: "Saw",
})

await timber.remove()

Samples
-------

Take a look at the samples in sample for examples of usage.

There are a few repositories that you can clone and start with:

-   Example how to use TypeORM with TypeScript
-   Example how to use TypeORM with JavaScript
-   Example how to use TypeORM with JavaScript and Babel
-   Example how to use TypeORM with TypeScript and SystemJS in Browser
-   Example how to use TypeORM with TypeScript and React in Browser
-   Example how to use Express and TypeORM
-   Example how to use Koa and TypeORM
-   Example how to use TypeORM with MongoDB
-   Example how to use TypeORM in a Cordova app
-   Example how to use TypeORM with an Ionic app
-   Example how to use TypeORM with React Native
-   Example how to use TypeORM with Nativescript-Vue
-   Example how to use TypeORM with Nativescript-Angular
-   Example how to use TypeORM with Electron using JavaScript
-   Example how to use TypeORM with Electron using TypeScript

Extensions
----------

There are several extensions that simplify working with TypeORM and integrating it with other modules:

-   TypeORM integration with TypeDI
-   TypeORM integration with routing-controllers
-   Models generation from the existing database - typeorm-model-generator
-   Fixtures loader - typeorm-fixtures-cli
-   ER Diagram generator - typeorm-uml
-   another ER Diagram generator - erdia
-   Create, drop and seed database - typeorm-extension
-   Automatically update `data-source.ts` after generating migrations/entities - typeorm-codebase-sync
-   Easy manipulation of `relations` objects - typeorm-relations
-   Automatically generate `relations` based on a GraphQL query - typeorm-relations-graphql
-   Generate TypeORM entities from Valibot schemas - piying-orm

Contributing
------------

Learn about contribution here and how to set up your development environment here.

This project exists thanks to all the people who contribute:

Sponsors
--------

Open source is hard and time-consuming. If you want to invest in TypeORM's future, you can become a sponsor and allow our core team to spend more time on TypeORM's improvements and new features. Become a sponsor

Gold Sponsors
-------------

Become a gold sponsor and get premium technical support from our core contributors. Become a gold sponsor
