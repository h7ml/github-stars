---
project: llcom
stars: 1067
description: 🛠功能强大的串口工具。支持Lua自动化处理、串口调试、WinUSB、串口曲线、TCP测试、MQTT测试、编码转换、乱码恢复等功能
url: https://github.com/chenxuuu/llcom
---

LLCOM
=====

English readme click here

可运行lua脚本的高自由度串口调试工具。使用交流群：`931546484`

下载
--

从微软商店安装：

exe便携版：国内用户点我下载

CI快照版：Appveyor Artifacts

所有正式版本：GitHub Releases

功能列表
----

-   其他串口调试功能具有的功能
-   收发日志清晰明了，可同时显示HEX值与实际字符串
-   自动保存串口与Lua脚本日志，并附带时间
-   串口断开后，如果再次连接，会自动重连
-   发送的数据可被用户自定义的Lua脚本提前处理
-   右侧快捷发送栏，快捷发送条目数量不限制
-   右侧快捷发送栏，支持10页数据，互相独立
-   可独立运行Lua脚本，并拥有定时器与协程任务特性（移植自合宙Luat Task架构）
-   可选文字编码格式
-   终端功能，直接敲键盘发送数据（包含ctrl+字母键）
-   可单独隐藏发送数据
-   集成TCP、UDP、SSL测试服务端/客户端功能，并且支持IPV6
-   集成各种编码互转功能
-   集成乱码恢复功能
-   集成mqtt测试功能
-   集成串口监听功能，可监听其他软件的串口通信数据

特色功能示范
------

### 使用Lua脚本提前处理待发送的数据

1.  结尾加上换行回车

return uartData.."\\r\\n"

1.  发送16进制数据

return uartData:fromHex()

此脚本可将形如`30313233`发送数据，处理为`0123`的结果

1.  更多玩法等你发现

json \= require("JSON")
t \= uartData:split(",")
return json:encode({
    key1 \= t\[1\],
    key2 \= t\[2\],
    key3 \= t\[3\],
})

此脚本可将形如`a,b,c`发送数据，处理为`{"key1":"a","key2":"b","key3":"c"}`的结果

**此处理脚本，同样对右侧快捷发送区域有效。**

### 独立的Lua脚本自动处理串口收发

右侧的Lua脚本调试区域，可直接运行你写的串口测试脚本，如软件自带的：

\--注册串口接收函数
uartReceive \= function (data)
    log.info("uartReceive",data)
    sys.publish("UART",data)\--发布消息
end

\--新建任务，等待接收到消息再继续运行
sys.taskInit(function()
    while true do
        local \_,udata \= sys.waitUntil("UART")\--等待消息
        log.info("task waitUntil",udata)
        local sendResult \= apiSendUartData("ok!")\--发送串口消息
        log.info("uart send",sendResult)
    end
end)

\--新建任务，每休眠1000ms继续一次
sys.taskInit(function()
    while true do
        sys.wait(1000)\--等待1000ms
        log.info("task wait",os.time())
    end
end)

\--1000ms循环定时器
sys.timerLoopStart(log.info,1000,"timer test")

甚至你可以利用xlua框架的特性，调用C#接口完成任何你想做的事情

request \= CS.System.Net.WebRequest.Create("http://example.com")
request.ContentType \= "text/html;charset=UTF-8";
request.Timeout \= 5000;\--超时时间
request.UserAgent \= "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/71.0.3578.98 Safari/537.36 Vivaldi/2.2.1388.37";

response \= request:GetResponse():GetResponseStream()

myStreamReader \= CS.System.IO.StreamReader(response, CS.System.Text.Encoding.UTF8);

print(myStreamReader:ReadToEnd())\--打印获取的body内容

myStreamReader:Close()
response:Close()

使用此功能，你可以完成大部分的自动化串口调试操作。

接口文档
----

接口文档可以在这个页面查看

已知问题与待添加的功能（请大家反馈，谢谢！）
----------------------

-   bug：某些条件下（比如Air720重启），COM口消失后不会被释放，导致无法再次开启该COM口，只能重启软件（.net 框架的bug，微软的人在看了）（已解决 #2f26e68）

开源
--

如果各位大佬不觉得麻烦的话，欢迎对本项目进行pr或直接重构。

本项目在前期只是为了实现功能，代码相当零散，所以不太适合阅读我的源码进行学习，等我有空的时候会重构代码。

本项目采用Apache 2.0协议，如有借用，请保留指向该项目的链接。

Contributors ✨
--------------

Thanks goes to these wonderful people (emoji key):

  
**whc2001**  
💻 🐛

  
**chenxuuu**  
📆

  
**neomissing**  
🤔

  
**RuoYun**  
🐛

  
**王龙**  
🤔 🐛 💻

  
**linhongz**  
🤔 🐛

This project follows the all-contributors specification. Contributions of any kind welcome!

特别感谢
----
