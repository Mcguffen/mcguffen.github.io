---
title: Hello World.I am yang.
date: 2021-03-09
categories:
 - blog
tags:
 - 建站
---
Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).

# 建站说明
- 基础功能
- github pages
- 自动化部署 github actions
- 在线编辑文章

## 全局安装hexo-cli
``` bash
$ sudo npm install -g hexo-cli
```

## 初始化hexo项目
cd到指定项目文件夹 hexo-blog是项目名
``` bash
$ hexo init hexo-blog
```

## Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

## hexo项目目录声明
![hexo项目目录声明](https://sm.ms/image/8QI7KbkVlyWa6pO)

## 更换主题
``` bash
$ cd themes/cactus
```
下载喜欢的主题到该文件夹
删除下载的主题默认的 .git文件
为了让主题和项目统一用git来管理。
然后配置根目录下的congfig.yml文件。
找到theme属性修改成你下载的主题名
本地运行项目查看是否生效
``` bash
$ hexo server
```
## 将本地项目部署到github pages
首先要有GitHub账号，创建项目时项目名有两种方式
- 方式1： https://[username].github.io  仓库名必须为[username].github.io打包产物放到master分支，优势是访问路径短。
- 方式2： https://[username].github.io/[repo]  自定义仓库名，打包产物放在gh-pages分支，这种更适合将开源项目用于展示。
选用第一种来展示。

### 使用git命令初始化项目以及添加项目的远程仓库地址

### 安装hexo-deployer-git库
帮助我们把本地代码部署到一个具体的远程仓库分支
``` bash
$ yarn add hexo-deployer-git
```

### 配置config.yml文件
修改根目录config.yml文件
```
deploy:
 type: git
 repo: 项目地址
 branch: master
```

### 运行npm run deploy部署代码到远程仓库
``` bash
$ npm run deploy
```
或者
``` bash
hexo deploy
```
会将本地项目生成的public目录下的文件上传到github仓库
### 在GitHub设置中选择master分支来展示项目网站
GitHub Pages
GitHub Pages is designed to host your personal, organization, or project pages from a GitHub repository.

 Your site is published at https://mcguffen.github.io/
至此 ,HEXO本地项目就被打包放到了github pages了。

## 自动化部署
### 先将源码上传到GitHub
由于master分支被占用，所以创建新的分支my-blog分支。
将代码上传到my-blog分支
``` bash
git add .
git commit -m '提交源码到my-blog分支'
git push --set-upstream origin myblog
```
### GitHub Actions自动化部署
实现项目的自动打包和部署
创建.github/workflow文件夹
在文件夹下创建.yml文件
比如feploy.yml文件
```
name: Build and Deploy
on: [push]
jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout 🛎️
        uses: actions/checkout@v2 # If you're using actions/checkout@v2 you must set persist-credentials to false in most cases for the deployment to work correctly.
        with:
          persist-credentials: false

      - name: Install and Build 🔧 # This example project is built using npm and outputs the result to the 'build' folder. Replace with the commands required to build your project, or remove this step entirely if your site is pre-built.
        run: |
          npm install
          npm run build
        env:
          CI: false

      - name: Deploy 🚀
        uses: JamesIves/github-pages-deploy-action@releases/v3
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          BRANCH: master # The branch the action should deploy to.
          FOLDER: public # The folder the action should deploy.
```
checkout安装一打包构建，最后触发一个代码的部署。
修改文章内容，验证是否自动化部署成功。
修改文章内容后使用git 上传代码
```
git add .
git commit -m 'feat:add github actions 验证是否自动化部署成功'
git push
```
