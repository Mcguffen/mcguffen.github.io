---
title: 命令行基础，技巧，Git操作,Github Pages,Hexo教程.
date: 2019-06-07
categories:
 - cmd
tags:
 - 命令行基础
---

## 命令行基础，技巧，Git操作,Github Pages,Hexo教程.
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
	•	cd ~/Desktop 进入桌面
	•	mkdir demo-1 创建目录，这时你可以切到桌面，看到 demo-1 目录
	•	rm -rf demo-1 删除目录
	•	touch 1.txt 创建文件，如果你发现文件后缀不见了，请让该死的 Windows 显示文件后缀
	•	mv 1.txt 2.txt 这样我们就把 1.txt 移到 2.txt 了，也就是重命名
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
curl -L https://www.baidu.com > baidu.html
拷贝网页
wget -p -H -e robots=off https://www.baidu.com (Windows 不支持 wget)
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
	•	&& 前面的执行成功了，再执行后面的
	•	|| 前面的执行失败了，就执行后面的
	•	; 前面执行完了，不管成功失败，就执行后面的
	•	> 重定向
	•	| 管道
	•	vim
	•	如何退出 vim
	•	强制退出（不保存）：狂按 ESC，然后按下 :q! 回车
	•	保存后退出：狂按 ESC，然后按下 :wq 回车
是不是很……简……单……
	•	如何学习 vim
vim 被誉为 编辑器之神。
如果你想要入门 vim，下面是三个教程：
	•	在命令行输入 vimtutor ，即可查看官方自带的中文教程。看完它。
	•	简明 VIM 练级攻略
	•	一个 vim 游戏
 ### 命令行技巧
 •	技巧一：~/.bashrc
~/.bashrc 文件的功能很强大。
	•	自动运行
	•	首先 touch ~/.bashrc 创建一下这个文件
	•	start ~/.bashrc 选用编辑器编辑这个文件，内容为 echo 'Hi'
	•	你也可以用命令行编辑文件 echo "echo 'hi'" >> ~/.bashrc
	•	关闭退出 Git Bash，然后打开 Git Bash，是不是看到了 Hi，这说明每次进入 Git Bash，就会优先运行 ~/.bashrc 里面的命令
	•	重新编辑 ~/.bashrc，内容改为 cd ~/Desktop，重启 Git Bash，有没有发现默认就进入桌面目录了？
你可以用 ~/.bashrc 在进入 Git Bash 前执行任何命令，十分方便。
	•	alias
	•	在 ~/.bashrc 里新增一行 alias f="echo 'frank is awesome'"，等于号两边不能有空格，你最好一个字都不要错。
	•	运行 source ~/.bashrc，作用是执行 ~/.bashrc
	•	运行 f，就会看到 frank is awesome
	•	也就是说，现在 f 就是 echo 'frank is awesome' 的缩写了，利用这个技巧，我们可以把很多常见的命令缩写一下，比如
	•	 alias la='ls -a'
	•	 alias ll='ls -l'
	•	 alias gst='git status -sb'
	•	 alias ga='git add'
	•	 alias ga.='git add .'
	•	 alias gc='git commit'
	•	 alias gc.='git commit .'
保存退出，然后运行 source ~/.bashrc
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

### Git操作

用 git 三个月，你就自然理解 git 了。不要试图一开始就理解 git！
	•	配置 GitHub
	•	进入 https://github.com/settings/keys
	•	如果页面里已经有一些 key，就点「delete」按钮把这些 key 全删掉。如果没有，就往下看
	•	点击 New SSH key，你需要输入 Title 和 Key，但是你现在没有 key，往下看
	•	打开 Git Bash
	•	复制并运行 rm -rf ~/.ssh/* 把现有的 ssh key 都删掉，这句命令行如果你多打一个空格，可能就要重装系统了，建议复制运行。
	•	运行 ssh-keygen -t rsa -b 4096 -C "你的邮箱"，注意填写你的邮箱！
	•	按回车三次
	•	运行 cat ~/.ssh/id_rsa.pub，得到一串东西，完整的复制这串东西
	•	回到上面第 3 步的页面，在 Title 输入「我的第一个 key」
	•	在 Key 里粘贴刚刚你你复制的那串东西
	•	点击 Add SSH key
	•	回到 Git Bash
	•	运行 ssh -T git@github.com，你可能会看到这样的提示： 图片 输入 yes 回车……问你话你就答，别傻在那
	•	然后如果你看到 Permission denied (publickey). 就说明你失败了，请回到第 1 步重来，是的，回到第 1 步重来；如果你看到 Hi FrankFang! You've successfully authenticated, but GitHub does not provide shell access. 就说明你成功了！
好了，终于 TMD 添加了一个无聊的 SSH key，不要问我这个有什么用，因为一会儿你就会用到它，你想了解原理就看这篇 文章
如果要讲清楚，太浪费时间了，我们只是想用用 GitHub 而已。
	•	一台电脑只需要一个 SSH key
	•	一个 SSH key 可以访问你的所有仓库，即使你有 1000000 个仓库，都没问题
	•	如果你新买了电脑，就在新电脑上重新生成一个 SSH key，把这个 key 也上传到 GitHub，它可以和之前的 key 共存在 GitHub 上
	•	如果你把 key 从电脑上删除了，重新生成一个 key 即可，替换之前的 key
	•	配置 git
git config --global user.name 你的英文名
git config --global user.email 你的邮箱
git config --global push.default matching
git config --global core.quotepath false
git config --global core.editor "vim"
五句话，依次运行。不执行的话，电脑可能会爆炸你信不信。
	•	使用 git
使用 git 有三种方式，请按照你的需求选择
	•	只在本地使用
	•	将本地仓库上传到 GitHub
	•	下载 GitHub 上的仓库
	•	1 只在本地使用
	•	1.1 初始化
	•	创建目录作为我们的项目目录：mkdir git-demo-1
	•	进入目录 cd git-demo-1
	•	git init，这句命令会在 git-demo-1 里创建一个 .git 目录
	•	ls -la 你就会看到 .git 目录，它就是一个「仓库」，不要进去看，这仓库里面有毒，别进去！
	•	在 git-demo-1 目录里面添加任意文件，假设我们添加了两个文件，分别是 index.html 和 css/style.css
	•	touch index.html
	•	mkdir css
	•	touch css/style.css
	•	运行 git status -sb 可以看到文件前面有 ?? 号
	•	 ## Initial commit on master
	•	 ?? css/
	•	 ?? index.html
这个 ?? 表示 git 一脸懵逼，不知道你要怎么对待这些变动。
	•	使用 git add 将文件添加到「暂存区」
	•	你可以一个一个地 add
	•	git add index.html
	•	git add css/style.css
	•	你也可以一次性 add
	•	git add . 意思是把当前目录（.表示当前目录）里面的变动都加到「暂存区」
	•	再次运行 git status -sb，可以看到 ?? 变成了 A
	•	 ## Initial commit on master
	•	 A  css/style.css
	•	 A  index.html
A 的意思就是添加，也就是说你告诉 git，这些文件我要加到仓库里
	•	使用 git commit -m "信息" 将你 add 过的内容「正式提交」到本地仓库（.git就是本地仓库），并添加一些注释信息，方便日后查阅
	•	你可以一个一个地 commit
	•	git commit index.html -m '添加index.html'
	•	git commit css/style.css -m "添加 css/style.css"
	•	你也可以一次性 commit
	•	git commit . -m "添加了几个文件"
	•	再再次运行 git status -sb，发现没有文件变动了，这是因为文件的变动已经记录在仓库里了。
	•	这时你使用 git log 就可以看到历史上的变动：
	•	 commit f0d95058cd32a332b98967f6c0a701c64a00810a
	•	 Author: Mcguffen
	•	 Date:   Thu Sep 28 22:30:43 2017 +0800
	•	
	•	     添加几个文件
	•	
	•	以上就是 git add / git commit 的一次完整过程，可以看到，挺复杂的。原则上，你错了任何一步，就给我从头来一遍，做到你不会再手抖为止。
	•	1.2 文件变动
如果我想继续改文件，应该怎么做呢？
	•	start css/style.css 会使用默认的编辑器打开 css/style.css（macOS 上对应的命令是 open css/style.css）
	•	然后我们在 css/style.css 里写入 body {background: red}，保存退出
	•	运行 git status -sb 发现提示中有一个 M
	•	 ## master
	•	 M css/style.css
这个 M 的意思就是 Modified，表示这个文件被修改了
	•	此时你如果想让改动保存到仓库里，你需要先 git add css/style.css 或者也可以 git add . 注意，由于这个 css/style.css 以前被我们 add 过，你往文章上面看，我们是 add 过 css/style.css 的，所以此处的 git add 操作可以省略，但我建议你使用 git 的前一个月，不要省略 git add。 换句话说，每一次改动，都要经过 git add 和 git commit 两个命令，才能被添加到 .git 本地仓库里。
	•	再次运行 git status -sb 发现 M 有红色变成了绿色，红色和绿色有啥区别呢？别管它们的区别，记住我说的，先 add，再 commit，等你熟练之后再去理解区别。 先形成肌肉记忆，在去形成大脑记忆！
	•	运行 git commit -m "更新 css/style.css"，这个改动就被提交到 .git 本地仓库了。再说一次，不要去 .git 目录里面，那里的东西你一无所知。
	•	再再次运行 git status -sb，会发现没有变更了，这说明所有变动都被本地仓库记录在案了。 这里来透露一下 git status -sb 是什么意思：git status 是用来显示当前的文件状态的，哪个文件变动了，方便你进行 git add 操作。-sb 选项的意思就是，SB都能看懂，哈，这是开玩笑，-s 的意思是显示总结（summary），-b 的意思是显示分支（branch），所以 -sb 的意思是显示总结和分支。
	•	1.3 总结
至此，我们来总结一下用到的命令
	•	git init，初始化本地仓库 .git
	•	git status -sb，显示当前所有文件的状态
	•	git add 文件路径，用来将变动加到暂存区
	•	git commit -m "信息"，用来正式提交变动，提交至 .git 仓库
	•	如果有新的变动，我们只需要依次执行 git add xxx 和 git commit -m 'xxx' 两个命令即可。别看本教程废话那么多，其实就这一句有用！先 add 再 commit，行了，你学会 git 了。
	•	git log 查看变更历史
	•	2 将本地仓库上传到 GitHub
如何将我们这个 git-demo-1 上传到 GitHub 呢？
	•	在 GitHub 上新建一个空仓库，名称随意，一般可以跟本地目录名一致，也叫做 git-demo-1 图片 按照截图所示，除了仓库名，其他的什么都别改，其他的什么都别改，其他的什么都别改，其他的什么都别改，这样你才能创建一个空仓库
	•	点击创建按钮之后，GitHub 就会把后续的操作全告诉你，如图 请点击一下 ssh 图片
	•	看图，点击 SSH 按钮，点击 SSH 按钮，点击 SSH 按钮，我想你现在肯定不会忘了点击 SSH 按钮了吧~~~~如果不点击这个按钮，你就会使用默认的 HTTPS 地址。但是千万不要使用 HTTPS 地址，因为 HTTPS 地址使用起来特别麻烦，每次都要输入密码，而 SSH 不用输入用户名密码。 为什么 SSH 不用密码呢，因为你已经上传了 SSH public key。还记得吗？如果不记得，翻到本文第一部分「配置 GitHub」章节。
	•	由于我们已经有本地仓库了，所以看图，图中下面半部分就是你需要的命令，我们一行一行拷贝过来执行
	•	找到图中的「…or push an existing repository from the command line」这一行，你会看到 git remote add origin https://github.com/xxxxxxxxxx/git-demo-1.git， 如果你发现这个地址是 https 开头的，那你就做错了，还记得吗，我们要使用 SSH 地址，GitHub 的 SSH 地址是以 git@github.com 开头的。
	•	再次点击 SSH 按钮，不管我强调多少遍，总会有人忘记点击 SSH 按钮，为什么呢？我也不知道，为了防止你忘了点击 SSH 按钮，我最后再说一遍，「点击 SSH按钮」，点击之后，整个世界就会变得美好起来。
	•	得到新的命令 git remote add origin git@github.com:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx/git-demo-1.git，复制并运行它
	•	复制第二行 git push -u origin master，运行它
	•	刷新当前页面，你的仓库就上传到 GitHub 了！是不是特别简单？只要你按照我说的做，一丝不苟，即可。
	•	3 直接在 GitHub 创建一个仓库，然后下载到本地
上面两步讲了
	•	在本地创建仓库
	•	将本地仓库上传到 GitHub
这里将第三种用法，那就是直接在 GitHub 创建一个仓库，然后下载到本地。
	•	在GitHub 上新建一个仓库 git-demo-2，这次就不创建空仓库了，而是自带 README 和 Lisence 的仓库，创建截图如下： 图片 请按图中所示，填写一模一样的内容，然后点击创建按钮。
	•	这样一来，这个仓库就会自动拥有三个文件： 图片
	•	这三个文件的作用请自行了解：.gitignore 的作用、README.md 的作用 以及 LISENCE 的作用
	•	好了，现在远程仓库已经创建好了，怎么下载到我们的本地（也就是我们的电脑上）呢？答案是使用 git clone 命令
	•	点击页面中唯一的绿色按钮「clone or download」，会看到一个弹出层 图片
	•	请确保弹出层里的地址是 SSH 地址，也就是 git@github.com 开头的地址，如果不是，就点击 Use SSH 按钮，就点击 Use SSH 按钮，就点击 Use SSH 按钮。然后复制这个地址。
	•	打开 Git Bash，找一个安全的目录，比如 ~/Desktop 桌面目录就很安全：cd ~/Desktop。运行。
	•	运行 git clone 你刚才得到的以git@github.com开头的地址，运行完了你就会发现，桌面上多出一个 git-demo-2 目录。我再说一遍，桌面上多出一个 git-demo-2 目录。我再说一遍，桌面上多出一个 git-demo-2 目录。这个细节很重要，很多小白发现不了这个细节，我也不知道他们是眼瞎还是怎么了……
	•	进入这个多出来的目录，对的，你肯定会忽略这一步。
	•	进入这个多出来的目录，对的，你肯定会忽略这一步。
	•	进入这个多出来的目录，对的，你肯定会忽略这一步。
	•	好了你进入了这个目录了，如果没有，我就要吐血了，因为我的提示很明显。
	•	运行 ls -la 你会看到，远程目录的所有文件都在这里出现了，另外你还看到了 .git 本地仓库。这是你就可以添加文件，git add，然后 git commit 了。
三种方式都说完了，它们分别是：
	•	在本地创建仓库
	•	将本地仓库上传到 GitHub
	•	下载 GitHub 上的仓库到本地
其实呢，我还可以说很多种不同的方式，但是，你记住这几种就行了，够你用的了。我们并不想要了解 git 的所有高级用法，我们的目的很明确：能通过 Git 命令使用 GitHub 就行。
我们再回顾一遍已经学到的命令：（这次只多了一个 git clone 命令）
	•	git clone git@github.com:xxxx，下载仓库
	•	git init，初始化本地仓库 .git
	•	git status -sb，显示当前所有文件的状态
	•	git add 文件路径，用来将变动加到暂存区
	•	git commit -m "信息"，用来正式提交变动，提交至 .git 仓库
	•	如果有新的变动，我们只需要依次执行 git add xxx 和 git commit -m 'xxx' 两个命令即可。别看本教程废话那么多，其实就这一句有用！先 add 再 commit，行了，你学会 git 了。
	•	git log 查看变更历史
	•	如何上传更新
你在本地目录有任何变动，只需按照以下顺序就能上传：
	•	git add 文件路径
	•	git commit -m "信息"
	•	git pull （相信我，你一定会忘记这一个命令）
	•	git push
下面是例子
	•	cd git-demo-1
	•	touch index2.html
	•	git add index2.html
	•	git commit -m "新建 index2.html"
	•	git pull
	•	git push
然后你去 git-demo-1 的 GitHub 页面，就能看到 index2.html 出现在里面了。是不是很……简……单……呢……
	•	git ignore
在项目目录创建 .gitignore 文件就可以指定「哪些文件不上传到远程仓库」，比如
.gitignroe
/node_modules/
/.vscode/
这样就可以避免 node_modules/ 和 .vscode/ 目录被上传到 github 了。
	•	记住一句话：永远都不要上传 node_modules 到 github。
	•	其他
还有一些有用的命令
	•	git remote add origin git@github.com:xxxxxxx.git 将本地仓库与远程仓库关联
	•	git remote set-url origin git@github.com:xxxxx.git 上一步手抖了，可以用这个命令来挽回
	•	git branch 新建分支
	•	git merge 合并分支
	•	git stash 通灵术
	•	git stash pop 反转通灵术
	•	git revert 后悔了
	•	git reset 另一种后悔了
	•	git diff 查看详细变化
学 git 命令都够你们学一周的，所以别妄想现在就掌握它，切记。

资源
	•	常用 Git 命令清单
	•	读懂 diff - 阮一峰
	•	搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门
	•	Git 菜鸟教程
	•	廖雪峰的 Git 教程

### 使用 GitHub Pages 预览 HTML
  注意只能预览 HTML，不能预览 Markdown。
	•	在 GitHub 新建一个仓库 x1
	•	在 x1 里面新建一个 HTML 比如 y1.html，文件内容为「<h1>这是一个HTML</h1>」
	•	新建文件的方法可以是使用 git add git commit git push
	•	也可以是直接在网页上操作，随便你怎么新建文件
	•	点击 Settings
	•	往下滚动页面
	•	选中 master branch 然后点击 Save 图片
	•	得到一个预览链接，假设预览链接是 https://zzzzzzzzz/ 图片
	•	访问 https://zzzzzzzzz/y1.html 即可预览 y1.html
	•	新建 y2.html，git add git commit git push，等一分钟，访问 https://zzzzzzzzz/y2.html 即可预览 y2.html
	•	新建 y3.html，git add git commit git push，等一分钟，访问 https://zzzzzzzzz/y3.html 即可预览 y3.html
### Hexo 教程
	•	注意：如果你使用的是 Windows 系统，Hexo 很容易安装不成功
如果不成功，二选一：
	•	你就放弃 Hexo，使用简书、知乎、segmentfault、掘金等工具写博客。
	•	你就放弃 Windows，改用 Linux，教程
	•	使用 Hexo + GitHub 可以轻松搞出一个好看的博客
以下是步骤。
	•	进入一个安全的目录，比如 cd ~/Desktop 或者 cd ~/Documents，别在根目录 / 瞎搞。以后所有的教程第一步都是「进入一个安全的目录，别在根目录瞎搞」，只有 ~ 里面的目录是你能碰的！
	•	在 GitHub 上新建一个空 repo，repo 名称是「你的用户名.github.io」（注意个用户名是你的GitHub用户名，不是你的电脑用户名）
	•	npm install -g hexo-cli，安装 Hexo
	•	hexo init myBlog
	•	cd myBlog
	•	npm i
	•	hexo new 开博大吉，你会看到一个 md 文件的路径 Windows 的路径中的 \ 需要变成 / 才行哦
	•	start xxxxxxxxxxxxxxxxxxx.md，编辑这个 md 文件，内容自己想（Ubuntu 系统用 xdg-open xxxxxxxxxxxxxxxxxxx.md 命令）
	•	start _config.yml，编辑网站配置
	•	把第 6 行的 title 改成你想要的名字
	•	把第 9 行的 author 改成你的大名
	•	把最后一行的 type 改成 type: git
	•	在最后一行后面新增一行，左边与 type 平齐，加上一行 repo: 仓库地址（请将仓库地址改为「你的用户名.github.io」对应的仓库地址，仓库地址以 git@github.com: 开头你知道吧？不知道？不知道的话现在你知道了）
	•	第 4 步的 repo: 后面有个空格，不要眼瞎。
	•	npm install hexo-deployer-git --save，安装 git 部署插件
	•	hexo deploy
	•	进入「你的用户名.github.io」对应的 repo，打开 GitHub Pages 功能，如果已经打开了，就直接点击预览链接
	•	你现在应该看到了你的博客！
	•	第二篇博客
	•	hexo new 第二篇博客
	•	复制显示的路径，使用 start 路径 来编辑它
	•	hexo generate
	•	hexo deploy
	•	去看你的博客，应该能看到第二篇博客了
	•	换主题
	•	https://github.com/hexojs/hexo/wiki/Themes 上面有主题合集
	•	随便找一个主题，进入主题的 GitHub 首页，比如我找的是 https://github.com/iissnan/hexo-theme-next
	•	复制它的 SSH 地址或 HTTPS 地址，假设地址为 git@github.com:iissnan/hexo-theme-next.git
	•	cd themes
	•	git clone git@github.com:iissnan/hexo-theme-next.git
	•	cd ..
	•	将 _config.yml 的第 75 行改为 theme: hexo-theme-next，保存
	•	hexo generate
	•	hexo deploy
	•	等一分钟，然后刷新你的博客页面，你会看到一个新的外观。如果不喜欢这个主题，就回到第 1 步，重选一个主题。
	•	上传源代码
注意「你的用户名.github.io」上保存的只是你的博客，并没有保存「生成博客的程序代码」，你需要再创建一个名为 blog-generator 的空仓库，用来保存 myBlog 里面的「生成博客的程序代码」。
	•	在 GitHub 创建 blog-generator 空仓库
图片
	•	按照截图中的命令执行即可，记住，别 TMD 用 HTTPS 地址。
这样一来，你的博客发布在了「你的用户名.github.io」而你的「生成博客的程序代码」发布在了 blog-generator。所有数据万无一失，你就不会因为误删 myBlog 目录而痛哭了。
以后每次 hexo deploy 完之后，博客就会更新；然后你还要要 add / commit /push 一下「生成博客的程序代码」，以防万一。
这个 blog-generator 就是用来生成博客的程序，而「你的用户名.github.io」仓库就是你的博客页面。
