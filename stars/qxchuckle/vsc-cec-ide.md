---
project: vsc-cec-ide
stars: 782
description: 一个没什么用的VSC插件
url: https://github.com/qxchuckle/vsc-cec-ide
---

CEC-IDE
=======

国产化你的VSCode，附带敏感词检测、防沉迷等功能，没有大问题不会再更新了

已上架VSCode插件市场CEC-IDE，Open VSX：CEC-IDE，下载vsix可前往releases

**命令：** Ctrl+Shift+P 打开命令中心

1.  `CEC-IDE` 进行国产化（国产化只是修改VSC的UI样式，不执行也能使用敏感词等功能）
2.  `CEC-IDE-RESTORE` 去除国产化

**注意:**

1.  请确保以管理员身份运行VSCode。
2.  最好不要多次执行 `CEC-IDE`，除了首次，后续执行 `CEC-IDE` 前请先执行 `CEC-IDE-RESTORE`。若没能国产化，请提 Issues。
3.  提示code损坏请装 Fix VSCode Checksums 插件，然后执行 `Fix Checksums: Apply` 命令。

在设置中可以自定义侧边栏视图的一些信息：

实用功能
----

### 1、敏感词检测

> 独立的敏感词检测插件：sensitive-word-detection 是本插件敏感词检测功能的独立版本

在任意文件，右键，点击敏感词检测，将会持续检测该文件是否有敏感词，若文件关闭或没有敏感词，则停止检测。右键点击停止检测敏感词可以手动停止检测。即使换行(最多隔一行)且隔着干扰字符也能检测到。

**快捷键:** `alt+shift+m` 检测，`alt+shift+n` 停止检测。

**命令:敏感词支持热重载**

1.  `CEC-UploadSensitiveWordsFile` 上传自定义敏感词txt文件，格式：一行一个敏感词。
2.  `CEC-ResetSensitiveWordsFile` 重置为插件自带的敏感词。

有快速修复功能，一键替换该敏感词或所有敏感词为`***`

点击右下角状态栏按钮，也能开始检测或停止检测，且在检测中会显示当前活动编辑器含有的敏感词数。

敏感词来源：tencent-sensitive-words 【有删改】

### 2、防沉迷

启用防沉迷模式后（默认关闭），右下角会新增一个状态栏项，记录当天编辑器使用时间。若超过所设置的防沉迷时间（默认2小时），则会提醒关闭编辑器，每分钟弹一次提醒。

若未启用防沉迷模式，则每次打开编辑器，都会提醒开启防沉迷模式。

可以在设置中对防沉迷模式进行自定义规则，包括关闭防沉迷提醒、关闭提醒开启防沉迷模式等。

展示
--

VSC图标修改
-------

软件的图标修改插件做不到

请下载仓库内 **CEC-IDE.ico** 自行右键-属性-更改图标（对于MacOS用户，请使用 CEC-IDE.icns）

* * *

> 整活项目，顺带学习下VSCode插件开发。  
> 本项目仅供个人学习使用。图片等资源来源于互联网，如有侵权请联系删除。

* * *
