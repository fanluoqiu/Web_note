---
html:
  embed_local_images: true
  embed_svg: true
  offline: false

print_background: true

export_on_save:
  html: true

toc: 
  depth_from: 1
  depth_to: 4
  ordered: true
---

# Web学习笔记
<p id=head>:)</p>

## 相关网站

- [MDN](https://developer.mozilla.org/zh-CN/docs/Learn/Getting_started_with_the_web)
- [学习进度](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Other_embedding_technologies)
- [HTML语法检查](https://validator.w3.org/)
## HTML

### 前言
HTML是一种由不同元素组成的标记语言，应用于文本，赋予文本不同的含义（它是段落吗？它是项目列表吗？它是表格吗？），将文档结构化为逻辑块（文档是否有头部？有三列内容？有一个导航菜单？）或嵌入非文本文件（图片、音频）。元素由开始标签、内容、结束标签三部分组成。

<center>
    <img src="Images/grumpy-cat-small.png" 
         width=700>
</center>


### 入门前知识
#### 元素类型
##### 块级元素
块级元素在页面中以块的形式展现。一个块级元素出现在它前面的内容之后的新行上。任何跟在块级元素后面的内容也会出现在新的行上。块级元素通常是页面上的结构元素。例如，一个块级元素可能代表标题、段落、列表、导航菜单或页脚。一个块级元素不会嵌套在一个内联元素里面，但它可能嵌套在另一个块级元素里面。

##### 内联元素
内联元素通常出现在块级元素中并环绕文档内容的一小部分，而不是一整个段落或者一组内容。内联元素不会导致文本换行。它通常与文本一起使用，例如，`<a>` 元素创建一个超链接，`<em>` 和 `<strong>` 等元素创建强调。


##### 空元素
一些元素只有一个标签，通常用来在此元素所在位置插入/嵌入一些东西。这些元素被称为空元素。（如`<img>`）

*例：*
```html
<p>文本一</p><p>文本二</p><p>文本三</p>

<b>文本四</b>
<b>文本五</b>
<b>文本六</b>
```
*输出：*
<center>
    <img src="Images/image.png">
</center>

>在这篇文章中提到的“块”和“内联”，不应该与 CSS 盒子的类型中的同名术语相混淆。尽管它们默认是相关的，但改变 CSS 显示类型并不会改变元素的分类，也不会影响它可以包含和被包含于哪些元素。防止这种混淆也是 HTML5 摒弃这些术语的原因之一。

#### 元素属性
属性包含元素的额外信息，这些信息不会出现在实际的内容中。在上述例子中，这个 class 属性是一个识别名称，以后为元素设置样式信息时更加方便。

<center>
    <img src="Images/image-1.png" 
         alt="元素属性" width=700/>
  
</center>
<br>

属性名称必须包含：

- 一个空格，它在属性和元素名称之间。如果一个元素具有多个属性，则每个属性之间必须由空格分隔。
- 属性名称，后面跟着一个等于号。
- 一个属性值，由一对引号（""）引起来。



#### HTML文档结构
```html
<!doctype html>   
<html lang="zh-CN">
  <head>
    <meta charset="utf-8" />
    <title>我的测试站点</title>
  </head>
  <body>
    <p>这是我的页面</p>
  </body>
</html>

```
`<!DOCTYPE html>`
声明文档类型，文档类型声明类似于链接，规定了 HTML 页面必须遵从的良好规则，能自动检测错误和其他有用的东西。需要包含它才能使其他东西正常工作。`<!DOCTYPE html>` 是最短的有效文档声明。

`<html>`
这个元素包裹了页面中所有的内容，有时被称为根元素。

`<head>`
这个元素是一个容器，它包含了所有你想包含在 HTML 页面中但不在 HTML 页面中显示的内容。这些内容包括你想在搜索结果中出现的关键字和页面描述、CSS 样式、字符集声明等等。

`<meta>`
这个元素代表了不能由其他 HTML 元相关元素表示的元数据，比如 `<base>`、`<link>`、`<script>`、`<style>` 或 `<title>`。`charset` 属性将文档的字符集设置为 UTF-8，其中包括绝大多数人类书面语言的大多数字符。有了这个设置，页面现在可以处理它可能包含的任何文本内容。

`<title>`
元素。这设置了页面的标题，也就是出现在该页面加载的浏览器标签中的内容。当页面被加入书签时，页面标题也被用来描述该页面。

`<body>`
元素。包含了你访问页面时所有显示在页面上的内容，包含文本、图片、视频、游戏、可播放音频轨道等等。


### 文本处理基础

#### 标题和段落
在HTML中，一共有六种标题元素标签——h1、h2、h3、h4、h5 和 h6。每个元素代表文档中不同级别的内容：`<h1>` 表示主标题，`<h2>` 表示二级子标题，`<h3>` 表示三级子标题，依此类推。每个段落是通过 `<p>` 元素标签进行定义的。

注意：
- 最好只对每个页面使用一次 `<h1>`——这是顶级标题，所有其他标题位于层次结构中的下方。
- 请确保在层次结构中以正确的顺序使用标题。不要使用 `<h3>` 来表示副标题，后面再跟 `<h2>` 来表示二级副标题——这是没有意义的，会导致奇怪的结果。
- 在现有的六个标题层次中，除非觉得有必要，否则应该争取每页使用不超过三个。

#### 列表

##### 无序列表
无序列表用于标记列表项目顺序无关紧要的列表
*例：*
```html
<ul>
  <li>时间</li>
  <li>地点</li>
  <li>人物</li>z
</ul> 
```

*输出：*
<ul>
  <li>时间</li>
  <li>地点</li>
  <li>人物</li>
</ul> 

##### 有序列表
有序列表用于标记列表项目顺序重要的列表
*例：*
```html
<ol>
  <li>直行100米</li>
  <li>右转</li>
  <li>直行20米</li>
</ol> 
```

*输出：*
<ol>
  <li>直行100米</li>
  <li>右转</li>
  <li>直行20米</li>
</ol> 

##### 描述列表*
描述列表常用于一个或一组专业名词、答案的解释。描述列表使用与其他列表类型不同的闭合标签——`<dl>`；此外，每一项都用`<dt>`（description term）元素闭合。每个描述都用`<dd>`（description definition）元素闭合。
*例：*
```html
<dl>

<dt>培根</dt>
<dd>整个世界的粘合剂。</dd>
<dt>鸡蛋</dt>
<dd>一块蛋糕的粘合剂。</dd>
<dt>咖啡<dt>
<dd>一种浅棕色的饮料。</dd>
<dd>可以在清晨带来活力。</dd>

</dl>
``` 
*输出：*
<dl>
<dt>培根</dt>
<dd>整个世界的粘合剂。</dd>
<dt>鸡蛋</dt>
<dd>一块蛋糕的粘合剂。</dd>
<dt>咖啡<dt>
<dd>一种浅棕色的饮料。</dd>
<dd>可以在清晨带来活力。</dd>
</dl>

#### 重点强调

##### 强调

`<em>`（emphasis）
浏览器默认样式为斜体，并可以被屏幕阅读器识别，以不同的语调发出。

##### 强烈的重要性

`<strong>`（strong importance）
浏览器默认样式为粗体，并可以被屏幕阅读器识别，以不同的语调发出。

##### 斜体、粗体、下划线
`<i>`
被用来传达传统上用斜体表达的意义：外国文字，分类名称，技术术语，一种思想...
`<b>`被用来传达传统上用粗体表达的意义：关键字，产品名称，引导句...

`<u>`被用来传达传统上用下划线表达的意义：专有名词，拼写错误...

### 文档与网站架构

#### 文档的基本组成部分
网页的外观一般由下面的版块组成：

<dl>
<dt>页眉</dt>
<dd>通常横跨于整个页面顶部有一个大标题 和/或 一个标志。这是网站的主要一般信息，通常存在于所有网页。</dd>

<dt>导航栏</dt>
<dd>指向网站各个主要区段的超链接。通常用菜单按钮、链接或标签页表示。类似于标题栏，导航栏通常应在所有网页之间保持一致，否则会让用户感到疑惑，甚至无所适从。许多 web 设计人员认为导航栏是标题栏的一部分，而不是独立的组件，但这并非绝对；还有人认为，两者独立可以提供更好的 无障碍访问特性，因为屏幕阅读器可以更清晰地分辨二者。</dd>

<dt>主内容</dt>
<dd>中心的大部分区域是当前网页大多数的独有内容，例如视频、文章、地图、新闻等。这些内容是网站的一部分，且会因页面而异。</dd>

<dt>侧边栏</dt>
<dd>一些外围信息、链接、引用、广告等。通常与主内容相关（例如一个新闻页面上，侧边栏可能包含作者信息或相关文章链接），还可能存在其他的重复元素，如辅助导航系统。</dt>

<dt>页脚</dt>
<dd>横跨页面底部的狭长区域。和标题一样，页脚是放置公共信息（比如版权声明或联系方式）的，一般使用较小字体，且通常为次要内容。还可以通过提供快速访问链接来进行<a href="https://developer.mozilla.org/zh-CN/docs/Glossary/SEO">SEO</a>。</dd>
</dl>

为了实现语义化标记，HTML 提供了明确这些区段的专用标签，例如：

- `<header>`：页眉。
- `<nav>`：导航栏。
- `<main>`：主内容。主内容中还可以有各种子内容区段，可用`<article>`、`<section>` 和 `<div>` 等元素表示。
- `<aside>`：侧边栏，经常嵌套在 `<main>` 中。
- `<footer>`：页脚。


### 常用标签



#### \<a>：锚元素

常用属性如下：
`href`
声明需要跳转的目标位置。
`title`
跳转提示（鼠标放置在跳转文本上方时触发）
`target`
指定打开方式。如target="_blank"，表明在新标签页打开。

>统一资源定位符（URL）与路径（path）
统一资源定位符（Uniform Resource Locator，URL）是一个定义了在网络上的位置的一个文本字符串。例如，Mozilla 的简体中文主页位于 https://www.mozilla.org/zh-CN/。

##### 链接到HTML网页
*例一：*
```html
<!--文本链接到bing-->
<a href="https://www.bing.com" title="跳转到Bing" target="_blank">bing</a> 
```
*输出：*
<a href="https://www.bing.com" title="跳转到Bing" target="_blank"><b>bing</b></a>


*例二：*
```html
<!--用图片链接到bing-->
<a href="https://www.bing.com" title="跳转到Bing" target="_blank">
    <img src="Images/bing-logo.png">
</a> 
```
*输出：*
<a href="https://www.bing.com" title="跳转到Bing" target="_blank">
    <center>
        <img src="Images/bing-logo.png" width=300/>
    </center> 
</a> 

##### 跳转到HTML网页的某个位置
如果需要跳转到当前网页的某个位置，需要给要链接到的元素分配一个 id 属性
```html
<a id=head>:)</a>  <!--将代码放置于需要被跳转的位置-->
```
再对使用`#`+`锚点名称`使用锚点
```html
<p><a href="#head">跳转到标题</a></p> <!--将代码放置于需要跳转的位置-->
```
*输出：*
<p><a href="#head">跳转到标题</a></p>

如果要跳转到其他网页的某个位置，需要在跳转路径中加入`被跳转的网页路径`+`#`+`锚点名称`

*例：*
```html
<!--作业1.html-->
<!doctype html> 
<html lang="zh-CN">
    <head>
        <meta charset="utf-8" />
        <title>我的测试站点</title>
    </head>
    <body>
        <h1>作业1</h1>
        <P>这是我<b>第一次</b>作业</P>
        <p id="anc_work">我是在学了<a href="https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Getting_started" title="点击跳转到MDN" target="_blank">web 入门</a>后开始这个作业</p>
    </body>
</html>
```
在跳转位置使用锚点

```html
  <p><a href="coursework/作业1.html#anc_work">跳转到作业1</a></p>
```


<p><a href="coursework/作业1.html#anc_work" target="_blank">跳转到作业1</a></p>

<a id="audio"></a>
#### \<audio>
*相关标签* 
<p><a href="#video">&ltvideo&gt</a></p>

---



#### \<div>:无语义元素
对于一些要组织的项目或要包装的内容，现有的语义元素均不能很好对应。用于作为一个单独的实体来修饰来响应单一的用 CSS 或 JavaScript。通过在其中插入 <figcaption>（作为第一个或最后一个子元素），可以将标题与 `<figure>` 元素相关联。图中找到的第一个`<figcaption>`元素显示为图的标题。

>与`<span>`不同的是，`<div>`是块级元素（block）

<p><a id=figure></a></p>

#### \<figure>:可附标题内容元素

**相关标签**
- <p><a href="#img">&ltimg&gt</a></p>
- <p><a href="#responsive">响应式图片设计</a></p>
---


`<figure>`元素代表一段独立的内容，可能包含`<figcaption>`元素定义的说明元素。该插图、标题和其中的内容通常作为一个独立的引用单元。通常，`<figure>` 的内容为图像、插图、图表、代码片段等，在文档的主内容流中引用，但可以移动到文档的另一部分或附录而不影响主内容流。
>\<figcaption> 元素 是与其相关联的图片的说明/标题，用于描述其父节点\<figure> 元素里的其他数据。

*例：*
```html
<figure>

  <blockquote>
      我们因为无知而读书，而我们读书让我们更加地觉得自己的无知。
  </blockquote>
  <figcaption><b>罗翔</b></figcaption>
</figure>
```
*输出：*

<img src="Images/image-2.png">

<p><a id=img></a></p>

#### \<img>：图像嵌入元素


**相关连接**
- <p><a href="#figure">&ltfigure&gt</a></p>
- <p><a href="#responsive">响应式图片设计</a></p>
---
用于插入一张图片，常规用法如例1所示：
*例1：*
```html
<img src="Images/ex1.jpg" alt="一只小狗" title="一只小狗" width=200> 
<!--alt值为文件无法访问时的描述文本-->
```
<dl>
  <dt>alt属性</dt>
  <dd>当图片不能正常显示时显示的文本内容</dd>
  <dt>title属性</dt>
  <dd>图片辅助说明文本，鼠标放置于图片上方触发</dd>

  <dt>heigh/width</dt>
  <dd>图片高度/宽度</dd>

</dl>

*输出：*
<center>
    <img src="Images/ex1.jpg" alt="一只小狗" title="一只小狗" width=200>
</center>




*例2：*

```html
<img 
  srcset="Images/1.jpg 5000w, Images/2.jpg 3000w"
  sizes="(max-width: 600px) 3000px,
         5000px"
  src="Images/2.jpg"
  alt="一张风景图"/>
```


#### \<link>：外部资源链接元素
规定了当前文档与外部资源的关系。该元素最常用于链接样式表

#### \<meta>：元数据
元数据就是描述数据的数据

#### \<picture> 
- <p><a href="#img">&ltimg&gt</a></p>
- <p><a href="#responsive">响应式图片设计</a></p>
---
`<picture> `元素包含了一些`<source>`元素，它使浏览器在不同资源间做出选择，紧跟着的是最重要的`<img>`元素。


```html
<picture>
  <source media="(max-width: 800px)" srcset="../Images/2-3000.jpg">
  <source media="(min-width: 800px)" srcset="../Images/1-5000.jpg" >
  <img src="elva-800w.jpg" alt="Chris standing up holding his daughter Elva" >
</picture>

```



#### \<span>:无语义元素
是短语内容的通用行内容器，并没有任何特殊语义。
>与`<div>`不同的是，`<span>`是内联（inline）无语义元素。

<a id="video"></a>
#### \<video>元素
*相关标签*
<p><a href="#audio">&lt audio&gt</a>

---

用于嵌入视频，它的简单用法如例1所示
*例1：*
```html
<video src="Images/firework.mp4" 
       width=500
       controls>
    <p>
      你的浏览器不支持 HTML5 视频。可点击<a href="Images/firework.mp4">此链接</a>观看
    </p>
</video>
```
<center>
<video src="Images/firework.mp4" 
       width=500
       controls>
    <p>
      你的浏览器不支持 HTML5 视频。可点击<a href="Images/firework.mp4">此链接</a>观看
    </p>
</video>
</center>

>在VScode+Markdown Preview Enhanced v0.8.11环境下预览无法播放视频，原因是临时预览文件的文件夹位置发生变动，使目标地址发生更改。在md生成的Html页面中能正常播放。

在不支持 video 元素的浏览器中，\<video>\</video> 标签中间的内容会显示，作为降级处理。常用属性如下：
<dl>
  <dt>src<dt>
  <dd>要嵌到页面的视频的URL。可以使用 &ltvideo&gt元素块内的&ltsource&gt元素来指定需要嵌到页面的视频。</dd>
  <dt>width/height<dt>
  <dd>指定视频宽度/高度</dd>
  <dt>autoplay</dt>
  <dd>布尔属性，声明该属性后，视频会尽快自动开始播放</dd>
  <dt>controls</dt>
  <dd>加上这个属性，浏览器会在视频底部提供一个控制面板，允许用户控制视频的播放，包括音量，跨帧，暂停/恢复播放。如果没有指定 controls 属性，那么视频不会展示浏览器自带的控件。</dd>
  <dt>loop</dt>
  <dd>布尔属性；指定后，会在视频播放结束的时候，自动返回视频开始的地方，继续播放。</dd>
  <dt>muted</dt>
  <dd>布尔属性，指明在视频中音频的默认设置。设置后，音频会初始化为静音。默认值是 false, 意味着视频播放的时候音频也会播放。</dd>
  <dt>poster</dt>
  <dd>海报帧图片 URL，用于在视频处于下载中的状态时显示。如果未指定该属性，则在视频第一帧可用之前不会显示任何内容，然后将视频的第一帧会作为海报（poster）帧来显示。</dd>

</dl>

>如果使用 autoplay="false" 来关闭视频的自动播放功能，会不起作用；只要 `<video>` 标签中有 autoplay 属性，视频就会自动播放。

*例2：*
```html
<video controls  loop  width="500"  poster="Images/image-3.png">
  <source src="Images/firework.mp4"/>
  抱歉，你的浏览器不支持内嵌视频!
</video>
```

<center>
  <video controls  loop  width="500"  poster="Images/image-3.png">
    <source src="Images/firework.mp4"/>
    抱歉，你的浏览器不支持内嵌视频!
  </video>
</center>

>播放前视频尺寸为poster指向图片的尺存






## 常用技巧

<p><a id="responsive"></a></p>

### 响应式图片设计


**方式一：使用\<img>标签和css样式**


定义展示图片的最大宽度：
```css 
img{ 
  max-width: 90vw;
  height: auto;
}
```

定义图片选择条件
```html
<img srcset="/Images/2-3000.jpg 3000w,/Images/1-5000.jpg 5000w"
    sizes="(max-width:800px) 3000px,5000px"
    alt="erro"
    src="/Images/2-3000.jpg"   
>
```
不支持`srcset`和`sizes`特性的浏览器会忽略，直接加载`src`中的图片。
>注意,在原始图片记载之后，在你改变视口的大小的时候，图片不会改变大小。srcset 和 sizes 属性在第一次加载的时候根据媒体条件加载图片时起作用，但在屏幕改变大小时不会起作用。

方式二:使用\<picture>+css

```html
<picture>
    <source media="(max-width: 800px)" srcset="Images/2-3000.jpg">
    <source media="(min-width: 800px)" srcset="Images/1-5000.jpg" >
    <img src="Images/erro.jpg" alt="山水图" >
  </picture>
```
在任何情况下，都必须在 `</picture>` 之前正确提供一个 `<img>` 元素以及它的 src 和 alt 属性，否则不会有图片显示。当媒体条件都不返回真的时候（你可以在这个例子中删除第二个 `<source>` 元素），它会显示默认图片；如果浏览器不支持 `<picture>` 元素时，它可以作为后备方案。

然后对\<img>标签编写样式：
```css
img{ 
  max-width: 90vw;
  height: auto;
}
```