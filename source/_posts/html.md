---
title: 个人域名,简历模板，HTML,部署到GitHub Pages。
---
##
### HTML
	•	HTML
HTML 的全称如果你还没有背下来，就背一下吧。
	•	HTML 的版本（W3C 组织制定规范）
	•	HTML 4.01
	•	XHTML
	•	HTML 5
	•	HTML 5.1
	•	规范文档（Specifications）
	•	由 W3C 写文档（李爵士）
	•	W3C 根据浏览器的实际情况总结文档，并不是凭空想象
	•	DOCTYPE
	•	用来选择文档类型
	•	除了 HTML 5 的 DOCTYPE，其他的都 TM 很难记：https://www.w3.org/QA/2002/04/valid-dtd-list.html
	•	如果你没写 DOCTYPE，那你就惨了
	•	html / head / body
	•	省略标签
	•	常见标签：a、form、input、button、h1、p、ul、ol、small、strong、div、span、kbd、video、audio、svg
	•	基本上，你知道标签对应单词的意思，就知道这个标签怎么用了（语义化）
	•	出了 div 和 span，其他标签都有默认样式
	•	MDN 上有所有标签的文档
	•	如何查看 MDN 文档
	•	Google：关键词 + MDN
	•	切换成中文
HTML 代码如下：
``` html
<!DOCTYPE html>
<html>
  <head>
    <title>xx的个人简历</title>
    <style>
    </style>
  </head>
  <body>
    <div class="topNavBar">
      <img src="#" alt="logo"/>
      <nav>
        <ul>
          <li><a href="#">ABOUT</a></li>
          <li><a href="#">SKILLS</a></li>
          <li><a href="#">EXPERIENCE</a></li>
          <li><a href="#">PRICING</a></li>
          <li><a href="#">BLOG</a></li>
          <li><a href="#">CALENDAR</a></li>
          <li><a href="#">CONTACT</a></li>
          <li><a href="#">OTHER</a></li>
          <li><a href="#">ALL DEMOS</a></li>
        </ul>
      </nav>
    </div>
    <div class="banner" style="background-image: url(#)"></div>
    <main>
      <div class="card">
        <div class="picture">
          <img src="" alt="头像">
        </div>
        <div class="text">
          <div class="profile">
            <span class="welcome">Hello</span>
            <h1>xx</h1>
            <p>前端开发工程师</p>
            <hr>
            <dl>
              <dt>年龄</dt>
              <dd>18</dd>
              <dt>所在城市</dt>
              <dd>北京</dd>
              <dt>邮箱</dt>
              <dd>fa@foxmail.com</dd>
              <dt>手机</dt>
              <dd>138xxxxxx</dd>
            </dl>
          </div>
          <footer class="media">
            <a href="#"><img src="#" alt="..."></a>
            <a href="#"><img src="#" alt="..."></a>
            <a href="#"><img src="#" alt="..."></a>
            <a href="#"><img src="#" alt="..."></a>
            <a href="#"><img src="#" alt="..."></a>
            <a href="#"><img src="#" alt="..."></a>
            <a href="#"><img src="#" alt="..."></a>
          </footer>
        </div>
      </div>

      <a class="button" href="#">下载 PDF 简历</a>

      <p>
        xx， 资深前端工程师<br>
        技能：前端开发，Rails 开发，Node.js 开发
      </p>

    </main>
  </body>
</html>
```
### 个人域名
	•	买个域名
	•	找个简历模板
	•	开始写 HTML（以后再写 CSS 和 JS）
	•	发布到互联网！🚀
买域名你有两个选择
	•	向国内服务商购买，不过你需要备案（备案就是把你的照片、姓名、住址和手机号告诉管理机构）
	•	向国外服务商购买，不需要备案，不过需要你懂一点英文
我们当然毫不犹豫地选择后者。XD
	•	进入 namesilo.com 搜索一个你喜欢的域名，比如我搜索的是 yang，当然是越短越好，好记。然后你就会知道哪些域名是可以买的 
	•	其中最低的价格是 .xyz 域名，价格只要 1.89 美元，折合人民币 12 块五毛（每年），是不是很便宜。不要急，还有更便宜的，后面会教你搜索优惠码。现在我们先确定域名，如果你对 .xyz 不满意，可以选 fangyinghang.info，.info 域名比 .xyz 稍微好看一点，当然你也可以选择 fangyinghang.me、fangyinghang.pro 等。
	•	选中你想要的域名，点击 REGISTER CHECKED DOMAINS 绿色按钮。
	•	别急着结账，有一个地方可以输入优惠码（如图）  去谷歌或者百度搜索「namesilo 优惠码」，填到里面，就可以优惠一美元！但是你要注意，一个用户只能使用一次优惠码，下次你再购买域名就没有优惠啦。
	•	用支付宝结账（一定要先输入邮箱，再选中支付宝，最后点击 go） 
支付成功后域名就是你的了，你可以给这个域名设置 A 记录和 CNAME，具体操作见视频，就是点几下鼠标的事情。
域名买了先放着，我们后面会用到。


### 简历模版
简历主要有两个重点
	•	外观
	•	内容
	•	外观
一般大家都会简历的外观很重视，我这里给大家介绍几个网站
	•	在 dribbble.com 搜索 cv 或者 resume
	•	在五百丁 直接花钱购买 Word 模板
如果还找不到好看的，可以去在 Google 搜索「frontend resume template」或者「frontend cv template」碰碰运气，找找灵感。
这里忠告各位相当程序员的同学：如果你没有设计细胞，就不要自己设计自己的简历，会丑死人的。
我在 dribbble 和 Google 搜到了几个不错的：
所以我最终还是选择了这个简历：
http://rscardwp.px-lab.com/
这个简历的优点
	•	是在线版，方便我们查看它的代
	•	有动效，赏心悦目
	•	界面很丰富，我们可以择其善者而从之
为了方便后期我们使用「逼近法」实现页面，请前往 https://www.getpaint.net/ 下载 paint.net 图片编辑软件，这个软件比 Photoshop 小多了，如果你有 Photoshop 就不用下载了。
外观确定之后，我们就要介绍一个我们学习的指导思想，那就是
需要用什么就学习什么
很多人想学会 HTML、CSS、JS 再做网页，最后却发现看完书之后什么页面都写不出来！这是错误的学习方法，先用再学才是选编程的不二法门！
	•	内容
我们简历里写什么内容呢？必须包含的有以下几部分：
	•	个人信息：姓名、性别、年龄、学校、所在城市、目标职位（千万不要写目标薪资）
	•	教育经历：不管你的学校好或者不好，都写上吧，因为面试官肯定会问的，写上可以避免浪费时间
	•	工作经历：如果有相关经验就写，如果没有相关经验就不写，或者一笔带过
	•	项目经验：这是我们的重点。我们就是要用项目来证明我们，所以我们至少要在毕业前准备 8 个项目，然后择优选择 4 到 6 个放在简历里。
可选部分有：
	•	开源代码：你的 GitHub 如果每天都有 commit 记录，可以加分不少
	•	博客链接：如果面试官看到你半年写了 20 篇博客，基本就会要你了
	•	外文翻译：如果你能翻译一些英文技术文章，也放在简历里吧
	•	他人评价：老师的评语、同学的夸奖等（截图）
	•	自拍：只要长得不丑，就一定要放头像，给人以亲切感。有头像的简历会比没有头像的简历更醒目。
	•	对公司业务的分析：表示你对这个公司很关注
不建议写到简历
	•	自我评价：没什么卵用
	•	对公司的喜爱：没什么卵用
	•	段子：没什么卵用
好了，接下来我们就开始学习 HTML 吧，因为一个在线简历显然会用到以下技术
	•	HTML
	•	CSS
	•	JS
	•	SVG
	•	AJAX


### 部署到Github Pages
步骤
	•	前提是你已经在 GitHub 上拥有一个仓库，这个仓库的根目录要有一个 index.html 文件。你可以把仓库取名为 resume 或者 cv，因为这是你的简历。
	•	进入仓库的 Settings 
	•	往下滚，滚到 GitHub Pages 
	•	在下拉列表中选到 master branch，然后点击 Save，就会得到一个预览地址。
	•	复制这个地址，粘贴到地址栏，不要打回车。
	•	不要打回车。
	•	不要打回车。
	•	不要打回车。
	•	在地址后面输入 index.html，就可以预览 index.html 了。
	•	有人会发现即使不输入 index.html 也能访问 index.html，这是因为默认会访问 index.html，如果你的根目录还有另外一个 HTML 文件，比如 xxx.html，那你就必须添加 xxx.html 才能访问它了，所以我上面教的是一般方法，而不输入 index.html 就能访问 index.html 是一个特例。
注意这个方法只能用来预览 HTML，不能用来预览 Markdown、CSS、JS 等文件。
这是 GitHub 免费提供给我们的 HTTP 服务，非常好用。我们的 hexo 博客就是使用这种方式进行预览的。
不过 GitHub Pages 并不提供编程功能，也就是说你不能把上节课的 server.js 上传到 GitHub，指望能用 Node.js 来接受请求和发出响应，GitHub 没有提供这种功能。


