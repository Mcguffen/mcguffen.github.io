---
title: html入门笔记
---

HTML 的全名是“超文本标记语言”（HyperText Markup Language），上个世纪90年代由欧洲核子研究中心的物理学家蒂姆·伯纳斯-李（Tim Berners-Lee）发明
## HTML起手式
- 在vscode起手输入！或者html:5，自动补全html模板。
``` html
 <!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
- ``` html
- <html lang="en">
- ```
- en可以改为zh-CN（zh：中文，CN：中国，因为还有其他地区的中文）
- <meta name="viewport" content="width=device-width, initial-scale=1.0">
- 防止页面缩放.
- <meta http-equiv="X-UA-Compatible" content="ie=edge">
默认访问IE浏览器内核转为edge版本
  
## HTML标签
- 表示文章/书的层级
  - 标题h1~h6
  - 章节section
  - 文章article
  - 段落p
  - 头部header
  - 脚部footer
  - 主要内容main
  - 旁支内容aside
  - 划分div
``` html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <title>文章标题</title>
</head>

<body>
  <header>导航栏</header>
  <div>
    <main>
      <h1>文章标题</h1>
      <section>
        <h2>第一章</h2>
        <p>这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话</p>
        <section>
          <h2>1.1 标题</h2>
          <p>一段话111</p>
        </section>
        <section>
          <h2>1.2 标题</h2>
          <p>一段话222</p>
        </section>
      </section>
    </main>
    <aside>
      参考文献：1， 2，3
    </aside>
  </div>
  <footer>&copy;bens版权所有</footer>
</body>

</html>
```

## 全局属性
所有标签都可以有的属性classcontenteditable所选的范围可编辑将style放到body上然后通过加入style{display:block; }可以将style显示出来，然后配合contenteditable来实现样式可编辑（只能编辑已有的样式，新建样式不起作用）。
``` html

<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>文章标题</title>
</head>

<body>
    <style contenteditable>
        style {
            display: block;
            border: 1px solid green
        }

        /* 这样写样式不方便，修改的话需要新加一个样式*/
        /*  [class="middle bordered"]{       background:black;       color:white;       border:5px solid red     } */
        .middle {
            background: black;
            color: white;
        }

        .bordered {
            border: 5px solid red
        }
    </style>
    <header>导航栏</header>
    <div class="middle bordered" contenteditable>
        <main>
            <h1>文章标题</h1>
            <section>
                <h2>第一章</h2>
                <p>这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话</p>
                <section>
                    <h2>1.1 标题</h2>
                    <p>一段话111</p>
                </section>
                <section>
                    <h2>1.2 标题</h2>
                    <p>一段话222</p>
                </section>
            </section>
        </main>
        <aside> 参考文献：1， 2，3 </aside>
    </div>
    <footer>&copy;版权所有</footer>
</body>

</html>
```
- hidden可以通过display:block来显示出来
- id不到万不得已， 千万不要用id，无论是CSS还是JS。在html中，因为id不报错id名与windos.下的关键字同名时。用这种形式来写JSxxx.style.border = "5px solid green";是不报错的。如果真的想用同名用下面这种方式：document.getElementById('parent').style.border = "10px solid yellow";
- style这是HTML的属性，不是CSS的样式
- tabindex设置该属性后，按tab键可以进行下一个带有该属性的地方
- title

``` html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>文章标题</title>
</head>
<style contenteditable>
    /* 这样写样式不方便，修改的话需要新加一个样式*/
    /*  [class="middle bordered"]{
      background:black;
      color:white;
      border:5px solid red
    } */
    .middle {
        background: black;
        color: white;
    }

    .bordered {
        border: 5px solid red
    }

    header {
        display: block;
    }

    #xxx {
        border: 5px solid orange;
        /* 不换行 */
        white-space: nowrap;
        /* 多余一样的省略 */
        overflow: hidden;
        /* 省略部分的处理方式 */
        text-overflow: ellipsis;
    }
</style>

<body>

    <header hidden>导航栏</header>
    <div class="middle bordered" contenteditable>
        <main>
            <h1>文章标题</h1>
            <section>
                <h2>第一章</h2>
                <p>这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话这是一段话</p>
                <section>
                    <h2>1.1 标题</h2>
                    <p>一段话111</p>
                </section>
                <section>
                    <h2>1.2 标题</h2>
                    <p>一段话222</p>
                </section>
            </section>
        </main>
        <aside>
            参考文献：1， 2，3
        </aside>
    </div>
    <footer id="xxx" title="&copy;版权所有">
        &copy;版权所有</footer>
</body>

</html>
```

## 内容标签🏷️
- ol + li（ordered list + list item）
- ul + li（unordered list + list item）
- dl + dt +dd（description list + term +data）
- pre（preview的缩写）保留空格、回车和tab
- hr
- br（break的缩写）
- a（anchar的缩写）
- em（emphasis的缩写）语气上的强调
- strong内容本身的重要性
- code
- q（quote缩写）
- blockquote

## table表格标签🏷️
- table
- thead
- tbody
- tfoot
- tr
- td
- th
