---
project: dt-form-renderer
stars: 24
description: Render Interaction Form Via JSON
url: https://github.com/DTStack/dt-form-renderer
---

dt-form-renderer
================

-   一个基于 React 和 Ant-Design 的表单渲染器
-   使用 JSON 描述表单
-   支持复杂的联动逻辑

  

文档
--

-   FormRenderer 组件
-   JSON 配置
-   表达式
-   表单联动
-   自定义表单控件
-   表单 Service
-   CHANGELOG

  

使用
--

组件

import React, { useRef } from 'react';
import FormRenderer from 'dt-form-renderer';
import jsonConfig from './jsonConfig';

function FormDemo () {

    const formRef \= useRef();

    return (
        <FormRenderer
            ref\={formRef}
            onValuesChange\={(...args) \=> console.log(args)}
            initialValues\={{}}
            jsonConfig\={}
            defaultExtraData\={{}}
        />
    )
}

表单配置

const jsonConfig \= {
    description: '这是一份表单配置',
    fieldList: \[
        {
            fieldName: 'schema',
            label: 'schema',
            widget: 'Select',
            widgetProps: {
                placeholder: '请选择schema',
                options: \[\],
                allowClear: true,
            },
        },
        {
            fieldName: 'tableName',
            label: '表名',
            dependencies: \['schema'\],
            widget: 'Select',
            widgetProps: {
                options: \[\],
                placeholder: '请选择表名',
            },
            rules: \[
                {
                    required: true,
                    message: '请选择表名！',
                },
            \],
        },
    \],
};

export default jsonConfig;

在线编辑
----

PlayGround
