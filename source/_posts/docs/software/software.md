---
title: win/macos软件安装(Git,Git Bash,Node.js,VSCode)
date: 2019-06-06
categories:
 - software
tags:
 - tools
---

## 软件安装
### Git安装和配置
#### 安装
直接安装Git Bash
#### 配置
请在命令行运行这五句话！！！一定要运行这五句话，不然 git 就不能用了
``` bash
git config --global user.name xxx #方便产品经理找（怼）你
git config --global user.email yyy #方便产品经理找（怼）你
git config --global push.default simple # 本来我写的是 matching，不过想了想可能 simple 更好
git config --global core.quotepath false #防止文件名变成数字
git config --global core.editor "vim" # 使用vim编辑提交信息
```
运行 git 的时候注意一下：git remote add origin 后面的地址，不允许使用 https 开头的地址。
### Git Bash安装和配置（win）
	•	安装
	•	从官网下载（）
双击安装，注意每一步的选项要参考下面的图（如果没有对应的图，就直接下一步）
  下面的路径可以随便填：      
好了，安装完成。
	•	配置
安装成功之后，需要设置一下外观：
   
关闭重启 Git Bash 即可。
	•	使用
	•	第一种使用方式
找一个目录，在目录上右键点击，然后选中「Git Bash Here」，即可用 Git Bash 打开这个目录。
试试输入 touch 1.txt，回车后看看目录里是不是多了一个文件。
	•	第二种使用方式
直接打开 Git Bash，输入 cd ~/Desktop 即可来到桌面所在的目录。
试试输入 touch 1.txt，回车后看看桌面上是不是多了一个文件。
	•	更多命令
下节课我们会专门学习命令行，你可以试试下面几个简单的命令：
``` bash
	•	创建目录：mkdir my-dir
	•	删除目录：rm -r my-dir
	•	创建文件：echo "hello" > newFile.txt
	•	删除文件：rm newFile.txt
```

### Node.js的安装和配置
	•	安装
	•	从官网下载安装包
安装了之后
	•	千万别 点击 Node.js 的图标
	•	千万别 点击 Node.js 的图标
	•	千万别 点击 Node.js 的图标
别问为什么，别点就是了。
	•	配置
打开 Git Bash，依次输入以下命令，按回车：
``` bash
npm config set registry https://registry.npm.taobao.org/
npm config set loglevel http
npm config set progress false
```
npm 的配置被存储在 ~/.npmrc，你可以随时改。
	•	使用
	•	npm 安装命令行小工具
装了 Node.js 之后我们就可以在 Git Bash 里面使用 node 和 npm 这两个命令了，试试看：
``` bash
which node
which npm
node -v
npm -v
```
依次输出看看你得到什么结果。
接下来跟大家展示一下 npm 的威力。我们可以用 npm 的翻译工具做一个随时可用的小字典，这个小工具的名字叫做 fanyi。
运行 
``` bash
npm i -g fanyi 
```
即可安装 fanyi，安装完成之后，输入 
``` bash
fanyi frontend 
```
就可以看到对应的中文释义了！
是不是很帅呢？！
	•	node 的使用
	•	进入 Git Bash
	•	输入 node，回车，就可以进入 node 运行环境，这个时候我们就可以写 JS 了
	•	试试写最简单的 JS 语句，比如 1+2，回车
	•	2 * 8，回车
这就是 node 的第一种使用方式
	•	node 的另一种使用方式
我们可以先创建一个 JS 文件，然后让 node 运行
	•	来到桌面：cd ~/Desktop
	•	新建一个目录用来玩耍：mkdir hello-node
	•	进入这个目录：cd hello-node
	•	新建一个有内容的 JS 文件：echo "console.log('Hi, Node.js')" > main.js，那么 main.js 就新建成功了
	•	输入 node main.js，回车，node 就会执行这个 main.js 文件，你会看到「Hi, Node.js」字样
	•	玩完了，删除 hello-node：cd .. ; rm -rf hello-node

### VSCode的安装和配置
	•	安装
二选一：
	•	从官网下载安装包
安装时把以下选项选中：
图片
	•	使用
	•	找个地方新建一个目录（目录名不要中文），假设目录名为 vs-demo
	•	右键点击该目录，open with code
	•	使用 Ctrl+Shift+E 打开资源管理器，在 vs-demo 目录里新建 HTML 文件，文件名为 index.html
	•	在 index.html 依次输入：英文感叹号、<kbd>回车</kbd> 键，即可看到一个完整的 HTML 页面
	•	由于 vscode 时常更新，如果 <kbd>回车</kbd> 键不行，就试试 <kbd>Tab</kbd> 键
这种快捷写法叫做 Emmet，目前所有的前端编辑器都支持 Emmet。换句话说，如果一个编辑器没有默认支持 Emmet，你就可以卸载这款编辑器了（比如 Sublime Text 括弧笑）。
关于 Emmet 的更多快捷写法，见：
	•	官网的视频介绍
	•	Emmet 作弊表
	•	配置
VSCode 的配置方式就写编辑一个配置文件，打开「文件 - 首选项 - 设置」，对应快捷键为 <kbd>Ctrl</kbd> + <kbd>,</kbd>
图片
左侧为系统默认配置项，右侧为你要覆盖的配置项。把你要修改的项从左边拷贝到右边，然后保存，即可生效。
	•	设置字体与字号
在右侧文件中添加一行（注意末尾要有英文逗号）
"editor.fontSize": 18,
保存，字号就变大了。
设置字体也是类似，添加
"editor.fontFamily": "Consolas, 'Courier New', monospace",
即可将字体设置为你想要的。这里推荐「10大最适合编程的字体推荐下载」，够你玩一上午了。我用的编程字体一般是 Source Code Pro 和 M Plus 这两款。
其实 VSCode 默认的配置就挺好的。
	•	插件安装
VSCode 自带 Emmet、Git 继承和 JS 调试功能（后续会讲到），已经十分完善了，但是还是有一些特殊的需求，这个时候我们就可以安装第三方插件了。由于第三方插件不是微软生产的，所以质量良莠不齐，请注意甄别。
	•	安装 open in browser
按 Ctrl + Shift + X 打开扩展面板，然后输入 open in browser，点击第一个结果的「安装」按钮，稍等片刻就安装好了（相比之下 Sublime 的插件安装体验就差很多）。
然后你在任意 HTML 文件右键，就可以看到 Open In Default Browser 这个按钮了，点就试试看。
	•	Git 操作
要在 VSCode 里面操作 Git，前提是你已经配置好了 Git，如果你没有配置过，那么就在 Git Bash 里输入以下命令：
``` bash
git config --global user.name 你的英文名
git config --global user.email 你的邮箱
git config --global push.default matching 
git config --global core.quotepath false
git config --global core.editor "vim"
```
然后你就可以像视频里面一样，愉快地使用 VSCode 的 Git 功能了。
如果你还希望用 VSCode 将代码推送到 GitHub，那么……待续
### macos
用 macOS 的同学按照如下命令做就行了，比 Windows 的 Git Bash 方便很多。
	•	安装命令行工具
首先你要让命令行翻墙：
	•	如果你有 VPN，直接开启 VPN 即可
	•	如果你的是 Shadowsocks，那么你需要按照 这篇帖子 让命令行翻墙
	•	安装 homebrew
	•	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	•	
	•	安装 proxychains-ng
	•	brew install proxychains-ng
	•	配置proxychains-ng
	•	下载配置文件
	•	 curl -L https://raw.githubusercontent.com/FrankFang/dot-files/master/proxychains.conf > ~/.proxychains.conf
	•	添加 bash alias，运行
	•	 touch ~/.bashrc; echo 'alias pc="proxychains4 -f ~/.proxychains.conf"' >> ~/.bashrc
	•	source ~/.bashrc
	•	pc git clone xxx 或者 pc brew install xxx ，那么这个命令行就是翻墙的。
然后就可以安装工具了
xcode-select --install
如果你是 vpn 就运行：brew install coreutils vim node git wget 
如果你是 SS 就运行：pc brew install coreutils vim node git wget 
npm i -g fanyi
你的 git、node、npm、fanyi 等命令就都有了 :)
	•	安装 iTerm2
https://www.iterm2.com/
iTerm2 比 macOS 自带的 Terminal 好用很多。
配置方法 见此