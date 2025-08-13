---
project: Today-wallpapers
stars: 18
description: 基于react electron puppeteer 开发
url: https://github.com/blazer233/Today-wallpapers
---

基于 react + electron 开发及结合爬虫的应用实践🎅
==================================

前言📝
----

> 👉 Electron 是一个可以使用 Web 技术如 JavaScript、HTML 和 CSS 来创建跨平台原生桌面应用的框架。借助 Electron，我们可以使用纯 JavaScript 来调用丰富的原生 APIs。 👈

### 一个 electron-react 栗子 🤖

#### 1️⃣-Demo 安装 react 脚手架

-   终端执行命令`npx create-react-app react-electron`自动进行配置安装
-   进入`react-electron`目录下执行`yarn start`，项目自动运行在 3000 端口

#### 2️⃣-Demo 配置 electron 主进程

-   因为`public`文件夹不会被`webpack`打包处理，会直接复制一份到`dist`目录下，所以在`public`中新建`electron.js`作为主进程
-   在主进程中只需要从 electron 包中结构出 app, BrowserWindow,并监听 app 的'ready'事件，使用 BrowserWindow 生成实例对象，从而判断环境进行加载静态文件 or 端口

const { app, BrowserWindow } \= require("electron");
const isDev \= process.env.NODE\_ENV !== "development";
app.on("ready", () \=> {
  mainWindow \= new BrowserWindow();
  isDev
    ? mainWindow.loadURL(\`file://${\_\_dirname}\\\\index.html\`)
    : mainWindow.loadURL(\`http://localhost:3000\`);
});

#### 3️⃣-Demo 配置 react-cli

需要引入的库

yarn add electron electron\-builder nodemon \-D //安装到生产环境
yarn add concurrently cross\-env \-S //安装到开发环境

-   在 package.json 中通过 mian 标明主进程执行目录，配置 homepage
    
-   配置`scripts`和`build`字段,在 react 启动后打开 electron 桌面应用、通过 `cross-env` 添加环境变量、以及在打包时如何进行配置（只进行 win 下打包）
    
    {
    "name": "my-app",
    "version": "0.1.0",
    "private": true,
    "main": "public/electron.js",
    "homepage": ".",
      "scripts": {
      "start": "cross-env NODE\_ENV=development concurrently \\"yarn run client\\" \\"wait-on http://localhost:3000 && yarn run electron:watch\\" ",
      "build": "yarn run build-client && yarn run build-electron",
      "client": "set BROWSER=none && react-scripts start",
      "electron:watch": "nodemon --watch public/electron.js --exec electron .",
      "electron": "electron .",
      "build-client": "react-scripts build",
      "build-electron": "electron-builder build -w",
      "test": "react-scripts test",
      "eject": "react-scripts eject"
      },
      "build": {
          "productName": "electron-demos",
          "files": \["build/","main.js"\],
          "dmg": {
          "contents": \[
              {"x": 110,"y": 150},
              {"x": 240,"y": 150,"type": "link", "path": "/Applications"}
          \]
          },
          "win": {
          "target": \[{"target": "nsis", "arch": \["x64" \]}\]
          },
          "directories": {
          "buildResources": "assets",
          "output": "release"
          }
      },
    }
    

此时我们可以运行`yarn start` 将之前的`react`起始页通过桌面程序的方式打开，也可以通过执行`yarn build` 将我们的桌面程序打包生成`.exe`文件进行安装 over。

### electron-react 每日壁纸 🧠

> 既然我们可以利用 `react` &`electron` 构建桌面应用，就可以利用众多 npm 包去实现一个能用在生活中可以用到的功能，前段时间由于兴趣使然，接触 node 爬虫比较多，所以我想结合 `puppeteer`实现每日壁纸的桌面应用

#### 1️⃣-wallpaper 明确需求

-   壁纸进行分类获取，所有主题的壁纸通过合集的方式保存
-   每天的壁纸按时更新，更新过的壁纸会保存到数据库中
-   壁纸合集中的壁纸可以通过喜欢功能进行收藏或取消
-   壁纸可以预览、下载，并可进行一键设置
-   在收藏的壁纸中可以开启是否进行每天自动设置当前壁纸
-   风格简约，自适应布局

#### 2️⃣-wallpaper 功能实现

##### 1、electron 部分

需要引入的库

-   `dayjs` 判断和添加日期时
-   `electron-store` 数据存储 (如果使用`mongodb`数据库在开发环境正常，但是打包后就会报错)
-   `electron-dl` 图片下载

首先进行`BrowserWindow`的初始化配置

mainWindow \= new BrowserWindow({
  show: false,
  width: 900,
  height: 700,
  minHeight: 700,
  minWidth: 310,
  frame: false, //无边框
  transparent: false, //透明
  alwaysOnTop: false,
  hasShadow: false, //阴影
  resizable: true,
  webPreferences: {
    nodeIntegration: true, //是否使用 node
    enableRemoteModule: true, //是否有子页面
    contextIsolation: false, //是否禁止 node
    nodeIntegrationInSubFrames: true, //否允许在子页面(iframe)或子窗口(child window)中集成 Node.js
  },
});

数据通过`electron-store`进行操作，使用方便，引入后操作实例对象调取`get`、`set`、`delete`进行获取、设置和删除,但缺点同样明显，不能像`mongodb`一样通过`mongoose`构建模型进行数据操作

const Store \= require("electron-store");
const store \= new Store(test);

store.set("test", true); //设置
store.get("test"); //获取
store.delete("test"); //删除

需求界面 UI 简洁，所以通过 electron 中的 `ipcMain` 和 `ipcRenderer` 通信模块结合前端`antd/icons`设置应用的最小化按钮、全屏按钮、恢复按钮，当点击最小化时，界面隐藏置系统托盘，托盘点击控制界面出现和隐藏，托盘图标右键进行关闭

👇👇👇👇👇 更改为

const {
  Menu: { buildFromTemplate, setApplicationMenu },
} \= require("electron");
setApplicationMenu(buildFromTemplate(\[\])); //取消默认工具栏

`ipcMain` 和 `ipcRenderer` 都是 `EventEmitter`类的一个实例。而`EventEmitter`类由`NodeJS`中的`events`模块导出，`EventEmitter` 类是 NodeJS 事件的基础，实现了事件模型需要的接口， 包括 `addListener`，`removeListener`, `emit` 及其它工具方法. 同原生 JavaScript 事件类似， 采用了发布/订阅(观察者)的方式， 使用内部 `_events` 列表来记录注册的事件处理器。

const { Tray } \= require("electron");
var appTray;
ipcMain.on("max-icon", () \=> {
  //点击最大化时，主进程响应
  mainWindow.isMaximized() ? mainWindow.restore() : mainWindow.maximize();
});
ipcMain.on("mini-icon", () \=> {
  //点击最小化时
  mainWindow.minimize(); //界面最小化
  mainWindow.hide(); //隐藏界面
  if (!appTray) {
    appTray \= new Tray(path.join(\_\_dirname, "favicon.ico")); //设置托盘图标
    appTray.setToolTip("one wallpaper💎"); //托盘图标hover时触发
    appTray.on("click", () \=>
      //托盘图标点击时触发
      mainWindow.isVisible() ? mainWindow.hide() : mainWindow.show()
    );
    appTray.setContextMenu(
      //托盘图标右击时触发
      buildFromTemplate(\[
        {
          label: "退出",
          click: () \=> app.quit(),
        },
      \])
    );
  }
});

electron 其余部分就是利用`ipcMain` 和 `ipcRenderer`通信，使用`electron-store`操作数据储存、处理并返回前端，当需要设置壁纸时通过`electron-dl`进行下载，并返回下载后图片的绝对路径给前端，用于设置桌面壁纸

##### 2、前端部分

需要引入的库

-   `antd` 页面样式
-   `wallpaper` 设置壁纸
-   `puppeteer` 爬虫
-   `node-schedule` 定时任务

前端页面初始化时先通过`ipcRenderer`进行数据库，如果存在则对比数据库中`time`字段保存的时间与当前时间是否为同一天，都符合则获取展示，否则调取`puppeteer`重新进行最新壁纸页面的数据爬取，并将爬取的数据`save`or`merge`到数据库，更新`time`字段，点击对应集合时，进行对应集合的爬取并添加到当前`children`字段进行保存， 数据结构为如下所示

\[
  {
    time:'xxxx-xx-xx'
  },
  {
    href: "当前集合链接",
    srcmini: "集合缩略图.jpg",
    title: "集合名称",
    children: \[
      {
        like: true, //该壁纸是否添加收藏
        href: "壁纸所属集合链接",
        maxsrc: "壁纸缩略图.jpg",
        srcmini: "壁纸大图.jpg",
      },
      ...
    \],
  }
  ...
\];

前端选用的是 `react`+`antd` 进行开发，需要引入的 node 库时在 `utils.js` 文件下进行引入处理、并通过 es6 方式进行导出，由于`electron`通信的回调函数在 es6 中并不友好，所以在`utils.js`中进行统一的异步封装，以`xxx-reply`作为响应 ipcRenderer 通信的标准格式，调用时直接传入通信事件名`await ipcasync('xxx')`

export const { ipcRenderer } \= window.require("electron");
export const ipcasync \= async (name, obj \= null) \=> {
  ipcRenderer.send(name, obj);
  return await new Promise(resolve \=> {
    ipcRenderer.on(\`${name}\-reply\`, (event, arg) \=> resolve(arg));
  });
};

爬虫使用的`puppeteer`库，通过无头浏览器进行爬取，防止网页动态加载导致获取不到数据，并可以进行点击、输入等模拟用户真实行为，弊端在于爬取速度较慢，所以会将爬取到的数据保存，避免二次爬取，在爬取壁纸集合时，会根据 electron 获取到的页面大小进行匹配壁纸尺寸进行爬取

爬取当前最新壁纸

const getHomePage \= async url \=> {
  let urls \= "壁纸网站域名/" + url; //url即子域名
  const browser \= await puppeteer.launch(config);
  const page \= await browser.newPage();
  await page.goto(urls);
  await page.waitForSelector(".wrapper", { visible: true });
  const arr \= await page.$$eval(".main>ul a", el \=>
    el.map(i \=> ({
      href: "壁纸网站域名/" + i.getAttribute("href"),
      srcmini: i.firstChild.getAttribute("src"),
      title: i.firstChild.getAttribute("title"),
      children: \[\],
    }))
  );
  browser.close();
  return arr;
};

爬取指定集合下壁纸

const getPages \= async (url, screen) \=> {
  const browser \= await puppeteer.launch(config);
  const page \= await browser.newPage();
  await page.goto(url);
  const all \= await page.$eval(".wrapper span", el \=> el.textContent);
  const allPage \= all.split("/")\[1\].replace("）", "");
  await page.waitForSelector(".wrapper", { visible: true });
  const arr \= await page.$$eval("#showImg li a", el \=>
    el.map(i \=> ({
      href: "壁纸网站域名/" + i.getAttribute("href"),
      srcmini:
        i.firstElementChild.getAttribute("src") ||
        i.firstElementChild.getAttribute("srcs"),
    }))
  );
  for (let i \= 0; i < arr.length; i++) {
    console.log(\`总共爬取 ${allPage} 张,当前爬取第 ${i} 张\`);
    await page.goto(arr\[i\].href);
    await page.waitForSelector(\`#tagfbl\`, { visible: true });
    const hrefItems \= await page.evaluate(
      el \=>
        document.querySelector(el)
          ? document.querySelector(el).getAttribute("href")
          : document.querySelector(\`a\[id="1920x1080"\]\`)
          ? document.querySelector(\`a\[id="1920x1080"\]\`).getAttribute("href")
          : document.querySelector(\`#tagfbl a\`).getAttribute("href"),
      \`a\[id="${screen}"\]\`
    );
    await page.goto("壁纸网站域名/" + hrefItems);
    await page.waitForSelector("body img", { visible: true });
    const hrefItem \= await page.$eval("body img", el \=> el.src);
    arr\[i\].maxsrc \= hrefItem;
  }
  browser.close();
  return arr;
};

#### 3️⃣-wallpaper 展示

功能展示

-   自适应布局 ✔
-   壁纸收藏 ✔
-   壁纸下载 ✔
-   每日更新 ✔
-   动态壁纸 ✖（真不知道怎么搞，来个大佬指导一下）

#### 4️⃣-wallpaper 总结

至此，谢谢各位在百忙之中点开这篇文章，希望对你们能有所帮助，相信你对 electron 结合 react 开发以及有了大概的认实，总的来说优化的点还有很多，比如 webpack 的打包配置、爬虫、等等...此项目为了大家能更熟练上手在上手 electron+react 的业务需求，如有问题欢迎各位大佬指正。

-   👋：跳转github
-   🍑：将 package 文件中的 executablePath 更改为自己谷歌浏览器的目标路径

求个 star，谢谢大家了
