---
project: bruce
stars: 69
description: 🔥 Bruce FEES 一套多功能前端工程化多包管理实践方案 📦
url: https://github.com/JowayYoung/bruce
---

Bruce
-----

请查看Bruce FEES的文档

### 开发计划

-   **@yangzw/bruce-app**：应用`@1.3.7`✔️
-   **@yangzw/bruce-ico**：图标`@1.3.7`
-   **@yangzw/bruce-img**：图像`@1.3.7`✔️
-   **@yangzw/bruce-lng**：语言`@1.3.7`
-   **@yangzw/bruce-pkg**：模块`@1.3.7`✔️
-   **@yangzw/bruce-std**：规范`@1.3.7`✔️
-   **@yangzw/bruce-ui**：组件`@1.3.7`
-   **@yangzw/bruce-us**：工具`@1.3.7`✔️

### 色彩定义

-   **redBright**：错误、主题
-   **yellowBright**：警告、链接、加载
-   **blueBright**：说明、路径、名称
-   **greenBright**：成功、命令

### 问题清单

-   `bruce-pkg`依赖的`listr2`目前未升级到`v7`，`v7`存在无法抛出错误的问题，但是`v6`需要显式依赖`enquirer`
-   `vite`从`v4`迁移到`v5`的注意事项
-   `stylelint`从`v15`迁移到`v16`的注意事项
-   `app/ico/img/std`需要去掉`tsconfig.json`的`"skipLibCheck":true`配置
-   `app`的`sass`和`sass-loader@14`存在版本兼容冲突，`sass-loader`降级到`v13`
-   `img`的`imagemin-svgo@11`存在`is-svg`错误，降级到`v10`
-   `std`的`eslint-config-love`只能停留在`v47`，需要`eslint`升级到`v9`才能使用`v52`(直接移除)
-   `std`的`typescript-eslint`只能停留在`v7`，需要`eslint`升级到`v9`才能使用`v8`

### 指令步骤

-   重建源码(0)：`npm run rebuild`(不包括`publish/upgrade`)
-   清空缓存(1)：`npm run clean`
-   初始项目(2)：`npm run init`
-   构建源码(3)：`npm run build`
-   压缩源码(4)：`npm run mini`
-   挂载源码(5)：`npm run link`
-   提交源码(6)：`npm run commit`
-   发布源码(7)：`npm run publish`
-   发布源码(8)：`npm run upgrade`
-   构建源码(单包)：`pnpm -F @yangzw/bruce-std run build`
-   调试源码(单包)：`pnpm -F @yangzw/bruce-std run dev`
-   增加依赖(单包)：`pnpm -F @yangzw/bruce-ui add bootstrap-icons`
-   删除依赖(单包)：`pnpm -F @yangzw/bruce-ui remove bootstrap-icons`
-   发布模块(单包)：`pnpm -reg https://registry.npmjs.org/ -F @yangzw/bruce-us --no-git-checks publish`

### 开发细节

#### yarn调试问题

整个项目使用`yarn`进行调试，`yarn`安装之后再配置`bin/prefix/cache目录`。**Windows**和**MacOS**同理，以`MacOS`为例。

找到`bin/prefix/cache目录`并手动删除，同时保留配置文件`/usr/local/share/.yarnrc`。

# 获取bin目录：/usr/local/bin
yarn global bin

# 获取prefix目录：/usr/local/share/.config/yarn/global
yarn global dir

# 获取cache目录：/usr/local/share/Library/Caches/Yarn
yarn cache bin

迁移`bin/prefix/cache目录`到指定位置，`bin目录`要在`prefix目录`中，`prefix目录`和`cache目录`要在同一文件夹中。其中`path`为`/Users/yangzw/Documents/记录/Yarn`。

# 设置bin目录
yarn config set prefix path/prefix/bin

# 设置prefix目录
yarn config set global-folder path/prefix

# 设置cache目录
yarn config set cache-folder path/cache

将`bin目录`增加到环境变量中，重启配置文件使它生效。

# 进入配置文件
vim ~/.bash\_profile

# 在.bash\_profile中定义环境变量
export PATH=$PATH:\`yarn global bin\`

# 重启配置文件
source ~/.bash\_profile

执行`yarn global add pkg`安装模块并测试它能否在全局环境中使用。

yarn global add typescript
tsc -v

调试范围模块时执行`yarn link`将它挂载到`~/.config/yarn/link`，但是上述配置已经改变`bin/prefix/cache目录`，所以要执行`yarn link --link-folder path`将它指定到`bin目录`中。

# 进入目录
cd pkg
# 链接指令
yarn link --link-folder path/prefix/bin
# 解除指令
yarn unlink --link-folder path/prefix/bin

#### sharp安装问题

设置`sharp镜像`指向到淘宝镜像。

npm config set sharp\_binary\_host https://npm.taobao.org/mirrors/sharp/
npm config set sharp\_dist\_base\_url https://npm.taobao.org/mirrors/sharp-libvips/
npm config set sharp\_libvips\_binary\_host https://npm.taobao.org/mirrors/sharp-libvips/

前往sharp-libvips手动下载压缩包，将它放置到`npm config get cache`获取目录的`_libvips文件夹`中。

-   **Windows**选择`win32-x64.tar.br`或`win32-x64.tar.gz`下载
-   **MacOS**选择`darwin-x64.tar.br`下载
-   **Linux**选择`linux-x64.tar.br`下载

#### 使用TS开发具备bin命令的Npm模块

首先，配置`tsconfig.json文件`，这些字段必须配置。

-   **allowJs**：允许编译器编译JS文件
-   **allowSyntheticDefaultImports**：允许导入没有默认导出的模块时，编译器生成默认导出
-   **baseUrl**：相对导入的基准路径
-   **downlevelIteration**：将`for-of`编译为ES5兼容的代码
-   **esModuleInterop**：允许导入CJS模块时使用ES模块的语法
-   **experimentalDecorators**：允许使用实验性的装饰器语法
-   **forceConsistentCasingInFileNames**：强制文件名称大小写一致
-   **jsx**：JSX编译方式
-   **lib**：编译之后的可用库
-   **module**：编译之后的模块规范
-   **moduleResolution**：模块解析方式
-   **outDir**：输出目录
-   **paths**：定义文件路径快捷方式(在Pnpm项目中无法使用)
-   **removeComments**：删除代码注释
-   **resolveJsonModule**：允许导入JSON文件
-   **rootDir**：源码目录(可选)
-   **skipLibCheck**：跳过错误类型检查(可选，在编译时遇到类型不通过可用这个选项跳过检查)
-   **sourceMap**：生成SourceMap文件
-   **strict**：启用所有严格类型的检查
-   **target**：编译之后的代码需要支持ECMAScript的版本
-   **exclude**：排除指定的文件或目录
-   **include**：包括指定的文件或目录

{
	"compilerOptions": {
		"allowJs": true,
		"allowSyntheticDefaultImports": true,
		"baseUrl": ".",
		"downlevelIteration": true,
		"esModuleInterop": true,
		"experimentalDecorators": true,
		"forceConsistentCasingInFileNames": true,
		"jsx": "preserve",
		"lib": \[
			"DOM",
			"DOM.Iterable",
			"ES2015",
			"ES2016",
			"ES2017",
			"ES2018",
			"ES2019",
			"ES2020",
			"ES2021",
			"ES2022",
			"ES2023",
			"ES2024",
			"ESNext"
		\],
		"module": "ESNext",
		"moduleResolution": "node",
		"outDir": "dist",
		"paths": {
			"@/\*": \[
				"src/\*"
			\]
		},
		"removeComments": true,
		"resolveJsonModule": true,
		"sourceMap": false,
		"strict": true,
		"target": "ES6"
	},
	"exclude": \[
		"node\_modules"
	\],
	"include": \[
		"src"
	\]
}

然后，配置`package.json文件`。为了让TS编译出来的JS能在`Node`的`ESM`模块规范的环境中运行，需要对这些字段进行配置。

-   **bin**: 模块的CMD工具，当模块被导入时，会加载这个文件
-   **main**: 模块的入口文件，当模块被安装时，会自动将这个字段中指定命令增加到PATH环境变量中
-   **type**: 模块规范

同时还要为CMD工具提供调试环境。使用`nodemon`监听`src目录`、`tsconfig.json`和`package.json`，当这些文件发生变化时，重新编译和打包TS为JS，通过`npm link`将模块链接到全局环境中，为命令提供全局的调试和调用。

{
	"type": "module",
	"main": "dist/index.js",
	"bin": {
		"bruce-pkg": "dist/index.js"
	},
	"scripts": {
		"build": "rimraf dist && tsc -p tsconfig.json && npm link",
		"dev": "nodemon -w src -w package.json -w tsconfig.json -e ts -x \\"npm run build\\""
	}
}

调试时执行`pnpm run -F @yangzw/bruce-pkg dev`。具体来说，命令中每个参数的作用如下。

-   **\-w**：全写为`--watch`，监听指定文件或目录的变化，如果存在多个目标，就用多个`-w`监听
-   **\-e**：全写为`--ext`，监听文件后缀，如果存在多种文件，就用逗号隔开
-   **\-x**：全写为`--exec`，文件发生变化时需要执行的命令，需要使用两个`\"`包裹命令

最后，规范`ts/tsx文件`的编写。参考文档1和文档2。

根据TS模块解决方案规则，`ts/tsx文件`的后缀不应该在导入TS文件时使用。相反，要么使用`js/jsx`的文件后缀，要么完全省略文件后缀。

import { getUser } from "./user.js"; // user.ts
import MyComponent from "./component"; // component.tsx

#### Mac电脑权限问题

在执行`npm run link`之后，生成的文件会存在权限问题，需要开通读写权限。

chmod +x /Users/yangzw/Documents/记录/Nvm/versions/node/v22.14.0/bin/bruce-app
chmod +x /Users/yangzw/Documents/记录/Nvm/versions/node/v22.14.0/bin/bruce-ico
chmod +x /Users/yangzw/Documents/记录/Nvm/versions/node/v22.14.0/bin/bruce-img
chmod +x /Users/yangzw/Documents/记录/Nvm/versions/node/v22.14.0/bin/bruce-lng
chmod +x /Users/yangzw/Documents/记录/Nvm/versions/node/v22.14.0/bin/bruce-pkg
chmod +x /Users/yangzw/Documents/记录/Nvm/versions/node/v22.14.0/bin/bruce-std

在检查`package.json文件`时，`Version Lens`可能无权读取`node_modules`文件夹的缓存，需要执行以下命令清理缓存。

npm cache clean -f
