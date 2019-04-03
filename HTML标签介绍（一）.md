# HTML常用标签介绍(一)



>本文将会介绍HTML中的一些常用标签，后面还会陆续整理


### 1:什么是HTML
HTML （Hypertext Markup Language）即超文本标记语言。HTML用于网页的制作，被浏览器解释后可以呈现出各式各样的精美页面。



### 2:HTML基本结构 
````
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>

</body>
</html>
````

###### 1：``<!DOCTYPE html>``
``<!DOCTYPE html>`` 即HTML 5 标准网页声明 ``<!DOCTYPE>`` 声明必须处于HTML最前面的位置，它可以告诉浏览器使用哪种HTML规范进行解析.
###### 2：标签及属性
标签是HTML组成的单元。标签一般都会成对出现,例如：``<p></p>`` 在这种标签内部可以嵌套其他标签如：``<p><strong></strong></p>`` 。除了这种以“开始标签”开头并且有“结束标签”进行闭合的标签外，还有一种标签，它的内部无法嵌套其他元素，这种标签叫做“空标签” 如：``<img>``标签。在``DOCTYPE``声明后所有以"<>"形式存在的东西都是HTML的标签。
- ``<html lang="en"><html>``
html标签是最基本的标签，所有的标签都被嵌套在html标签内部。``lang="en"`` 其中``lang``是html标签的一个属性,``lang``属性规定html内容的语言即：language的简称， ``en``则是lang这个属性的值即english ，除了 ``en``这个值 还有 ``lang="zh_CN"`` 即简体中文。如果你使用了``<html lang="en"><html>`` 有些浏览器在显示这个页面时会提示你是否需要翻译，而``<html lang="zh_CH"><html>`` 则不会出现这样的提示，但是我们在书写HTML时，一般还是会定义为``<html lang="en"><html>``.
-  ``<head></head>``
head标签用于定义HTML的头部且其内容不会显示在HTML页面上。head标签内可以引入脚本，引入样式表等。可以被嵌套在head标签内的标签有：``<base>``,``<link>``,``<meta>``,``<script>``,``<style>``,``<tilte>``其中 ``<title>``标签的作用是定义页面的标题，它是head标签中**唯一必须的元素**。在head内可以使用的标签只有这六个，写入其他标签，浏览器会自动纠错到body标签中。
- ``<meta charset="UTF-8">``
``<meta charset="UTF-8">`` 规定了HTML的字符编码。
-  ``<title>Document</title>``
title标签定义了页面的标题，在浏览器打开页面时，浏览器上方的标题栏上呈现的内容就是title标签里面定义的。
-  ``<body></body>``
body标签定义了HTML内容的主体，body标签也是一个HTML带有最基本的必须元素。
###3:文字和段落
######1：标题标签
``<h1></h1>``~``<h6></h6>``. 从h1到h6 由大到小 HTML规定了六个标题标签
######2：p标签
``<p></p>`` 标签的英文全程为：paragraph 即 段落。在p标签内的文字进行手动缩进和换行都没有任何意义，除非使用代码操作。p标签中需要了解的属性为：align.
````
<p align="left">Hello,HTML</p>
<p align="right">Hello,HTML</p>
<p align="center">Hello,HTML</p>
<p align="justify">Hello,HTML</p>
````
align属性四个值分别可以将段落内的文字进行左对齐，右对齐，中间对齐以及伸展对齐。
###### 3：pre标签
``<pre></pre>``标签为预格式标签。在预格式标签中 可以人为进行缩进与换行操作  并且按照pre标签里的格式将内容展现出来 。
###### 4：换行与水平线
``<br>``标签的功能是换行，``<hr>``标签的功能是显示一条水平线。这两个标签都是空标签。
###### 5：斜体，加粗，放大及缩小
- ``<i></i>`` 
i标签 italic 即斜体，被i标签齐嵌套的文字会以斜体的形式呈现，i标签现在基本已经被em标签所取代。
-  ``<em></em>``
em 标签 emphasized 强调。em标签与i标签所呈现的样式是一样的，但是em标签更注重语意。如果你想在一段文字中对某些文字进行强调并希望被强调的文字以斜体的形式呈现 那么就应该使用em标签 而非 i标签。
-  ``<b></b>``
b标签 bold 加粗。b标签现在基本已经被strong标签所取代。
-  ``<strong></strong>``
strong 标签所产生的效果也是对被嵌套的文字进行加粗显示 单纯看效果和b标签是相同的，但是strong 标签更强调的是语意。如果你想在一段文字中对某些文字进行强调并希望被强调的文字加粗显示，那么就应该使用strong标签而非 b标签
-  ``<big></big>``和``<small></small>``
字体加大一号与字体缩小一号。不过有些浏览器并不支持big标签
######6：上标及下标
``<sup></sup>``是上标标签 如：``x<sup>2</sup>`` 效果为：x². `` 与上标标签相对的 <sub></sub>``是下标标签。

###### 7：特殊符号
在HTML的页面中想要显示出``<p>`` 这样一个内容则需要将``<`` "p" 以及``>``写在HTML里，但是这样``<p>``就会被浏览器解释为标签。所以HTML需要一些特殊的符号来对某些类似于``<``和``>``这样的符号进行转义。常见的特殊转义符有：
-  ``&lt;`` 即：&lt;
-  ``&gt;`` 即：&gt;
-  ``&reg;`` 即：&reg; 已注册
-  ``&copy;`` 即：&copy; 版权
-  ``&trade`` 即：&trade; 商标
-  ``&nbsp;`` 即：&nbsp; 空格
###### 8：注释
在HTML中 注释的写法
````
<!--注释内容-->
````
###4:列表
######1：无序列表
无序列表是由``<ul></ul>``标签和``<li></li>``标签组成的。
````
<ul>
   <li>列表项</li>
   <li>列表项</li>
   <li>列表项</li>
   .........
</ul>
````
ul标签的type属性可以决定列表项的无序标识符的样式，默认的样式为 type="disc" 即实心黑圆点。除了disc还有 square(正方形) ,circle(空心圆)。但是这个属性已经不用了，不是不能使用，而是现在都使用CSS样式来进行控制。
######2：有序列表
有序列表是由``<ol></ol>``标签和``<li></li>``标签组成的。
````
<ol>
      <li>列表项</li>
      <li>列表项</li>
      <li>列表项</li>
      ........
</ol>
````
###### 3：定义列表
定义列表标签为``<dl></dl>``在定义列表内有``<dt></dt>``标签和``<dd></dd>``标签。其中 dt标签用于定义列表项 ，dd标签则用于对列表项的详细描述。 对于一个dt列表项 可以有多个dd标签对列表项进行描述。三者要组合使用。如：
````
    <dl>
        <dt>计算机</dt>
        <dd>用来计算的仪器</dd>
        <dd>用来玩游戏的神器</dd>
        <dt>电视机</dt>
        <dd>以视觉方式显示信息的装置</dd>
        <dd>娱乐消遣的神器</dd>
    </dl>
````

### 5:img标签
``<img>``标签是用来在页面插入图像的标签，img标签的常用属性有：
- src
src属性是img标签必需写的属性，src的值是图像的地址，可以写入相对路径或绝对路径。
- alt
alt属性是在当图像无法顺利加载在页面上时，代替图像显示在页面上的文字内容。
- width，height
width 和 height 属性指定图像显示的宽和高。width的值可以是百分比或是像素值，当其值为百分比时指的是相对于当前浏览器窗口宽度的宽度的百分比。而height属性的值只能是像素值。

img标签除了是一个空标签还是一个可替换标签，可替换标签的含义是这个标签的展现并非是由浏览器的CSS渲染来控制的，而是它自身决定的。一张图片的大小，宽和高决定了它在页面的宽和高。

### 6:a标签和iframe标签
a标签的作用是点击实现超链接。iframe标签的作用是在一个页面上嵌套另一个页面。我们先从iframe说起。
- iframe标签
iframe标签常用的属性有src以及 frameborder 属性。即：``<iframe src="" frameborder=""></iframe>``。src属性指的是当前页面嵌套的页面的地址，frameborder属性通常设置值为0，如果没有设置frameborder="0"或者没有写frameborder属性，那么在当前页面上就会看到一个3D的嵌套框。
-  a 标签
a标签的作用是实现超链接，常用的属性有href ，download 和taget以及title。
-  a标签常用的属性：download
download属性指示浏览器下载URL而并非导航到它，因此将提示用户将其保存为本地文件。
-  a标签常用的属性：href
包含超链接指向的URL或URL片段。URL片段是哈希标记"#"前面的名称，哈希标记指定当前文档的内部目标位置（HTML元素的id）。如"<a href="#1">linkto1</a>" 点击此链接将跳转到当前页面的id等于1的标签位置处。另外可以使用``href="#top"``或者``href="#"``链接用来返回到页面的顶部，这是HTML5的特性。
-  a标签常用的属性：target
指定在何处显示链接资源。target的值有五种。
1. -self:当前页面加载链接的资源
2. -blank:新窗口加载链接的资源
3. -parent:在父框架中打开链接，如果没有父框架，此选项的行为与-self相同
4. -top:在顶级框架中打开链接，如果没有parent关系，此选项的行为与-self相同。如示例：
````
<!--index.html-->
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Index</title>
    <style>
        iframe{
            width: 80%;
            height: 400px;
        }
    </style>
</head>
<body>
    <iframe src="./index2.html" ></iframe>
</body>
</html>
<!--index2.html-->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Index2</title>
    <style>
        iframe{
            width: 80%;
            height: 200px;
        }
    </style>
</head>
<body>
    <p>这是index2.html的内容</p>
    <iframe src="./index3.html" ></iframe>
</body>
</html>
<!--index3.html-->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Index3</title>
</head>
<body>
    <p>这是Index3.html的内容</p>
    <div>
        <a target="_top" href="https://www.qq.com" download>qq</a>
    </div>
</body>
</html>
````
点击链接后，发生跳转的位置在顶级框架index.html加载。如果将index3.html的target属性值改为"_parent" 那么会在父级框架 index2.html中打开链接。
5. iframename ：当target=" iframename"时，点击链接可以在指定的 ``<iframe name="iframename"></iframe>`` 中打开链接。如示例：
````
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Test</title>
    <style>
        iframe{
            width: 80%;
            height: 400px;
        }
    </style>
</head>
<body>
    <iframe name="xxx" src="#" frameborder="0"></iframe>
    <div>
        <a href="https://www.qq.com" target="xxx">点击</a>
    </div>
</body>
</html>
````
-  a标签常用的属性：title
title属性的功能是当鼠标停留在链接位置片刻，浮现出一段提示性文字，提示性文字的内容就是title属性对应的值。

### 7:a标签(续)
除了上面有关a标签的用法，a标签还有很多用法。而重点就是a标签的本质以及href这个属性。
1. href属性
href 属性的值为超链接的地址，而且href属性的值应该写完整的URL，比如：``<a href="https://www.baidu.com">百度</a>``。但也可以这样写：``<a href="//www.baidu.com">百度</a>`` ,这种无协议href的写法，会让浏览器根据当前协议，自动补全无协议链接的协议，如果使用file:// 协议浏览当前页面就会访问到``file://www.baidu.com``这个地址，需要注意的是应该尽量不要使用file://协议去预览网页（因为使用了file协议 就无法使用POST请求）。如果你有GitBash 可以通过命令``npm i -g http-server`` 下载一个http-server。下载完毕后在当前要预览的页面路径下使用GitBash 并键入``http-server``或者``http-server -c-1``命令 开启服务器。这样你就可以使用http协议，而a标签的href属性值也可以使用无协议链接的这种href写法了，点击链接后，浏览器仍然能跳转到``https://www.baidu.com``上。

1. a标签的本质。
点击链接的过程，实际上就是发起一次GET请求的过程。如：
````
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Test</title>
</head>
<body>
    <a href="?name=Dobby">link</a>
</body>
</html>
````
``<a href="?name=Dobby">link</a>`` a标签中的href的值为"?name=Dobby"。首先在GitBash上开启http-server,然后在浏览器的URL上输入localhost:8080/test.html（我的页面命名为test.html），并F12开启开发者工具，点击链接。点击链接后地址栏的URL变为：``http://localhost:8080/test.html?name=Dobby``
而在开发者工具的Network  Headers的信息中 可以看到 Query String Parameters 下 的请求参数为name=Dobby。这说明**a标签的本质就是发起GET请求**。

3. 锚链接
锚链接可以实现在当前页面上，对不同为值的跳转，也叫书签。``<a href="#">link</a>`` 点击这个链接，会返回到页面的顶部，在上文也有提到过 #代表的含义是当前页面的意思。可以在页面中设置不同的锚点如：``<span id="1"></span>``,``<span id="2"><span>``等等，可以利用 ``<a href="#1">link</a>`` 跳转到 ``<span id="1"></span>``的位置。
4. 刷新页面
``<a href="">link</a>``点击这样一个链接就可以刷新页面，也就是浏览器重新向服务器发起一个GET请求。当理解了**a标签的本质就是发起GET请求**。那么也不难理解``<a href="">link</a>``的作用就是刷新页面了。
5. a标签的JavaScript 伪协议。
如代码：``<a href="javascript:alert(1)">link<a>``在点击链接后，会执行javascript代码，即弹出提示框，内容为"1"。这个功能是历史遗留下来的，为了可以点击链接执行JS的代码，a标签支持这种javascript伪协议即 冒号后面可以写JS的代码。其中最常用的一个功能就是``<a href="javascript:;" >link</a>``这个链接点击后页面不会有任何发应，``<a href="#" >link</a>`` 的功能是让页面回到顶部，``<a href="" >link</a>``的功能则是刷新页面，而``<a href="javascript:;" >link</a>`` 的功能则是实现点击后没有任何动作的a标签，从而满足一些奇葩功能。
6. a标签的邮件链接
如：``<a href="mailto:xxx@qq.com">link</a>`` 同javascript伪协议一样，a标签也支持"mailto"伪协议.在点击链接后，会弹出邮件功能，并在收件人一项下自动补全收件人邮箱即``mailto:``后面的邮箱地址。
7. a标签创建一个可点击的图片（点击图片跳转链接）
``<a href="跳转链接的地址"><img src="图片的URL" alt="xxx"></a>`` 在a标签可以嵌套一个img标签 ，这样就可以实现点击图片跳转到一个URL上的功能。
5. a标签的download属性
a标签的download属性定义了这个a标签的作用为下载。download属性也叫布尔属性，也就是说download的值只能为true或者 false。但是一般情况都不会去写download="true" 或者 download="false" 因为只要在标签写上了download属性就默认它的值为true，不写即是false。例如：``<a href="http://qq.com" download>link</a>``在点击链接后，``http://qq.com``的内容会下载下来。其实页面的下载是由服务器给浏览器的响应决定的，如果这个页面的``content-type:application/octet-stream`` ，那么当请求到这个页面时，这个页面就会以下载的方式响应给用户。但是如果这个页面的content-type为：``content-type:text/html`` 你又想下载此页面，那么需要在a标签上加上download属性。
6. a标签创建电话链接
``<a href="tel:+491570156">+491570156</a>`` 这个例子是MDN上的例子，这个用法是给a标签创建电话链接。