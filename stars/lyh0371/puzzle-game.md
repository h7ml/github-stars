---
project: puzzle-game
stars: 33
description: 使用vue3+vite2实现的数字华容道拼图游戏
url: https://github.com/lyh0371/puzzle-game
---

项目名称
----

数字华容道 线上体验

技术栈
---

vue3 + vite2

使用
--

<num-game
:gamedata\="gamedata"
ref\="game"
@endCallback\="endCallback"\> </num\-game\>

配置项
---

{
  level: 3 , // 默认是3\*3 生成数组盘 支持3,4,5,6
  mode:"number", // 默认'number'支持 'number' 、 'img' 两种,如果mode='img'下面imgs参数必填
  imgs:\[\], //图片路径,需要根据level自定义张数
  style:{
    sliderBg: "red", // 滑块背景色
    sliderColor: "#fff", // 滑块字体颜色
    sliderFontSize: "14px", // 滑块字体大小
    gameBoxBg: "#5a009b", // 游戏盘背景色
  }
}

API
---

-   `game` 游戏开始
-   `endCallback` 游戏结束

个人项目webpack 打包多页面应用并支持自动生成路由 欢迎大家 start
---------------------------------------

欢迎关注微信公众号\[码不停息\]
-----------------
