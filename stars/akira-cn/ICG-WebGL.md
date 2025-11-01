---
project: ICG-WebGL
stars: 847
description: 交互式计算机图形学——基于WebGL的自顶向下方法（第七版）的例子与练习题
url: https://github.com/akira-cn/ICG-WebGL
---

ICG-WebGL
=========

webgl.group
-----------

这是《交互式计算机图形学——基于WebGL的自顶向下方法（第七版）》这本书的每章示例和部分练习题参考实现。

作者官方的示例代码在这里。

重构后的代码在线运行

我们将重写官方实例的例子：

-   重构示例代码，增加必要的注释
-   使用Babel7
-   增加练习题参考答案
-   替换MV.js和MV2.js为gl-matrix
-   使用transform-gl-matrix插件简化gl-matrix的API
-   重写部分Utils功能，组织到一个简单的工具库GLHelper中
-   使用Webpack打包，使用glsl-shader-loader加载shader文件
-   使用eslint-config-sprite
-   部分练习提供其他参考实现版本，比如THREE.js实现版本。
-   增加其他扩展例子实现

欢迎共同学习本教程的同学参与项目，为项目贡献PR。

代码本地运行
------

npm start

访问 http://localhost:3000

或者也可以独立运行某一章节的例子：

npm run chapter02

上面的命令运行第二章的例子。

License
-------

MIT
