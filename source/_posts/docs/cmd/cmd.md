---
title: 命令行基础
date: 2019-06-07
categories:
 - cmd
tags:
 - 命令行基础
---

## 命令行基础
### 命令行基础

• 命令行是什么
实际上是先有命令行，后有的图形界面。最开始的游戏也是在命令行上的。
世界上第一个程序员（女）也是通过命令行来编程的，所以一个程序员不学命令行是说不过去的。

• 如何学习
首先背单词：
英文
翻译
directory
目录、文件夹
file
文件
make
新建
remove
删除
move
移动
copy
复制
list
罗列
link
链接
find
查找
echo
发出回音、重复
touch
触摸
change
改变
背下来了吗？每个单词都很短，应该不难背。好的，你基本已经学会命令行了。接下来我们学习这些单词的缩写
	•	缩写
命令
全写
缩写
创建目录
make directory
mkdir
删除
remove
rm
移动 / 重命名
move
mv
复制
copy
cp
罗列
list
ls
改变目录
change directory
cd
缩写规则就是：删掉元音字幕（A E I O U），保留前 2 到 3 个辅音字母
好了，你已经学会 50% 了，接下来我们来试试。
	•	试试
	•	cd ~/Desktop 进入桌面
	•	mkdir demo-1 创建目录，这时你可以切到桌面，看到 demo-1 目录
	•	rm -rf demo-1 删除目录
	•	touch 1.txt 创建文件，如果你发现文件后缀不见了，请让该死的 Windows 显示文件后缀
	•	mv 1.txt 2.txt 这样我们就把 1.txt 移到 2.txt 了，也就是重命名
	•	绝对路径与相对路径的区别
以 / 开头的路径就是绝对路径，具体区别，在下面用命令行体会。
	•	常见的自带命令
操作
命令
进入目录
cd
显示当前目录
pwd
创建目录
mkdir 目录名
创建目录
mkdir -p 目录路径
我是谁
whoami
--
--
查看路径
ls 路径
查看路径
ls -a 路径
查看路径
ls -l 路径
查看路径
ls -al 路径
--
--
创建文件
echo '1' > 文件路径
强制创建文件
echo '1' >! 文件路径
追加文件内容
echo '1' >> 文件路径
创建文件
touch 文件名
改变文件更新时间
touch 文件名
--
--
复制文件
cp 源路径 目标路径
复制目录
cp -r 源路径 目标路径
--
--
移动节点
mv 源路径 目标路径
--
--
删除文件
rm 文件路径
强制删除文件
rm -f 文件路径
删除目录
rm -r 目录路径
强制删除目录
rm -rf 目录路径
--
--
查看目录结构
tree
建立软链接
ln -s 真实文件 链接
--
--
下载文件
curl -L https://www.baidu.com > baidu.html
拷贝网页
wget -p -H -e robots=off https://www.baidu.com (Windows 不支持 wget)
磁盘占用
df -kh
当前目录大小
du -sh .
各文件大小
du -h
如何学习我目前还没有掌握的命令？
Google: Linux 查看文件内容
	•	快捷键
	•	<kbd>↑</kbd> <kbd>↓</kbd> 上一命令 / 下一命令
	•	<kbd>!</kbd><kbd>!</kbd> 上一命令占位符
	•	<kbd>Tab</kbd> 自动补全路径
	•	<kbd>Alt</kbd>+<kbd>.</kbd> 上一命令的最后一个参数
	•	&& 前面的执行成功了，再执行后面的
	•	|| 前面的执行失败了，就执行后面的
	•	; 前面执行完了，不管成功失败，就执行后面的
	•	> 重定向
	•	| 管道
	•	vim
	•	如何退出 vim
	•	强制退出（不保存）：狂按 ESC，然后按下 :q! 回车
	•	保存后退出：狂按 ESC，然后按下 :wq 回车
是不是很……简……单……
	•	如何学习 vim
vim 被誉为 编辑器之神。
如果你想要入门 vim，下面是三个教程：
	•	在命令行输入 vimtutor ，即可查看官方自带的中文教程。看完它。
	•	简明 VIM 练级攻略
	•	一个 vim 游戏
 ### 命令行技巧
 •	技巧一：~/.bashrc
~/.bashrc 文件的功能很强大。
	•	自动运行
	•	首先 touch ~/.bashrc 创建一下这个文件
	•	start ~/.bashrc 选用编辑器编辑这个文件，内容为 echo 'Hi'
	•	你也可以用命令行编辑文件 echo "echo 'hi'" >> ~/.bashrc
	•	关闭退出 Git Bash，然后打开 Git Bash，是不是看到了 Hi，这说明每次进入 Git Bash，就会优先运行 ~/.bashrc 里面的命令
	•	重新编辑 ~/.bashrc，内容改为 cd ~/Desktop，重启 Git Bash，有没有发现默认就进入桌面目录了？
你可以用 ~/.bashrc 在进入 Git Bash 前执行任何命令，十分方便。
	•	alias
	•	在 ~/.bashrc 里新增一行 alias f="echo 'frank is awesome'"，等于号两边不能有空格，你最好一个字都不要错。
	•	运行 source ~/.bashrc，作用是执行 ~/.bashrc
	•	运行 f，就会看到 frank is awesome
	•	也就是说，现在 f 就是 echo 'frank is awesome' 的缩写了，利用这个技巧，我们可以把很多常见的命令缩写一下，比如
	•	 alias la='ls -a'
	•	 alias ll='ls -l'
	•	 alias gst='git status -sb'
	•	 alias ga='git add'
	•	 alias ga.='git add .'
	•	 alias gc='git commit'
	•	 alias gc.='git commit .'
保存退出，然后运行 source ~/.bashrc
	•	这样一来，你的 Git 操作就会简单很多：
	•	 ga 1.txt
	•	 ga .
	•	 gc 1.txt
	•	 gc.
	•	 gst
接下来说两个目前用不到的技巧。
	•	环境变量
还可以在 ~/.bashrc 里面设置一些环境变量，比如你可以在 ~/.bashrc 里面添加一行
export SASS_BINARY_SITE="https://npm.taobao.org/mirrors/node-sass"
那么以后你安装 node-sass 的时候就不会因为被墙而报错了。以后会用到的，现在先说一下。
	•	设置 PATH
export PATH="目录的绝对路径:$PATH"
这句话可以在 PATH 里添加一个目录。看不懂这句话没关系，等你用得到的时候你再回来看。