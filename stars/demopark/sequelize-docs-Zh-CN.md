---
project: sequelize-docs-Zh-CN
stars: 3001
description: Sequelize 文档的中文版本:  v7.0.0-alpha.18 | v6.32.0
url: https://github.com/demopark/sequelize-docs-Zh-CN
---

Sequelize Docs 中文版
==================

> 此项目同步自 sequelize / sequelize 项目.
> 
> 更新日志请参阅: CHANGELOG

Sequelize 是一个易用且基于 promise 的 Node.js ORM 工具 适用于 Postgres, MySQL, MariaDB, SQLite, DB2, Microsoft SQL Server, Snowflake, Oracle DB 和 Db2 for IBM i. 它具有强大的事务支持, 关联关系, 预读和延迟加载,读取复制等功能.

Sequelize 遵从 语义版本控制 和 官方 Node.js LTS 版本. Sequelize v7 版本正式支持 Node.js `^14.17,0`, `^16.0.0`. 其他版本或可正常工作.

你目前正在查看 Sequelize 的**教程和指南**.你可能还对API 参考 (英文)感兴趣.

文档版本
----

-   v7 中文文档(开发版本)
    
-   v6 中文文档(保持更新)
    
-   v5 中文文档(停止更新)
    
-   v4 中文文档(停止更新)
    

主要版本变更日志
--------

在此处可以找到主要版本的升级信息：

-   从 v5 升级到 v6
-   从 v6 升级到 v7

文档(v7-alpha)
------------

**注意** 由于当前alpha阶段api调整, 文档中的API参考指向尚未确定. 可前往 V7 API 参考自行查询.

### 核心概念

-   Getting Started - 入门
-   Model Basics - 模型基础
-   Model Instances - 模型实例
-   Model Querying - Basics - 模型查询(基础)
-   Model Querying - Finders - 模型查询(查找器)
-   Getters, Setters & Virtuals - 获取器, 设置器 & 虚拟字段
-   Validations & Constraints - 验证 & 约束
-   Raw Queries - 原始查询
-   Associations - 关联
-   Paranoid - 偏执表

### 高级关联概念

-   Eager Loading - 预先加载
-   Creating with Associations - 创建关联
-   Advanced M:N Associations - 高级 M:N 关联
-   Association Scopes - 关联作用域
-   Polymorphic Associations - 多态关联

### 其它主题

-   Dialect-Specific Things - 方言特定事项
-   Transactions - 事务
-   Hooks - 钩子
-   Query Interface - 查询接口
-   Naming Strategies - 命名策略
-   Scopes - 作用域
-   Sub Queries - 子查询
-   Other Data Types - 其他数据类型
-   Constraints & Circularities - 约束 & 循环
-   Extending Data Types - 扩展数据类型
-   Indexes - 索引
-   Optimistic Locking - 乐观锁定
-   Read Replication - 读取复制
-   Connection Pool - 连接池
-   Working with Legacy Tables - 使用遗留表
-   Migrations - 迁移
-   TypeScript
-   Resources - 资源

安装
--

# 使用 npm
npm install sequelize # 这将安装最新版本的 Sequelize
# 使用 yarn
yarn add sequelize

# 用于支持数据库方言的库:
# 使用 npm
npm i pg pg-hstore # PostgreSQL
npm i mysql2 # MySQL
npm i mariadb # MariaDB
npm i sqlite3 # SQLite
npm i tedious # Microsoft SQL Server
npm i ibm\_db # DB2
npm i odbc # IBM i

# 使用 yarn
yarn add pg pg-hstore # PostgreSQL
yarn add mysql2 # MySQL
yarn add mariadb # MariaDB
yarn add sqlite3 # SQLite
yarn add tedious # Microsoft SQL Server
yarn add ibm\_db # DB2
yarn add odbc # IBM i

简单示例
----

#### TypeScript

import { Sequelize, Model, DataTypes, InferAttributes, InferCreationAttributes } from 'sequelize';

const sequelize \= new Sequelize('sqlite::memory:');

class User extends Model<InferAttributes<User\>, InferCreationAttributes<User\>> {
  declare username: string | null;
  declare birthday: Date | null;
}

User.init({
  username: DataTypes.STRING,
  birthday: DataTypes.DATE
}, { sequelize, modelName: 'user' });

(async () \=> {
  await sequelize.sync();
  const jane \= await User.create({
    username: 'janedoe',
    birthday: new Date(1980, 6, 20),
  });
  console.log(jane.toJSON());
})();

#### JavaScript (CJS)

const { Sequelize, Model, DataTypes } \= require('sequelize');
const sequelize \= new Sequelize('sqlite::memory:');

class User extends Model {}
User.init({
  username: DataTypes.STRING,
  birthday: DataTypes.DATE
}, { sequelize, modelName: 'user' });

(async () \=> {
  await sequelize.sync();
  const jane \= await User.create({
    username: 'janedoe',
    birthday: new Date(1980, 6, 20)
  });
  console.log(jane.toJSON());
})();

请通过 Getting started - 入门 来学习更多相关内容. 如果你想要学习 Sequelize API 请通过 API 参考 (英文).

下载量趋势
-----

近五年Sequelize下载量趋势
