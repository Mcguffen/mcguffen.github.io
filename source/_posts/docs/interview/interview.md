---
title: interview
date: 2021-07-27
categories:
 - frontEnd
tags:
 - interview
---
# 面试题
 抽象问题具体化
 原理说一下思路

## HTML

1. 必考：你是如何理解 HTML 语义化的？
   1. 举例法
      HTML 语义化就是使用正确的标签（总结）段落就写 p 标签，标题就写 h1 标签，文章就写article标签，视频就写video标签，等等。
   2. 阐述法
      首先讲以前的后台开发人员使用table布局，然后讲美工人员使用div+css布局，最后讲专业的前端会使用正确的标签进行页面开发。
      说到HTML语义话，我们得先从原始的页面开始说起，起初页面是由后端的人员编写的，页面也肯定不好看，然后就是div+css编写，整个网页都是div，为了改变这种这种状况，
      开发者们和官方提出了让HTML结构语义化的概念，并且官方w3c，也在HTML5给出了几个新的语义化的标签。总而言之就是要在合适的地方使用合适的标签，比如
      1.article标签代表一个在文档，页面或者网站中自成一体的内容，其目的是为了让开发者独立开发或重用。
      2.em标签和strong标签都表示强调的标签，但是其中em表示语义上的强调，strong表示内容上的强调
      3.nav元素代表页面的导航链接区域。用于定义页面的主要导航部分。但是我在有些时候却情不自禁的想用它，譬如：侧边栏上目录，面包屑导航，搜索样式，或者下一篇上一篇文章，但是事实上规范上说nav只能       用在页面主要导航部分上。
2. meta viewport 是做什么用的，怎么写？
   举例法
   `<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, minimum-scale=1">`
   然后逐个解释每个单词的意思。
   这个标签标识是编写移动端页面的，是为了使我们编写的页面可以在手机等设备上显示的标签，可以回答一般都是打开淘宝网页，然后打开开发者模式然后切换到移动端直接复制其中的meat viewport标签（这样回答    应该就可以了）
3. 你用过哪些 HTML 5 标签？
   举例法
   平时如果只用div写页面你就完了，把你平时用到的html5标签列举出来即可，但是要注意如果这个标签的用法比较复杂，你要先看一下MDN的文档再说这个标签；如果你说出一个标签，却不知道它有哪些API，那么你    就会被扣分。
   回答：HTML5里面新增加了语义化标签article（表示文章，博客条目），nav（表示定义导航链接的部分。）、header（定义文档的页眉）等标签，和一些其他的video（定义视频，比如电影片段或其他视频流）、      audio（定义声音，比如音乐或其他音频流）、canvas（用来定义图形容器，必须使用脚本来绘制图形)标签.


4. H5 是什么？
   阐述法
   搜一下知乎就知道了，H5表示移动端页面，反正不是HTML5。
   注意这里的H5不单单是HTML5，HTML5并不是一项技术，而是一个标准。”H5“本应是一个技术合集，却被意会成了一项技术，变成可以在质上而不是量上描述的概念。现在多用于微信上面微场景，就是那种打开之后有    动画，有音乐的东西。这项技术的应用已经在当下广泛应用于移动营销，在移动广告方面。目前h5在移动端的开发方面起着重大的作用。

## CSS

1. 必考：两种盒模型分别说一下。
   CSS中的两种盒模型指的是content-box和border-box,他们是通过box-sizing来设置的,
   默认是content-box,他们两者的区别是content-box的宽度只有内容区,
   而border-box的宽度包括边框,内边距和内容区,
   平时我一般使用的是border-box,因为border-box更符合我们对盒子的认识

2. 必考：如何垂直居中？
   背代码 https://www.yuque.com/docs/share/708bd899-0c46-47ea-a94c-d7a189c0f7dc?# 《七种方式实现垂直居中》
   1.可以使用table的自带居中功能,用一个一行一列的table,里面的文字会自动居中
   2.将div装成table,声明三个嵌套的div,让他们分别
   display:table,display:table-row,display:table-cell,然后display:table-cell中的内容就会居中
   3.父元素相对定位,子元素绝对定位,然后子元素left,top的值为50%,之后再用负margin分别为
   子元素宽度和高度的一半就可以居中
   4.还是上面的那种办法,父元素相对定位,子元素绝对定位,偏移量为50%,
   但是这次不用负margin,用transform的translate(-50%)来让子元素居中
   5.父元素相对定位,子元素绝对定位,然后让偏移量都为0,把margin设置为auto,
   这样子元素就hi居中
   6.还有就是flex布局,让父元素的justifiy-content和align-items的值都为center.
   7.在子元素的前面加上两个高度为100%的inline-block元素,并且设置verticel-align,
   然后让父元素的text-align的值为center,这样中间的那个inline-block子元素就能居中

3. 必考：flex 怎么用，常用属性有哪些？
   看 MDN，背代码。
   flex是一种用于按行或按列布局元素的一维布局方法,
   元素可以膨胀以填充额外的空间, 收缩以适应更小的空间
   平时我使用的常见属性有 父元素:justify-content,align-items,flex-direction,flex-wrap,
   子元素:order,flex.
   一般问这个问题都会再问你一个例子,如果被问到,记着随机应变.

   一般问完flex之后很有可能会接着问grid布局,我这里写一下我的答案。
   grid布局我一般使用的时候是父元素设置display:flex,然后通过grid来画它的行列,之后在子元素上
   通过grid-column和grid-row来分配它的位置

4. 必考：BFC 是什么？
   BFC 全称 block formatting context ，中文译作「块格式化上下文」。
   背 BFC 触发条件，
   

   MDN 写了

   。

   但是不用全部背下来，面试官只知道其中几个：

   1. 浮动元素（元素的 float 不是 none）
   2. 绝对定位元素（元素的 position 为 absolute 或 fixed）
   3. 行内块元素
   4. overflow 值不为 visible 的块元素
   5. 弹性元素（display为 flex 或 inline-flex元素的直接子元素）
   BFC的英文是block-formatting-context,中文意思就是块格式化上下文,一个元素开启BFC之后
   这个元素会包裹它内部的浮动元素,使内部的元素和外部隔开,
   内部子元素再怎么翻江倒海，翻云覆雨都不会影响外部的元素,在开启BFC内的兄弟元素之间margin
   会合并,开启BFC的方法有浮动元素,绝对定位的元素,行内块元素,overflow不是visible的元素,
   一般的开启BFC的方式是overflow:hidden,但是会有副作用,新的开始BFC的方式是display:flow-root
   5. CSS 选择器优先级

   1. 背人云亦云的答案（错答案、已过时）：https://www.cnblogs.com/xugang/archive/2010/09/24/1833760.html
   2. 看面试官脸色行事
   3. 方方给的三句话
      1. 越具体优先级越高
      2. 同样同级别的优先级写在后面的覆盖写在前面的
      3. !important 优先级最高，但是要少用

6. 清除浮动说一下

   背代码

   ```css
    .clearfix:after{
        content: '';
        display: block; /*或者 table*/
        clear: both;
    }
    .clearfix{
        zoom: 1; /* IE 兼容*/
    }
   ```

## 原生 JS

1. 必考：ES 6 语法知道哪些，分别怎么用？
   举例法
   let const 箭头函数 Promise 展开操作符 默认参数 import export，见[方方整理的列表](https://fangyinghang.com/es-6-tutorials/)
   ES6中的let 和const声明变量的用法我一直再用,还有新的解构赋值还挺方便的,其他的还有箭头函数。还有一些数组和函数的拓展API
   注意:这里能不说promise就不要说promise,不说面试官很有可能会问,说了面试官一定会问,还有可能会说:"那你能手写一个promise这种送命题".

2. 必考 Promise、Promise.all、Promise.race 分别怎么用？
   2021年的面试题不仅会问promise还会问它的这两个API,因为之前promise刚出来所以只要会用就可以了,现在要求知道这两个API.给大家一个参考链接:
   [参考链接](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise)
   
   在promise没有出现之前函数的回调总是五花八门的,而且调用的时候总是容易出现回调地狱,也很难进行
   错误处理,所以就有了promise,promise对象有三种状态:
   进行中(pending),已成功(fulfilled),失败(rejected),
   当promise状态从pending到fulfilled了就执行resolve回调,当promise状态从pending到rejected就执行reject回调,
   回调函数是通过.then通过链式操作定义的,其中Promise.all是将多个promise包装成一个新的promise实例的,如果这多个promise的
   状态都为fulfilled就然会一个fulfilled,promise实例,如果有一个错误就是返回rejected实例
   Promise.race()方法也是将多个promise包装成一个,但是跟Promise.all不同的是最后的返回的promise对象实例的状态是由率先改变状态的那个promise决定的.
   [参考链接](https://zhuanlan.zhihu.com/p/159417958)
 
   
   1. 背代码 Promise 用法

      ```js
       function fn(){
           return new Promise((resolve, reject)=>{
               成功时调用 resolve(数据)
               失败时调用 reject(错误)
           })
       }
       fn().then(success, fail).then(success2, fail2)
      ```

   2. 背代码 Promise.all 用法

      ```js
       Promise.all([promise1, promise2]).then(success1, fail1)
      ```

      promise1和promise2都成功才会调用success1

   3. 背代码 Promise.race 用法

      ```js
       Promise.race([promise1, promise2]).then(success1, fail1)
      ```

      promise1和promise2只要有一个成功就会调用success1；

      promise1和promise2只要有一个失败就会调用fail1；

      总之，谁第一个成功或失败，就认为是race的成功或失败。

3. 必考：手写函数防抖和函数节流
   1. 背代码
函数节流就是在触发一个事件后在一段事件后执行一段代码,如果在这一段事件内再次触发这个事件,则无视该事件,等这一段代码执行完毕之后才可以重新触发.
      ```js
       // 节流（一段时间执行一次之后，就不执行第二次）
       function throttle(fn, delay){
           let canUse = true
           return function(){
               if(canUse){
                   fn.apply(this, arguments)
                   canUse = false
                   setTimeout(()=>canUse = true, delay)
               }
           }
       }
      
       const throttled = throttle(()=>console.log('hi'))
       throttled()
       throttled()
      ```

      注意，有些地方认为节流函数不是立刻执行的，而是在冷却时间末尾执行的（相当于施法有吟唱时间），那样说也是对的。

   2. 背代码
函数防抖就是在触发一个事件之后执行一段代码,如果在这一段事件内继续触发该事件,则需要重新等待这一段时间后再执行代码
      ```js
       // 防抖（一段时间会等，然后带着一起做了）
       function debounce(fn, delay){
           let timerId = null
           return function(){
               const context = this
               if(timerId){window.clearTimeout(timerId)}
               timerId = setTimeout(()=>{
                   fn.apply(context, arguments)
                   timerId = null
               },delay)
           }
       }
       const debounced = debounce(()=>console.log('hi'))
       debounced()
       debounced()
      ```

4. 必考：手写AJAX

   1. 背代码，完整版

      ```js
       var request = new XMLHttpRequest()
       request.open('GET', '/a/b/c?name=ff', true);
       request.onreadystatechange = function () {
         if(request.readyState === 4 && request.status === 200) {
           console.log(request.responseText);
         }};
       request.send();
      ```

   2. 背代码，简化版

      ```js
       var request = new XMLHttpRequest()
       request.open('GET', '/a/b/c?name=ff', true)
       request.onload = ()=> console.log(request.responseText)
       request.send()
      ```

5. 必考：这段代码里的 this 是什么？

   1. 背代码
      1. fn()
         this => window/global
      2. obj.fn()
         this => obj
      3. fn.call(xx)
         this => xx
      4. fn.apply(xx)
         this => xx
      5. fn.bind(xx)
         this => xx
      6. new Fn()
         this => 新的对象
      7. fn = ()=> {}
         this => 外面的 this
        
 有时候我们使用函数名加括号来调用函数,其实函数的调用就是一个语法糖,真实的调用就是
 函数名.call()来调用的,而我们平时调用函数时候的this,其实就是call的第一个参数,如果不传就是
 undefined,或者null,而Windows会默认把windows传进去,例如:
 fn() 等价于 fn.call(null) 等价于 fn.call(Windows)
 如果通过一个对象.函数()来调用的话就是 obj.fn() 等价于 obj.fn.call(obj)
 如果把函数放到一个数组中,再通过array[0]()这样的方式来调用,则就是 array.0.call(array)所以里面
 的this就是array
 箭头函数里面没有this,箭头函数里面的this就是它定义的地方的this
 
 [this到底是什么？](https://zhuanlan.zhihu.com/p/23804247)
 
   2. 看调用
      [《this 的值到底是什么？一次说清楚》](https://zhuanlan.zhihu.com/p/23804247)

6. 必考：闭包/立即执行函数是什么？

   1. 闭包 https://zhuanlan.zhihu.com/p/22486908、
  闭包就是函数内部可以访问外部的变量,闭包通常被用来间接的访问一个变量,换句话说就是隐藏一个变量
  闭包不会造成内存的泄露,内存泄漏是指你用不到的变量还占据着内存,而闭包里面我们隐藏的变量就是我们用不到的变量,
  但是为什么有人说是容易造成内存泄漏呢?因为IE在我们使用闭包之后无法收回里面的内存空间,这是IE的问题,不是闭包的问题.
  如何解决内存泄露：将暴露全外部的闭包变量置为null
  适用场景：封装组件，for循环和定时器结合使用,for循环和dom事件结合.可以在性能优化的过程中,节流防抖函数的使用,导航栏获取下标的使用
  
  
   2. 立即执行函数 https://zhuanlan.zhihu.com/p/22465092
   立即执行函数就是什么一个匿名函数然后去立即调用
   function(){console.log}(),因为要兼容js语法,所以需要在最前面加上一些小东西,比如:~ ! +  - ; 
   也可以加上括号
   为什么要使用立即执行函数呢? 
   因为在ES6之前如果想创建一个局部作用域使局部作用域里面的变量不与外面的变量冲突,
   所以才发明了这个语法,而ES6中有了块级作用域就不需要使用立即执行函数了,但是块级作用域中的变量
   需要使用let 或者 const 声明

7. 必考：什么是 JSONP，什么是 CORS，什么是跨域？

   1. JSONP https://zhuanlan.zhihu.com/p/22600501
   说起JSONP就要说起同源策略,在当前的网页控制台输入window.origin就可以看到当前网页的源,如果两个网页的,协议,域名,端口号完全一致就说 这两个url同源,如果一个JS文件运行在源A里面,那么就只能获取源A    的数据,不能获取源B的数据,即不能跨域,跨域阻止的是数据访问,但是还是而已引用的,引用的时候network还是200
   2. CORS https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Access_control_CORS
    跨域就是不同源的网站可以相互访问对方服务器的数据,要实现跨域就要用到CORS和JSNP
    CORS就是需要在共享数据的时候提前声明,需要设置Access-Control-Allow-Origin的值,如果无法使用CROS
    或者是兼容IE的时候就需要使用JSONP,JSONP就是去执行一个JS文件,这个JS文件会执行一个回调,回调里面
    就有我们的数据,这个回调的名字是可以随机生成的,我们把这个随机生成的名字传给后台,后台会把这个
    回调返回给我们并执行,优点就是它可以兼容IE,和实现跨域,缺点就是它是一个script标签,所以不能发送
    post请求,读不到AJAX那个精准的状态
8. 常考：async/await 怎么用，如何捕获异常？
   async函数是一个返回promise对象的一个异步函数,一个async里面可以包含一个或多个await指令
   await后面跟的应该是一个返回promise的一个函数,如果不是promise则返回值本身,await会暂停
   当前函数的执行,等待promise处理完成,若 Promise 正常处理(fulfilled)，其回调的resolve函数参数
   作为 await 表达式的值,若 Promise 处理异常(rejected)，await 表达式会把 Promise 的异常原因抛出
   捕获异常的话就是等await后面的promise处理异常,然后将错误抛出.可以放在try , catch中捕获异常
   1. [阮一峰的书讲了](http://es6.ruanyifeng.com/?search=async&x=0&y=0#docs/async)
   2. [方方的视频课讲了](https://xiedaimala.com/courses/12a78a03-35f9-42ea-9b37-540540460f6e) 最后一节。

9. 常考：如何实现深拷贝？
  如果是普通的数组或者是普通的对象,就是数组里面是基本类型,对象里面是基本类型那就可以直接将拷贝
  的东西转换为字符串然后再转化回来就好了,常用方法为 JSON.parse(JSON.stringfiy(拷贝的东西))
  如果不是话就需要  递归去判断类型,然后检查环,接着忽略原型
   背代码，要点：

   1. 递归
   2. 判断类型
   3. 检查环（也叫循环引用）
   4. 需要忽略原型

10. 常考：如何用正则实现 trim()？

    背代码

    ```
    String.prototype.trim = function(){
        return this.replace(/^\s+|\s+$/g, '')
    }
    //或者 
    function trim(string){
        return string.replace(/^\s+|\s+$/g, '')
    }
    ```

11. 常考：不用 class 如何实现继承？用 class 又如何实现？

    1. 背代码，不用 class 这样实现

       ```js
        function Animal(color){
            this.color = color
        }
        Animal.prototype.move = function(){} // 动物可以动
        function Dog(color, name){
            Animal.call(this, color) // 或者 Animal.apply(this, arguments)
            this.name = name
        }
        // 下面三行实现 Dog.prototype.__proto__ = Animal.prototype
        function temp(){}
        temp.prototype = Animal.prototype
        Dog.prototype = new temp()
       
        Dog.prototype.constuctor = Dog // 这行看不懂就算了，面试官也不问
        Dog.prototype.say = function(){ console.log('汪')}
       
        var dog = new Dog('黄色','阿黄')
       ```

    2. 背代码，用 class 就简单了

       ```js
        class Animal{
            constructor(color){
                this.color = color
            }
            move(){}
        }
        class Dog extends Animal{
            constructor(color, name){
                super(color)
                this.name = name
            }
            say(){}
        }
       ```
    class的话直接通过extends关键字继承,在子类里面再调用super()


12. 常考：如何实现数组去重？

    1. 计数排序变形，背代码 （遍历数组）
    2. 使用 Set（面试已经禁止这种了，因为太简单）[...new Set(numbers)]
    3. 使用 WeakMap

13. 放弃：== 相关题目（反着答）
    不要背，记不住，太复杂且没有规律
    这种问题一般就是考使用==的时候会先做类型转换,然后再比较,规则非常难记,而我一般都是使用的===
    所以我会这样答
    我一般使用的是三个等于号的比较,因为我认为==的自动类型转换导致比较的结果不准确,所以我一般使用
     的都是三个等于号,如果需要类型转换我会自己进行类型转换

14. 送命题：手写一个 Promise
    提前写一遍，放在博客里，参考 https://juejin.im/post/5aafe3edf265da238f125c0a
15. 作用域问题：    

## DOM

1. 必考：事件委托

   1. 错误版（但是可能能过）

      ```js
       ul.addEventListener('click', function(e){
           if(e.target.tagName.toLowerCase() === 'li'){
               fn() // 执行某个函数
           }
       })
      ```

      bug 在于，如果用户点击的是 li 里面的 span，就没法触发 fn，这显然不对。

   2. 高级版

      ```js
       function delegate(element, eventType, selector, fn) {
           element.addEventListener(eventType, e => {
             let el = e.target
             while (!el.matches(selector)) {
               if (element === el) {
                 el = null
                 break
               }
               el = el.parentNode
             }
             el && fn.call(el, e, el)
           })
           return element
         }
      ```

      思路是点击 span 后，递归遍历 span 的祖先元素看其中有没有 ul 里面的 li。

2. 曾考：用 mouse 事件写一个可拖曳的 div
   参考代码：https://jsbin.com/munuzureya/edit?html,js,output
   注意点: 记下初始位置,获取鼠标当前位置:e.clientX xxx.style.left是字符串,初始值为空,监听事件的移动要在document上。
   ```
   var dragging = false
   var position = null

   xxx.addEventListener('mousedown',function(e){
     dragging = true
     position = [e.clientX, e.clientY]
   })

   document.addEventListener('mousemove', function(e){
     if(dragging === false){return}
     console.log('hi')
     const x = e.clientX
     const y = e.clientY
     const deltaX = x - position[0]
     const deltaY = y - position[1]
     const left = parseInt(xxx.style.left || 0)
     const top = parseInt(xxx.style.top || 0)
     xxx.style.left = left + deltaX + 'px'
     xxx.style.top = top + deltaY + 'px'
     position = [x, y]
   })
   document.addEventListener('mouseup', function(e){
     dragging = false
   })
   ```

   ## HTTP

3. 必考：HTTP 状态码知道哪些？分别什么意思？

   - 2xx 表示成功
   - 3xx 表示需要进一步操作
   - 4xx 表示浏览器方面出错
   - 5xx 表示服务器方面出错
   - 完整参考 http://www.runoob.com/http/http-status-codes.html
   ```
   100   //continue
   200   //请求成功
   201   // Created 资源已创建
   204   // 无内容 No Content
   301   //永久重定向
   302   //临时重定向
   403   //服务器拒绝请求
   404   //请求的资源无法找到
   408   //请求时间超时
   414   //请求过长
   500   //服务器内部错误
   502   //无响应  Bad Gateway
   505   //不支持请求的HTTP协议的版本
   ```

4. 大公司必考：HTTP 缓存有哪几种？
   http缓存就是通过复用以前获取的资源来提高网站和应用程序的性能,一般设置缓存是通过cache-control
   ,ETag,Expires,通过设置cache-control可以客户端可以在多久的时间内使用缓存的内容,而无需发送请求
   (Cache-Control: max-age=3600, must-revalidate),设置Etag给资源一个MD5标识符,下次请求的时候将
   这个ETag带上,如果这个ETag跟服务端的一致那就不用再次请求资源,返回304直接使用本地缓存,
   如果不一致就请求资源,然后200,Expires就是给返回的资源加上一个格林时间,如果超过这个时间则表示
   资源过期,需要重新的请求数据,但是这个不怎么准确,因为客户端的时间是可以自己更改的.

   - 需要详细的了解 ETag、CacheControl、Expires 的异同
   - 参考 https://imweb.io/topic/5795dcb6fb312541492eda8c
   - 参考mdn https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Caching
   - 答题要点：
     1. ETag 是通过对比浏览器和服务器资源的特征值（如MD5）来决定是否要发送文件内容，如果一样就只发送 304（not modified）
     2. Expires 是设置过期时间（绝对时间），但是如果用户的本地时间错乱了，可能会有问题
     3. CacheControl: max-age=3600 是设置过期时长（相对时间），跟本地时间无关。

5. 必考：GET 和 POST 的区别

   1. 错解，但是能过面试
      - GET在浏览器回退时是无害的，而POST会再次提交请求。
      - GET产生的URL地址可以被加入收藏栏，而POST不可以。
      - GET请求会被浏览器主动cache，而POST不会，除非手动设置。
      - GET请求只能进行url编码，而POST支持多种编码方式。
      - GET请求参数会被完整保留在浏览器历史记录里，而POST中的参数不会被保留。
      - GET请求在URL中传送的参数是有长度限制的，而POST么有。
      - 对参数的数据类型，GET只接受ASCII字符，而POST没有限制。
      - GET比POST更不安全，因为参数直接暴露在URL上，所以不能用来传递敏感信息。
      - GET参数通过URL传递，POST放在Request body中。
   2. 正解
      就一个区别：语义——GET 用于获取资源，POST 用于提交资源。
      错误答案：
      1.post安全,get不安全
      2.get url 参数有限制 , post没有限制
      3.get参数放在url里面,post放在消息体里面
      4.get只需要一个报文,post需要两个或两个以上
      5.get 幂等,post不幂等
      至于那些说两个安不安全的其实都不安全,还有那个参数限制,get为1024个字节,post为 5M | 10M |20M,还有参数都可以放到url里面,报文的话火狐浏览器post只有一个,幂不幂等就是废话
      参考 https://blog.fundebug.com/2019/02/22/compare-http-method-get-and-post/

6. Cookie V.S. LocalStorage V.S. SessionStorage V.S. Session

   - Cookie V.S. LocalStorage
     1. 主要区别是 Cookie 会被发送到服务器，而 LocalStorage 不会
     2. Cookie 一般最大 4k，LocalStorage 可以用 5Mb 甚至 10Mb（各浏览器不同）
   - LocalStorage V.S. SessionStorage
     1. LocalStorage 一般不会自动过期（除非用户手动清除），而 SessionStorage 在回话结束时过期（如关闭浏览器）
   - Cookie V.S. Session
     1. Cookie 存在浏览器的文件里，Session 存在服务器的文件里
     2. Session 是基于 Cookie 实现的，具体做法就是把 SessionID 存在 Cookie 里

## 框架 Vue

1. 必考：watch 和 computed 和 methods 区别是什么？

   1. 思路：先翻译单词，再阐述作用，最后强行找不同。
   2. 要点：
      1. computed 和 methods 相比，最大区别是 computed 有缓存：如果 computed 属性依赖的属性没有变化，那么 computed 属性就不会重新计算。methods 则是看到一次计算一次。
      2. watch 和 computed 相比，computed 是计算出一个属性（废话），而 watch 则可能是做别的事情（如上报数据）

2. 必考：Vue 有哪些生命周期钩子函数？分别有什么用？

   1. 钩子在[文档](https://cn.vuejs.org/v2/guide/instance.html#生命周期图示)全都有，看红色的字。
   ```
   beforeCreate    //在组件创造之前做一些事情
   created         //组件创造之后做一些事情
   beforeMount    //组件挂载之前做一些事情
   mounted        //组件挂载之后做一些事情
   beforeUpdate   //更新之前做一些事情
   updated       //更新之后做一些事情
   beforeDestroy //摧毁之前做一些事情
   destroy       //摧毁之后做一些事情
   ```
   2. 把名字翻译一遍就是满分
   3. 要特别说明哪个钩子里请求数据，[答案是 mounted](https://segmentfault.com/q/1010000010643393)

3. 必考：Vue 如何实现组件间通信？

   1. 父子组件：使用 v-on 通过事件通信
   2. 爷孙组件：使用两次 v-on 通过爷爷爸爸通信，爸爸儿子通信实现爷孙通信
   3. 任意组件：使用 eventBus = new Vue() 来通信，eventBus.$on 和 eventBus.$emit 是主要API
   4. 任意组件：使用 Vuex 通信

4. 必考：Vue 数据响应式怎么做到的？
    这个之前是Vue的双向绑定,现在变了,如果问的是双向绑定就回答v-model,如果问的是响应式的话就参考官方文档:
   1. 答案在文档《[深入响应式原理](https://cn.vuejs.org/v2/guide/reactivity.html)》
   2. 要点
      1. 使用 Object.defineProperty 把这些属性全部转为 getter/setter
      2. Vue 不能检测到对象属性的添加或删除，解决方法是手动调用 Vue.set 或者 this.$set
    当把一个JavaScript对象传入Vue实例作为data选项时，Vue将遍历这个对象中的属性，
    并使用Object.defineProperty,把这些属性全部转化为getter和setter，
    这些getter和setter用户是看不见的，但是在内部他们可以让Vue追踪和依赖，
    在属性被修改时会通知变更，当属性的setter被触发时会通知watcher，
    使属性的相关组件重新渲染。而由于JavaScript的限制导致Vue无法监听属性的添加和修改，
    所以最好把属性写到data对象上才可以将它转化为响应式的，对于已创建的Vue实例，
    不允许再添加根级别的响应式数据，但是可以使用Vue.set(object, propertyName, value). 
5. 必考：Vue.set 是做什么用的？
   见上一题

6. Vuex 你怎么用的？

   1. 背下文档第一句：Vuex 是一个专为 Vue.js 应用程序开发的状态管理模式
   2. 说出核心概念的名字和作用：State/Getter/Mutation/Action/Module
 看一下文档核心概念https://vuex.vuejs.org/zh/
7. VueRouter 你怎么用的？

   1. 背下文档第一句：Vue Router 是 Vue.js 官方的路由管理器。

   2. 说出核心概念的名字和作用：History 模式/导航守卫/路由懒加载

   3. 说出常用 API：router-link/router-view/this.$router.push/this.$router.replace/this.$route.params

      ```js
       this.$router.push('/user-admin')
       this.$route.params
      ```
 文档https://router.vuejs.org/zh
8. 路由守卫是什么？
   看官方文档的例子，背里面的关键的话
   https://router.vuejs.org/zh/guide/advanced/navigation-guards.html#%E5%85%A8%E5%B1%80%E5%89%8D%E7%BD%AE%E5%AE%88%E5%8D%AB

## 框架 React

1. 必考：受控组件 V.S. 非受控组件

   ```jsx
    <FInput value={x} onChange={fn}/> 受控组件
    <FInput defaultValue={x} ref={input}/> 非受控组件
   ```

   区别受控组件的状态由开发者维护，非受控组件的状态由组件自身维护（不受开发者控制）
   [非受控组件](https://zh-hans.reactjs.org/docs/uncontrolled-components.html)
   [受控组件](https://zh-hans.reactjs.org/docs/forms.html)

2. 必考：React 有哪些生命周期函数？分别有什么用？（Ajax 请求放在哪个阶段？）

   答题思路跟 Vue 的一样 参考blog https://juejin.cn/post/6844903655372488712

   1. 钩子在[文档](https://react.docschina.org/docs/state-and-lifecycle.html)里，蓝色框框里面的都是生命周期钩子
   2. 把名字翻译一遍就是满分
   3. 要特别说明哪个钩子里请求数据，[答案是 componentDidMount](https://segmentfault.com/q/1010000008133309)

3. 必考：React 如何实现组件间通信？

   1. 父子靠 props 传函数
   2. 爷孙可以穿两次 props
   3. 任意组件用 Redux（也可以自己写一个 eventBus）

4. 必考：shouldComponentUpdate 有什么用？

   1. 要点：用于在没有必要更新 UI 的时候返回 false，以提高渲染性能
   2. 参考：http://taobaofed.org/blog/2016/08/12/optimized-react-components/

5. 必考：虚拟 DOM 是什么？

   1. 要点：虚拟 DOM 就是用来模拟 DOM 的一个对象，这个对象拥有一些重要属性，并且更新 UI 主要就是通过对比（DIFF）旧的虚拟 DOM 树 和新的虚拟 DOM 树的区别完成的。
   2. 参考：http://www.alloyteam.com/2015/10/react-virtual-analysis-of-the-dom/

6. 必考：什么是高阶组件？

   1. 要点：[文档原话](https://react.docschina.org/docs/higher-order-components.html)——高阶组件就是一个函数，且该函数接受一个组件作为参数，并返回一个新的组件。
   2. 举例：React-Redux 里 [connect 就是一个高阶组件](https://react-redux.js.org/api/connect)，比如 `connect(mapState)(MyComponent)` 接受组件 MyComponent，返回一个具有状态的新 MyComponent 组件。

7. React diff 的原理是什么？
   看你记忆力了：https://imweb.io/topic/579e33d693d9938132cc8d94

8. 必考 Redux 是什么？

   1. 背下文档第一句：Redux 是 JavaScript 状态容器，提供可预测化的状态管理。重点是『状态管理』。
   2. 说出核心概念的名字和作用：Action/Reducer/Store/单向数据流
   3. 说出常用 API：store.dispatch(action)/store.getState()

9. connect 的原理是什么？
   react-redux 库提供的一个 API，connect 的作用是让你把组件和store连接起来，产生一个新的组件（connect 是高阶组件）
   参考：https://segmentfault.com/a/1190000017064759
   加一个自定义Hook
   下面是一个自封装的Hook,是表示第二次更新的时候才触发的事件,因为在函数组件中可以使用Hook来完全代替class组件,其中的生命周期钩子可以使用useEffect来代替,useEffecct(()=>{},[dep])其中第二个参数的传递可以使useEffect Hook来代替不同的生命周期,

   1.不传第二个参数的时候表示每次更新都会执行这个Hook componentDidMount
   2.传递一个空数组表示第一次渲染执行 componentDidUpdate
   3.传递一个[n]表示n变了的时候执行
   4.如果useEffect中返回一个函数返回一个函数表示组件消失前执行 componentWillUnMount
   ```
     const useUpdate = (fn,dep)=>{
     const [count,setCount] = useState(0)
     useEffect(()=>{
       setCount(()=>count+1)  
     },[dep]) 
     useEffect(()=>{
        if(count >1 ){fn()}
      },[count,fn])
   }
   const [n,setN] = useState(0)
   useUpdate(()=>{console.log('第二次变化才执行的Hook')},n)
   ```

## TypeScript

1. never 类型是什么？
   不应该出现的类型 尤雨溪的答案：https://www.zhihu.com/question/354601204/answer/888551021
2. TypeScript 比起 JavaScript 有什么优点？
   提供了类型约束，因此更可控、更容易重构、更适合大型项目、更容易维护

# Webpack

1. 必考：有哪些常见 loader 和 plugin，你用过哪些？
2. 英语题：loader 和 plugin 的区别是什么？
3. 必考：如何按需加载代码？
4. 必考：如何提高构建速度？
5. 转义出的文件过大怎么办？

上面五题请看这个不错的参考：https://zhuanlan.zhihu.com/p/44438844

# 安全

1. 必考：什么是 XSS？如何预防？
   比较复杂，看我的文章 https://zhuanlan.zhihu.com/p/22500730
2. 必考：什么是 CSRF？如何预防？
   比较复杂，看若愚的文章 https://zhuanlan.zhihu.com/p/22521378

## 开放题目

1. 必考：你遇到最难的问题是怎样的？
   要点：一波三折。参考 https://www.zhihu.com/question/35323603
2. 你在团队的突出贡献是什么？
   把小事说大。
3. 最近在关注什么新技术
   书、博客、推特、知乎，不要说 CSDN、百度。
4. 有没有看什么源码，看了后有什么记忆深刻的地方，有什么收获
   看过源码说源码，推荐看 underscore.js 的源码
   没看过源码就说同事的代码，代码烂就说哪里烂，代码好就说哪里好
   收获：命名规范、设计模式

## 刁钻题目

1. 代码

   ```js
    [1,2,3].map(parseInt)
   ```

   答案

   ```
    1
    NaN
    NaN
   ```

2. 代码

   ```js
    var a = {name: 'a'}
    a.x = a = {}
    问 a.x 是多少？
   ```

   答案

   ```
    undefined
   ```

3. ```
   (a ==1 && a== 2 && a==3)
   ```

    

   可能为 true 吗？

   1. 利用 == 会调用 valueOf() 的特性

      ```js
       var a = {
        value: 1,
        valueOf(){
         return this.value++
        }
       }
       a ==1 && a== 2 && a==3 // true
      ```

   2. 利用 a 会读取 window.a 的特性

      ```js
       var value = 1; 
       Object.defineProperty(window, 'a', {
           get(){
               return value++;
           }
       })
       a ==1 && a== 2 && a==3 // true
       // 或者 
       a ===1 && a=== 2 && a===3 // true
      ```

## 超纲题

1. JS 垃圾回收机制

   1. 看图讲解

       

      https://javascript.info/garbage-collection

      1. 什么是垃圾
      2. 如何捡垃圾（遍历和计数，只是[不同的算法](https://www.jianshu.com/p/a8a04fd00c3c)而已）
      3. 前端又有其特殊性（JS进程和DOM进程）

   2. 更深入一些的讲解 http://newhtml.net/v8-garbage-collection/

2. Eventloop 说一下

   ```js
    setTimeout(function () {
        console.log(4);
    }, 0);
    new Promise(function (resolve) {
        console.log(1);
        resolve();
        console.log(2);
    }).then(function () {
        console.log(5);
    });
   
    console.log(3);
   ```

   ```js
    1
    2
    3
    5
    4
   ```

   1. 肤浅理解：『一会儿』和『尽快』异步任务

   2. 详细理解：Eventloop 是个啥？

   3. 浏览器有 Eventloop 吗？

   4. 每个 API 对应哪个任务队列？

      1. setTimeout
      2. setImmediate（浏览器没有）
      3. process.nextTick（浏览器没有）
      4. MutationObserver（Node 没有）
      5. promise.then
      6. await

   5. 这种题目尽量说思路，因为你不可能通过眼睛看出结果（必须画图）

      ```js
       async function async1() {
           console.log(1);
           await async2();
           console.log(2);
       }
       async function async2() {
           console.log(3)
       }
      
       async1();
      
       new Promise(function (resolve) {
           console.log(4);
           resolve();
       }).then(function () {
           console.log(5);
       });
      ```

      ```
       1
       3
       4
       2
       5
      ```

      注意：这一题的答案不唯一，在 Node.js 和 Chrome 的结果不一样，甚至在 Chrome 上也是时而这个答案，时而那个答案。所以还是说思路最重要。
     
     
     
     参考 https://juejin.cn/post/6844903582538399752
     添加一个JS中的事件运行机制：

     首先JS的运行是单线程的，但是我们平时运行的时候肯定会有异步的的操作，所以JS的运行是分同步任务和异步任务的，所有的同步任务是运行在主线程的，形成一个执行栈，而异步任务是运行在任务队列中的，只要异步任务有了运行结果就会在任务队列中放置一个事件，一旦执行栈中的同步代码执行完毕，就会读取任务队列，将事件停止等待，进入执行栈开始执行。

     如果问到了node.js中的eventlop,就从 timer poll check 这三个中说 , 首先eventlop打开后会在poll阶段，然后setTimeout会放在timer阶段，setimediate会放在check阶段，nexttick会放在当时的那个阶段执行的最后执行。

## 个性化题目

- PWA
- echarts.js / d3.js
- three.js
- flutter
- SSR

做个 hello world 基本就能应付面试了，如果怕应付不了，就再做个复杂点的。
