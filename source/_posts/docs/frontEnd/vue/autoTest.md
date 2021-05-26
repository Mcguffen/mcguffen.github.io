---
title: 自动化测试和持续化集成
date: 2020-06-20
categories:
 - frontEnd
tags:
 - vue
 - karma
 - mocha
 - chai
 - travis ci
---
# 测试
## 测试方法
- BDD 行为驱动开发（behavior driven development）
也就是用自然语言描述需求
```
expect(button).to.be.true
```
是不是很像我们平常说的英语，I expect button to be true

chai库就是用来做这件事的
- TDD 测试驱动开发（test driven development）
用例实现完了，开发也就完成了
先把测试用例写好，根据测试开发.

assert断言，浏览器上存在这样的api ：assert 这也是我们测试用到的核心，这个api能够判断是否为真
```
console.assert(1===1)
undefined
console.assert(1===2)
Assertion failed: console.assert
undefined
```

如果我断言了一个假信息，浏览器会抛出错误


## 单元测试

## 使用karma+mocha进行单元测试单元测试
了解了测试的原理与方法，现在开始动手写自动化测试吧
1.安装各种工具：
- karma是一个基于Node.js的JavaScript测试执行过程管理工具，karma能让你的代码在一个无头浏览器上运行。
- Mocha是一个测试框架，在vue-cli中配合chai断言库实现单元测试。
安装
```
npm i -D karma karma-chrome-launcher karma-mocha karma-sinon-chai mocha sinon sinon-chai karma-chai karma-chai-spies

```
2. 创建karma的配置
新建一个karma.conf.js 这个配置文件定义了使用的测试框架，测试文件入口，打开的测试浏览器，端口等等
```js
module.exports = function (config) {
     config.set({

         // base path that will be used to resolve all patterns (eg. files, exclude)
         basePath: '',
            // frameworks to use
            // available frameworks: https://npmjs.org/browse/keyword/karma-adapter
            frameworks: ['mocha', 'sinon-chai'],
            client: {
                chai: {
                    includeStack: true
                }
            },


            // list of files / patterns to load in the browser
            files: [
                'dist/**/*.test.js',
                'dist/**/*.test.css'
            ],


            // list of files / patterns to exclude
            exclude: [],


            // preprocess matching files before serving them to the browser
            // available preprocessors: https://npmjs.org/browse/keyword/karma-preprocessor
            preprocessors: {},


            // test results reporter to use
            // possible values: 'dots', 'progress'
            // available reporters: https://npmjs.org/browse/keyword/karma-reporter
            reporters: ['progress'],


            // web server port
            port: 9876,


            // enable / disable colors in the output (reporters and logs)
            colors: true,


            // level of logging
            // possible values: config.LOG_DISABLE || config.LOG_ERROR || config.LOG_WARN || config.LOG_INFO || config.LOG_DEBUG
            logLevel: config.LOG_INFO,


            // enable / disable watching file and executing tests whenever any file changes
            autoWatch: true,


            // start these browsers
            // available browser launchers: https://npmjs.org/browse/keyword/karma-launcher
            browsers: ['ChromeHeadless'],


            // Continuous Integration mode
            // if true, Karma captures browsers, runs the tests and exits
            singleRun: false,

            // Concurrency level
            // how many browser should be started simultaneous
            concurrency: Infinity
        })
    }
```

3.创建test/button.test.js 文件
这个文件中我们就要开始写自己的测试代码了

我们使用BDD 行为驱动测试，根据这个组件的行为来设计测试用例，比如我们对button组件进行测试，这里我举了两个列子，实际情况下测试用例比这个要多的多

首先我们要从chai库中引入expect用来进行断言

然后引入我们的组件和vue

我们第一个用例用来说明这个组件是存在的

我们第二个用例用来证明这个组件有props：icon属性，我们首先对组件所有的props进行测试：具体的测试方法：
- 我们创建一个button的构造函数，然后去实例化一个button出来
- 给我们的button传入一个icon的propsData，并将这个button挂载到页面上
- 我们通过拿到这个button下面的use标签（引入的iconfont。下面的标签结构都是svg>use）的索引，和我们的props比较，看是否是我们设置的icon

我们第三个用例用来证明组件的事件是否可以触发

- 同样的创建一个button实例
- 使用sinon.fake（）创建一个回调函数，让这个button触发click事件之后调用这个函数
- 如果这个函数被调用了，就说明我们的click事件可以正常执行
```
 const expect = chai.expect;
 import Vue from 'vue'
 import Button from '../src/button'
 Vue.config.productionTip = false
 Vue.config.devtools = false
describe('Button', () => {
     it('存在.', () => {
         expect(Button).to.be.ok
     })
     it('可以设置icon.', () => {
         const Constructor = Vue.extend(Button)
         const vm = new Constructor({
         propsData: {
             icon: 'settings'
         }
         }).$mount()
         const useElement = vm.$el.querySelector('use')
         expect(useElement.getAttribute('xlink:href')).to.equal('#i-settings')
         vm.$destroy()
     })
    it('点击 button 触发 click 事件', () => {
         const Constructor = Vue.extend(Button)
         const vm = new Constructor({
         propsData: {
             icon: 'settings',
         }
         }).$mount()

         const callback = sinon.fake();
         vm.$on('click', callback)
         vm.$el.click()
         expect(callback).to.have.been.called

     })
})
```
4. 创建测试脚本 在 package.json 里面找到 scripts 并改写 scripts
首先打包test下面的一级文件，移除缓存，启动karma。
```
"scripts": {
     "dev-test": "parcel watch test/* --no-cache & karma start",
     "test": "parcel build test/* --no-cache --no-minify && karma start --single-run"
 }
```
5. 运行测试脚本
```
先删掉缓存
rm -rf .cache dist
```
我们可以使用npm run test进行一次运行

这样做的效果是，我们每次改了代码都要跑一次npm run test

也可以使用npm run dev-test 进行 watch 运行

这样我们每次改代码都会在后台自动运行test
## 使用travis ci持续集成
有了上面的自动化测试方法，我们已经可以很方便的在每次修改代码之后，都自动运行测试用例

但是这种方法还是需要你在自己的终端里去运行，有没有可能我去雇一个保姆，去帮我运行测试脚本呢

travis ci就是这个保姆

你每次提交代码，travis ci都会帮你去吧测试脚本跑一遍

首先在项目根目录新建一个.travis.yml，里面写上用什么语言测试，用nodejs的哪几个版本
```
language: node_js
node_js:
  - "10"
  - "11"
  - "12"
addons:
  chrome: stable
sudo: required
before_script:
  - "sudo chown root /opt/google/chrome/chrome-sandbox"
  - "sudo chmod 4755 /opt/google/chrome/chrome-sandbox"
```
然后去travis ci网站。将你的github项目添加进去
一旦测试出现问题会给你发邮件哦

