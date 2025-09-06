---
project: outils
stars: 2622
description: :rocket: 前端业务代码工具库
url: https://github.com/proYang/outils
---

outils
======

前端业务代码工具库

> 目的：高效率完成前端业务代码

业务开发过程中，会经常用到`日期格式化`、`url参数转对象`、`浏览器类型判断`、`节流函数`等常用函数，为避免不同项目多次复制粘贴的麻烦，这里统一封装，并发布到npm，以提高开发效率。如果你也有常用的代码，欢迎为本项目提交pr。

🏗️ 安装使用
--------

1.  直接下载`min`目录下的outils.min.js使用，支持UMD通用模块规范
2.  使用npm安装

### 浏览器:

  <script src\="outils.min.js"\></script\>
  <script\>
      var OS \= outils.getOS()
  </script\>

### npm:

$ npm install --save-dev outils

webpack、RequireJS、SeaJS等

// 完整引入
const outils \= require('outils')
const OS \= outils.getOS()

**推荐使用方法**

你真的不需要完整引入所有函数，所以只引入需要使用的方法即可。

// 只引入部分方法('outils/<方法名>')
const getOS \= require('outils/getOS')
const OS \= getOS()

📦 API文档
--------

### Array

####   arrayEqual  判断两个数组是否相等

### Class

####   addClass  为元素添加class

####   hasClass  判断元素是否有某个class

####   removeClass  为元素移除class

### Cookie

####   getCookie  根据name读取Cookie

####   removeCookie  根据name删除Cookie

####   setCookie  添加Cookie

### Device

####   getExplore  获取浏览器类型和版本号

####   getOS  获取操作系统类型

### Dom

####   getScrollTop  获取滚动条距顶部的距离

####   offset  获取一个元素的距离文档(document)的位置，类似jQ中的offset()

####   scrollTo  在${duration}时间内，滚动条平滑滚动到${to}指定位置

####   setScrollTop  设置滚动条距顶部的距离

####   windowResize  H5软键盘缩回、弹起回调

### Function

####   debounce  函数防抖

####   throttle  函数节流

### Keycode

####   getKeyName  根据keycode获得键名

### Object

####   deepClone  深拷贝，支持常见类型

####   isEmptyObject  判断Object是否为空

### Random

####   randomColor   随机生成颜色

####   randomNum  生成指定范围随机数

### Regexp

####   isColor  判断是否为16进制颜色，rgb 或 rgba

####   isEmail  判断是否为邮箱地址

####   isIdCard  判断是否为身份证号

####   isPhoneNum  判断是否为手机号

####   isUrl  判断是否为URL地址

### String

####   digitUppercase  现金额转大写

### Support

####   isSupportWebP  判断浏览器是否支持webP格式图片

### Time

####   formatPassTime  格式化${startTime}距现在的已过时间

####   formatRemainTime  格式化现在距${endTime}的剩余时间

####   isLeapYear  判断是否为闰年

####   isSameDay  判断是否为同一天

####   timeLeft  计算${startTime - endTime}的剩余时间

####   monthDays  获取指定日期月份的总天数

### Url

####   parseQueryString  url参数转对象

####   stringfyQueryString  对象序列化
