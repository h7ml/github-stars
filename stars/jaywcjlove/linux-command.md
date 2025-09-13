---
project: linux-command
stars: 34370
description: Linux命令大全搜索工具，内容包含Linux命令手册、详解、学习、搜集。https://git.io/linux
url: https://github.com/jaywcjlove/linux-command
---

Special thanks to:  
  
  
**Warp, the intelligent terminal for developers!**  
Available for MacOS, Linux, & Windows  
  

  
  

* * *

Linux Command
=============

当前仓库搜集了 600 多个 Linux 命令，是一个非盈利性的仓库，生成了一个 web 网站方便使用，目前网站没有任何广告，内容包含 Linux 命令手册、详解、学习，内容来自网络和网友的补充，非常值得收藏的 Linux 命令速查手册。版权归属原作者，对任何法律问题及风险不承担任何责任，没有任何商业目的，如果认为侵犯了您的版权，请来信告知。我不能完全保证内容的正确性。通过使用本站内容带来的风险与我无关。当使用本站时，代表您已接受了本站的使用条款和隐私条款。

赞助支持
----

非常感谢一直以来支持我开源项目的朋友们！如果您认可我的工作，欢迎通过 赞助 我或下载并使用我开发的 macOS 应用 来支持我。以下是我个人独立开发的 macOS 应用列表：

Web 版本
------

Github Web | Gitee Web | Githack | Statically

扫描二维码移动端预览搜索，也可通过二维码下面链接地址打开使用，下面网站是通过 Github Action 自动更新。

⚠️ Gitee Web 存在 `违禁违规` 内容问题 #283。

预览搜索：**https://git.io/linux**

你可以随意部署 web 版，这非常简单，只需要克隆 gh-pages 分支代码到你的静态服务就可以了。你也可以将 `command` 目录中的 Markdown 文件拿去自己生成 HTML。还可以使用下方 Docker 部署 web 版。

⚠️ 部署的静态网站，还是希望挂个 GitHub 地址，这样大家共同维护命令文档，让文档更加完善，更加丰富，当然删除本站所有相关信息，其实我也不太在意，默认允许你们随意搞，我不负任何负责。如果您也部署了一份，可以将网址放到下面 :)。

由于中国国内访问，时常打不开，你可以访问下面镜像网站。也可以通过推荐或提交 PR 的方式添加你的镜像站 #649，以提升权重并加快搜索引擎收录。

**推荐使用的镜像 web 版本**

**`qqcl.com`** **`wu114.cn`** **`waadri.top`** **`zanglikun.com`** **`alapi.cn`** **`fasfuah.icu`** **`cnxiaobai.com`** **`sicangge.com`** **`largeinfo.cc`** **`srebro.cn`** **`getaifun.com`** **`devonline.net`** **`man.zch.ooo`** **`mmoke.com`** **`bqrdh.com`** **`zyimm.com`** **`vovuo.com`** **`shinote.net`** `liguiying.cn` `renye.net` `diqi.org` `alistnas.top` `nenufm.com` `jiangyang.online` `xiyung.cn` `78888889.xyz`

**其它 web 版本**

`briline.net` `pkslow.com` `ifdev.cn` `witnect.top` `lylme.com` `ftqq.com` `gaomeluo.com` `atoolbox.net` `xiaoshanseo.com` `262235.xyz` `cmsblogs.cn` `loquy.cn` `buyao.vip` `hezhiqiang.gitbook.io` `utils.fun` `51tools.info`

其它版本
----

-   KDE/Krunner
-   微信小程序版本，由 **@Matz Yang** 提供 #260
-   Chrome 插件，下载 crx 文件安装 或者通过 Chrome Web Store 下载
-   Raycast 版本，(**#338**)
-   Alfred 版本下载，`Dash` 版本 #91，可配合 `alfred` 使用，下载 .docset.tgz 文件，由 **@SHANG殇** 提供
-   Android 版本下载
-   Mac/Win/Linux
-   `@chenjiandongx/how` Python 版 #129，由 **@陈键冬** 提供
-   `@chenjiandongx/pls` Golang 版 #129，由 **@陈键冬** 提供

Docker 部署
---------

轻松通过 docker 部署 linux-command 网站。

docker pull wcjiang/linux-command

docker run --name linux-command --rm -d -p 9665:3000 wcjiang/linux-command:latest
# Or
docker run --name linux-command -itd -p 9665:3000 wcjiang/linux-command:latest

在浏览器中访问以下 URL

http://localhost:9665/

Vercel
------

可以点击下面按钮一键部署至 Vercel:

部署结果

通过 Vercel 分配的域名访问，或者自行在设置中绑定域名。

Netlify
-------

可以点击下面按钮一键部署至 Netlify:

部署结果

通过 Netlify 分配的域名访问，或者自行在设置中绑定域名。

宝塔面板
----

可通过宝塔面板应用商店快速部署 linux-command

部署步骤

### 前提

-   仅适用于宝塔面板 9.2.0 及以上版本
-   安装宝塔面板，前往宝塔面板官网，选择正式版的脚本下载安装

### 部署

1.  登录宝塔面板，在左侧菜单栏中点击 `Docker`
2.  首次会提示安装`Docker`和`Docker Compose`服务，点击立即安装，若已安装请忽略。
3.  安装完成后在`Docker-应用商店-实用工具`中找到 `linux-command`，点击`安装`，也可以在搜索框直接搜索`linux`。
4.  设置域名等基本信息，点击`确定`

-   说明：
    -   名称：应用名称，默认`linuxcommand_随机字符`
    -   版本选择：默认`latest`
    -   域名：如您需要通过域名访问，请在此处填写您的域名
    -   允许外部访问：如您需通过`IP+Port`直接访问，请勾选，如您已经设置了域名，请不要勾选此处
    -   端口：默认`3000`，可自行修改
    -   CPU 限制：0 为不限制，根据实际需要设置
    -   内存限制：0 为不限制，根据实际需要设置

1.  提交后面板会自动进行应用初始化，大概需要`1-3`分钟，初始化完成后即可访问。

### 访问 linux-command

-   如果您填写域名，请在浏览器输入您的域名访问，如`http://demo.linux-command`，即可访问 `linux-command` 页面。
-   如您选择`IP+端口访问`请在浏览器地址栏中输入域名访问 `http://<宝塔面板IP>:6806`，即可访问 `linux-command` 页面。

Linux命令分类
---------

_这里存放Linux 命令大全并不全，你可以通过linux-command来搜索，它是把 command 目录里面搜集的命令，生成了静态HTML并提供预览以及索引搜索。_

### 文件传输

bye、ftp、ftpcount、ftpshut、ftpwho、ncftp、tftp、uucico、uucp、uupick、uuto、scp

### 备份压缩

ar、bunzip2、bzip2、bzip2recover、compress、cpio、dump、gunzip、gzexe、gzip、lha、restore、tar、unarj、unzip、zip、zipinfo

### 文件管理

diff、diffstat、file、find、git、gitview、ln、locate、lsattr、mattrib、mc、mcopy、mdel、mdir、mktemp、mmove、mread、mren、mshowfat、mtools、mtoolstest、mv、od、paste、patch、rcp、rhmask、rm、slocate、split、tee、tmpwatch、touch、umask、whereis、which、cat、chattr、chgrp、chmod、chown、cksum、cmp、cp、cut、indent

### 磁盘管理

cd、df、dirs、du、edquota、eject、lndir、ls、mcd、mdeltree、mdu、mkdir、mlabel、mmd、mmount、mrd、mzip、pwd、quota、quotacheck、quotaoff、quotaon、repquota、rmdir、rmt、stat、tree、umount

### 磁盘维护

badblocks、cfdisk、dd、e2fsck、ext2ed、fdisk、fsck.ext2、fsck、fsck.minix、fsconf、hdparm、losetup、mbadblocks、mformat、mkbootdisk、mkdosfs、mke2fs、mkfs.ext2、mkfs、mkfs.minix、mkfs.msdos、mkinitrd、mkisofs、mkswap、mpartition、sfdisk、swapoff、swapon、symlinks、sync

### 系统设置

alias、apmd、aumix、bind、chkconfig、chroot、clock、crontab、declare、depmod、dircolors、dmesg、enable、eval、export、fbset、grpconv、grpunconv、hwclock、insmod、kbdconfig、lilo、liloconfig、lsmod、minfo、mkkickstart、modinfo、modprobe、mouseconfig、ntsysv、passwd、pwconv、pwunconv、rdate、resize、rmmod、rpm、set、setconsole、setenv、setup、sndconfig、SVGAText Mode、timeconfig、ulimit、unalias、unset

### 系统管理

adduser、chfn、chsh、date、exit、finger、free、fwhois、gitps、groupdel、groupmod、halt、id、kill、last、lastb、login、logname、logout、logrotate、newgrp、nice、procinfo、ps、pstree、reboot、renice、rlogin、rsh、rwho、screen、shutdown、sliplogin、su、sudo、suspend、swatch、tload、top、uname、useradd、userconf、userdel、usermod、vlock、w、who、whoami、whois

### 文本处理

awk、col、colrm、comm、csplit、ed、egrep、ex、fgrep、fmt、fold、grep、ispell、jed、joe、join、look、mtype、pico、rgrep、sed、sort、spell、tr、uniq、vi、wc

### 网络通讯

dip、getty、mingetty、ppp-off、smbd(samba daemon)、telnet、uulog、uustat、uux、cu、dnsconf、efax、httpd、ip、ifconfig、mesg、minicom、nc、netconf、netconfig、netstat、ping、ping6、pppstats、samba、setserial、shapecfg(shaper configuration)、smbd(samba daemon)、statserial(status ofserial port)、talk、tcpdump、testparm(test parameter)、traceroute、tty(teletypewriter)、uuname、wall(write all)、write、ytalk、arpwatch、apachectl、smbclient(samba client)、pppsetup

### 设备管理

dumpkeys、loadkeys、MAKEDEV、rdev、setleds

### 电子邮件与新闻组

archive、ctlinnd、elm、getlist、inncheck、mail、mailconf、mailq、messages、metamail、mutt、nntpget、pine、slrn、X WINDOWS SYSTEM、reconfig、startx(start X Window)、Xconfigurator、XF86Setup、xlsatoms、xlsclients、xlsfonts

### 其他命令

yes

开发使用
----

可以通过 `npm` 安装 `linux-command` 包，包含所有命令的 markdown 文本，和一个索引文件。

npm install linux-command

var comm \= require("linux-command");
console.log("---->", comm.ls);

var alias \= require("linux-command/command/alias.md");
console.log("---->", alias); // markdown string

你也可以通过 CDN 来访问索引数据，和对应的命令详细内容，我将更新内容定期发布版本，提供大家使用，UNPKG 带上版本号，将锁定版本访问，删除版本号请求数据，将会自动重定向最新版本。

# 命令索引 JSON 数据
https://unpkg.com/linux-command/dist/data.json
# 对应命令详情（Markdown）数据
https://unpkg.com/linux-command/command/<命令名称\>.md

你也可以通过 Github 的 Raw 来，获取最新的内容

# 命令索引 JSON 数据
https://raw.githubusercontent.com/jaywcjlove/linux-command/master/dist/data.json
# 对应命令详情（Markdown）数据
https://raw.githubusercontent.com/jaywcjlove/linux-command/master/command/<命令名称\>.md 

Linux学习资源整理
-----------

### 社区网站

-   Linux中国 - 各种资讯、文章、技术
-   LabEx - 免费提供了Linux在线环境，不用在自己机子上装系统也可以学习Linux，超方便实用。
-   鸟哥的linux私房菜 - 非常适合Linux入门初学者看的教程。
-   Linux公社 - Linux相关的新闻、教程、主题、壁纸都有。
-   Linux Today - Linux新闻资讯发布，Linux职业技术学习！。
-   X-CMD - Shell + AWK 为核心增强原生命令输出以及交互体验，各种命令以及现代化软件包的介绍和使用教程，每日科技新闻资讯，欢迎浏览关注！

### 知识相关

-   Linux思维导图整理
-   Linux初学者进阶学习资源整理
-   Linux 新手入门（动手实验）
-   【译】Linux概念架构的理解 En
-   Linux 守护进程的启动方法
-   Linux知识点小结
-   10大白帽黑客专用的 Linux 操作系统

### 软件工具

-   超赞的Linux软件 Github仓库Zh En

Adobe软件的最佳替代品 原文在这里

-   Evince (Adobe Acrobat Reader) 一个“支持多种文档格式的文档查看器”，可以查看PDF，还支持各种漫画书格式
-   Pixlr (Adobe Photoshop) 一个强大的图像编辑工具
-   Inkscape (Adobe Illustrator) 一个专业的矢量图形编辑器
-   Pinegrow Web Editor (Adobe Dreamweaver) 一个可视化编辑制作 HTML 网站
-   Scribus (Adobe InDesign) 一个开源电子杂志制作软件
-   Webflow (Adobe Muse) 一款可以帮助用户不用编码就可以快速创建网站的谷歌浏览器插件。
-   Tupi (Adobe Animate) 一款可以创建HTML5动画的工具。
-   Black Magic Fusion (Adobe After Effects) 一款先进的合成软件，广泛应用于视觉特效、广电影视设计以及3D动画设计等领域。

### 中国开源镜像站点

-   阿里云开源镜像站：http://mirrors.aliyun.com/
-   网易开源镜像站：http://mirrors.163.com/
-   搜狐开源镜像站：http://mirrors.sohu.com/
-   北京交通大学：http://mirror.bjtu.edu.cn/ <教育网荐>
-   兰州大学：http://mirror.lzu.edu.cn/ <西北高校FTP搜索引擎>
-   上海交通大学：http://ftp.sjtu.edu.cn/
-   清华大学：http://mirrors.tuna.tsinghua.edu.cn/
    -   http://mirrors4.tuna.tsinghua.edu.cn/
-   中国科学技术大学：http://mirrors.ustc.edu.cn/
    -   http://ipv6.ustc.edu.cn/ <IPv6 only>
-   东北大学：http://mirror.neu.edu.cn/
-   浙江大学：http://mirrors.zju.edu.cn/
-   东软信息学院：http://mirrors.neusoft.edu.cn/

### 游戏玩家发行版

_面向游戏玩家的八款最佳 Linux 发行版，本文由开源中国整理，原文在这里_。

-   SteamOS 官方文档 镜像下载
-   Ubuntu GamePack 下载地址
-   Fedora – Games Spin 下载地址
-   SparkyLinux – GameOver Edition 下载地址
-   Lakka 下载地址
-   Game Drift Linux 下载地址
-   Solus 下载地址
-   Manjaro Gaming Edition (mGAMe) 下载地址

Team
----

小弟调调™

ZhuangZhu-74

Huck Huang

感谢所有贡献者
-------

一如既往，感谢我们出色的贡献者！

贡献者列表，由 contributors 自动生成

License
-------

Licensed under the MIT License.
