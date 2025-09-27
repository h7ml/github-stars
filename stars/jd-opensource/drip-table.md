---
project: drip-table
stars: 1643
description: A tiny and powerful enterprise-class solution for building lowcode tables. 轻量、强大的企业级表格可视化搭建解决方案。
url: https://github.com/jd-opensource/drip-table
---

Drip Table
==========

English | 简体中文 | Documentation | Discussions｜Gitter | Official Wechat group

📖 Introduction
---------------

`Drip Table`is a dynamic table solution for enterprise level middle and background launched by JD retail. The project is based on `React` and `JSON Schema` . It aims to reduce the difficulty of developing table and improve work efficiency by `simple configuration` to quickly generate page dynamic table.

`Drip Table` contains serval sub projects: `drip-table`, `drip-table-generator`.

The introduction of each sub-project are as follows:

-   `drip-table`: the core library of the solution for building dynamic tables. It's main ability is to render a dynamic table automatically when received data which conforms to the `JSON Schema` standard.
    
-   `drip-table-generator`: a visual tool for producing configuration data that meets the `JSON Schema` standard in order to sent to `DripTable` for rendering a table and columns.
    

Features
--------

-   Basic table
-   Compound table
-   Toolbar
-   Renderer
-   Text component
-   Number component
-   Image component
-   Link component
-   Tag component
-   Button component
-   Select component
-   DataPicker component
-   PopUpPage component
-   RichText component
-   Group component
-   Custom component
-   Header slot
-   Footer slot
-   Pagination
-   Virtual list
-   Sticky
-   Sub table
-   Row selection
-   Row draggable
-   Fixed column
-   Show/Hide column
-   Edit data
-   Stripe
-   Table with border
-   Column resizing
-   Size
-   Global styles
-   Empty table prompt
-   Loading
-   Card layout
-   Filter

⬆️ Getting Start
----------------

`Drip table` is divided into two application scenarios: configuration end and application end. The configuration side is mainly responsible for generating `JSON Schema` standard data through visualization and `low-code`. The function of the application side is to render the `JSON Schema` standard configuration data into a dynamic table.

### The configuration side

1.  Install dependencies
    
    The configuration side depend on the application side, please make sure that `drip-table` has been installed before installing dependencies.
    
    > yarn
    
    yarn add drip-table-generator
    
    > npm
    
    npm install --save drip-table-generator
    
2.  Import at the entrance of a file
    
    import DripTableGenerator from "drip-table-generator";
    import "drip-table-generator/dist/index.min.css";
    
3.  Use components in pages
    
    return <DripTableGenerator />;
    
    Then the configuration side can be rendered normally, as the sample screenshot below:
    

### The application side

1.  Install dependencies
    
    Install the `drip-table`:
    
    > yarn
    
    yarn add drip-table
    
    > npm
    
    npm install --save drip-table
    
2.  Import at the entrance of a file
    
    // import drip-table
    import DripTable from "drip-table";
    // import drip-table css
    import "drip-table/dist/index.min.css";
    
3.  Use components in pages
    
    const schema \= {
      size: "middle",
      columns: \[
        {
          key: "columnKey",
          title: "Column Title",
          dataIndex: "dataIndexName",
          component: "text",
          options: {
            mode: "single",
          },
        },
      \],
    };
    return (
      <DripTable
        schema\={schema}
        dataSource\={\[\]}
      />
    );
    
    Then the application side can be rendered normally, as the sample screenshot below:
    

🤝 Contribution
---------------

If you're interested in this project, you're welcome to create ✨issue. We are appreciated for your ❤️star.

### development

1.  Clone
    
    git clone https://github.com/JDFED/drip-table.git
    
2.  Install dependencies
    
    lerna bootstrap
    
3.  build independecies
    
    > yarn
    
    yarn run build
    
    > npm
    
    npm run build
    
4.  Run project
    
    yarn start
    

-   visit http://localhost:8000
-   `drip-table` demo page: /drip-table/guide/basic-demo
-   `drip-table-generator` demo page: /drip-table-generator/demo

For more commands, see DEVELOP . Please visit the official website address drip-table 。

Communication
-------------

Official Wechat group

License
-------

MIT License
