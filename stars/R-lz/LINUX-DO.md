---
project: LINUX-DO
stars: 360
description: 一个简单的L站的移动端
url: https://github.com/R-lz/LINUX-DO
---

LINUX DO 🐧
===========

* * *

🌟 这是什么？
--------

使用Flutter开发的LINUX DO客户端,支持 `Android` `IOS`.

📦 项目结构
-------

```
lib/
├── 🏛 const/          
├── 🧠 controller/      
├── 🗃 models/         
├── 🌐 net/          
├── 📱 pages/        
├── 🗺 routes/       
├── ⚙️ utils/         
└── 🎨 widgets/       
```

🚀 启程指南
-------

### 环境准备

必要条件:
  - Flutter: "\>=3.0.0 <4.0.0"
  - Dart: "\>=3.0.0 <4.0.0"
  - 开发工具: Android Studio / VS Code
  - iOS: Xcode 13.0+（用于iOS开发）
  - Android: Android SDK（用于Android开发）

```
安装flutter
```

# 检查安装结果
flutter --version

# 检查环境
flutter doctor -v

### 🎯 开发环境配置

#### 1\. 项目获取

# 克隆项目
git clone https://github.com/R-lz/LINUX-DO.git
cd LINUX-DO

# 安装依赖
flutter pub get

#### 2\. 代码生成

# 生成路由、JSON序列化等代码
flutter pub run build\_runner build --delete-conflicting-outputs

#### 3\. 平台特定配置

iOS 配置  

```
确保系统中安装了xcode,cocoapods
```

# 进入 iOS 目录
cd ios

pod cache clean --all
rm -rf Pods Podfile.lock

pod install --repo-update

cd ..

* * *

Android 配置  

```
确保你的系统中已安装JDK，并配置了环境变量（JAVA_HOME 和 PATH）
```

#### 生成签名文件

mkdir -p keystore

keytool -genkey -v -keystore keystore/linux-do.jks -alias mykey -keyalg RSA -keysize 2048 -validity 10000

继续交互式

Enter keystore password:  \[输入 Keystore 密码\]
Re-enter new password:   \[再次输入确认密码\]
What is your first and last name? 
... ...

创建key.properties

touch keystore/key.properties

cat \> keystore/key.properties << EOF
storePassword=<你的Keystore密码>
keyPassword=<你的密钥密码>
keyAlias=mykey
storeFile=../keystore/linux-do.jks
EOF

### 🚀 启动项目

#### iOS

# 开发版本
flutter run -d ios

# 发布版本
flutter build ios --release

#### Android

# 开发版本
flutter run -d android

# 安卓打包
flutter build apk --release --split-per-abi

使用Github Actions编译打包

#### Android:

```
配置 KEYSTORE_BASE64 | KEY_PROPERTIES
```

# 生成base64
base64 -i release.jks

配置步骤:

-   打开仓库Settings
-   点击 `Secrets and variables` -> `New repository secret`
-   添加两个Secret
-   添加 Key: `KEYSTORE_BASE64` Value:<生成的base64>
-   添加KEY\_PROPERTIES 复制整个`key.properties`文本内容
-   转到Actions运行`build_android`

#### IOS:

```
ios为未签名的IPA,直接运行`build_ios`
```

* * *

🤝 参与贡献
-------

每一个想法都值得被倾听，每一行代码都应该被尊重。

-   发现任何问题或功能上的建议,请通过Issues反馈
-   欢迎提交PR
-   感谢你对项目的贡献！

如果这个项目有帮助到你，请献上你的 Star ⭐️ 你的认可，是我们前进的动力。

📜 开源协议
-------

本项目采用MIT许可证 - 请参阅LICENSE文件以获取详细信息。
