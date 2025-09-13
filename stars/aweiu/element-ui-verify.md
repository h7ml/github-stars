---
project: element-ui-verify
stars: 472
description: 如果你受够了饿了么ElementUI原生的校验方式，那就来试试它吧！一款更懂你的校验插件
url: https://github.com/aweiu/element-ui-verify
---

element-ui-verify
=================

如果你受够了饿了么 ElementUI 原生的校验方式，那就来试试它吧！

前言
--

饿了么 ElementUI 虽好，但表单校验的体验不够理想

如果说产品开发要讲究用户体验，那插件开发也要讲究开发体验，而好的开发体验，要靠好的 api 设计来保障

本人专注校验插件开发 30 年，有祖传的校验插件 api 设计（玩笑）。主要是参考了之前写的vue-verify-pop的 api，并加以完善，取其精华，去其糟粕，揉和日月之精华。。。

本插件只是对 ElementUI 原本的校验方式做了一层封装，核心的校验器仍然是async-validator，非侵入式，完全不会影响你继续使用 ElementUI 的原生校验

示例
--

<template\>
  <el-form label-width\="100px" :model\="model"\>
    <el-form-item label\="年龄" prop\="age" verify int :gt\="0"\>
      <el-input v-model\="model.age"\></el-input\>
    </el-form-item\>
  </el-form\>
</template\>
<script\>
  export default {
    data() {
      return {
        model: {
          age: ""
        }
      };
    }
  };
</script\>

ok，你已经完成了一个内容为大于 0 的整数校验！(欢迎对比官方版的相似例子)

文档
--

https://aweiu.com/documents/element-ui-verify/
