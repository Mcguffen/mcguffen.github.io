---
title: 脚本
---
	•	理解脚本
如果你打开一本 JavaScript 教程，那么很可能在第一章就看到这句话：
JavaScript 是一门动态类型、面向对象的脚本语言。
然而很多前端工作一年都不清楚这个脚本是什么意思。
其实脚本原本来自戏剧舞台，比如下面这个脚本：
公馆一室内 王妈：（小心翼翼地）小姐，您还是得注意身子，就吃点东西吧。 鸡小姐：（把碗砸在地上）不吃，我就是不吃。 （王妈下）
脚本主要由人物对话和舞台提示组成。演员和道具组只需要按照脚本说的做即可。
编程领域的脚本也是类似的，计算机只要照着脚本上说的做即可，比如下面这个脚本：
cd ~/Desktop
mkdir demo
cd demo
echo "hi" > index.html
cd ~/Desktop
所以说，脚本就是给计算机照着做的。这是我们对「脚本」的一个感性认识。接下来我们写一个脚本。
	•	写一个脚本
	•	找个地方新建文件，后缀随意，一般来说脚本的后缀是 .sh，但是我偏要把后缀写成 .txt。我喜欢把脚本放在 ~/local 目录里。（我知道你没有这个目录，创建一下这个目录就行啦）
	•	mkdir ~/local
	•	cd ~/local
	•	touch demo.txt
	•	编辑 demo.txt，内容如下：
	•	 mkdir demo
	•	 cd demo
	•	 mkdir css js
	•	 touch index.html css/style.css js/main.js
	•	 exit
	•	（Windows 用户请跳过这一步）给 demo.txt 添加执行权限 chmod +x demo.txt
	•	在任意位置执行 sh ~/local/demo.txt 即可运行此脚本
	•	cd ~/Desktop
	•	sh ~/local/demo.txt
	•	你会看到当前目录里多出一个 demo 目录，demo 目录里面还有一些文件 好了，这个 demo.txt 就是你写出的第一个 Bash 脚本了。
	•	将 ~/local 添加到 PATH 里
	•	cd ~/local; pwd 得到 local 的绝对路径
	•	创建 ~/.bashrc：touch ~/.bashrc
	•	编辑 ~/.bashrc：start ~/.bashrc
	•	在编辑器里添加一行字： export PATH="local的绝对路径:$PATH"
	•	local的绝对路径 是什么?
	•	想要知道 local的绝对路径，只需要：
	•	进入 git bash
	•	cd ~/local
	•	pwd
	•	打印出来的东西就是 local的绝对路径！
	•	source ~/.bashrc
	•	之前你要运行 sh ~/local/demo.txt，现在你只需要运行 demo.txt 就行了（想想为什么，道理显而易见）
	•	demo.txt 的后缀 .txt 很无聊，删掉它
	•	mv ~/local/demo.txt ~/local/demo
	•	现在你只要运行 demo 就能执行该脚本了。
	•	细节
	•	PATH 的作用 你每次在 Bash 里面输入一个命令时（比如 ls、cp、demo），Bash 都会去 PATH 列表里面寻找对应的文件，如果找到了就执行。
	•	使用 type demo 可以看到寻找过程
	•	使用 which demo 可以看到寻找结果
	•	文件后缀的作用：毫无作用 你以为一个文件以 .exe 结尾就一定可以双击吗？你以为一个文件以 .png 结尾就一定是图片吗？图样图森破！
	•	参数
demo 脚本只能创建名字为 demo 的目录，太无聊了，我们让目录名是可变的吧。
mkdir $1
cd $1
mkdir css js
touch index.html css/style.css js/main.js
exit
$1 表示你传的第一个参数。
老师你怎么知道 $1 表示第一个参数？
好问题，答案是
我 Google 出来的 http://lmgtfy.com/?q=bash+first+param 用百度也行 http://www.baidu-x.com/?q=bash+%E7%AC%AC%E4%B8%80%E4%B8%AA+%E5%8F%82%E6%95%B0
	•	判断目录是否已存在
if [ -d $1 ]; then
  echo 'error: dir exists'
  exit
else
  mkdir $1
  cd $1
  mkdir css js
  touch index.html css/style.css js/main.js
  echo 'success'
  exit
fi
老师，你怎么知道 -d $1 可以判断目录是否存在？
我 Google 出来的 http://lmgtfy.com/?q=bash+dir+exists
	•	返回值
	•	exit 0 表示没有错误
	•	exit 1 表示错误代码为 1
demo && echo '结束'
只有在 demo 成功时，才会执行 echo '结束'
	•	思考题
我们创建的 index.html style.css 和 main.js 都是空文件，如何给他们填充内容呢？
	•	Node.js 写脚本
上面我们写的脚本叫做 Bash Script（Bash脚本）。
JS 的全称叫做 JavaScript（Java脚本），虽然 JS 和 Java 没什么关系，但是 JS 依然是一种脚本。
	•	我们在 Bash 命令行里输入 Bash 命令，也可以在 Node.js 命令行里输入 JS 命令（<kbd>Ctrl</kbd> + <kbd>D</kbd> 退出）
	•	Bash 脚本能做的事情，JS 脚本也能做。(sh demo.sh 对应 node demo.js）
	•	用 JS 切换目录
console.log(process.cwd()) // 打印当前目录
// process.chdir('~/Desktop'); // 这句话不行的，因为 JS 不认识 ~ 目录
process.chdir("/Users/frank/Desktop")
console.log(process.cwd()) // 打印当前目录
console.log 就相当于 echo
	•	用 JS 脚本创建目录
Google nodejs create dir
文档：https://nodejs.org/api/fs.html#fs_fs_mkdirsync_path_mode
let fs = require("fs")
fs.mkdirSync("demo")
	•	用 JS 脚本创建文件
Google nodejs create file
文档： https://nodejs.org/api/fs.html#fs_fs_writefilesync_file_data_options
let fs = require('fs')
fs.writeFileSync("./index.html", "")
	•	用 JS 脚本来重写 demo.sh
	•	创建 ~/local/jsdemo.js，内容如下
	•	 var fs = require('fs')
	•	
	•	 var dirName = process.argv[2] // 你传的参数是从第 2 个开始的
	•	
	•	 fs.mkdirSync("./" + dirName) // mkdir $1
	•	 process.chdir("./" + dirName) // cd $1
	•	 fs.mkdirSync('css') // mkdir css
	•	 fs.mkdirSync('js') // mkdir js
	•	
	•	 fs.writeFileSync("./index.html", "")
	•	 fs.writeFileSync("css/style.css", "")
	•	 fs.writeFileSync("./js/main.js", "")
	•	
	•	 process.exit(0)
	•	（Windows 用户跳过这一步）给 jsdemo.js 加上执行权限 chmod +x ~/local/jsdemo.js
	•	cd ~/Desktop
	•	node ~/local/jsdemo.js zzz，就可以看到 zzz 目录创建成功了
	•	shebang
我们每次执行 ~/local/jsdemo.js 都要用 node 来执行，能不能做到不加 node 也能执行呢（也就是指定执行环境），可以，在 jsdemo.js 第一行加上这一句即可：
#!/usr/bin/env node
（以下操作在 Windows 上可能失败，失败了就算了）
	•	然后你就可以直接用 ~/local/jsdemo.js zzz 了（省得输入 node 了）。
	•	如果你已经把 ~/local 加入了 PATH，那么甚至可以直接输入 jsdemo.js zzz 来执行。
	•	如果你再把 jsdemo.js 的后缀 .js 去掉，就可以直接 jsdemo zzz 了。
注意，你每次执行前最好删掉 zzz 目录，以免发生冲突。
	•	总结
我们学会了
	•	脚本就是给机器一行一行执行的文本
	•	Bash 脚本有 Bash 脚本的语法，Node.js 脚本有 JS 语法
	•	不管是那种脚本，能实现的功能都差不多，只是语法不同
	•	Bash 脚本的语法挺奇葩的，比如 $1 $# 等符号
	•	不用特别去学 Bash 脚本的用法，遇到不会的就 Google
	•	不用特别去学 Node.js 脚本的用法，遇到不会的就 Google
	•	新人写代码最大的问题就是「抄错了」
	•	多写了一个空格
	•	少写了一个空格
	•	单词拼错了
	•	没有加分号
	•	多加了分号

