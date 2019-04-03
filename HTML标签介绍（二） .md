# HTML常用标签介绍(二)

>本文将继续上文接着介绍一些HTML常用标签
### 1:HTML全局属性
在介绍常用常见的HTML标签之前，先以最简单的方式介绍一下HTML当中的全局属性。
-   [accesskey](https://www.w3.org/TR/html5/editing.html#element-attrdef-global-accesskey)
accesskey属性规定激活元素的快捷键
-  [class](https://www.w3.org/TR/html5/dom.html#element-attrdef-global-class)
class属性规定元素的类名

-   [contenteditable](https://www.w3.org/TR/html5/editing.html#element-attrdef-global-contenteditable)
contenteditable。当contenteditable 属性的值设置为true时，就可以使元素在页面中变成可编辑的状态 。例如：
````
<div contenteditable="true">
  This text can be edited by the user.
</div>
````
在设置了 div的contenteditable属性值为true后，div标签内的内容 就可以在页面进入可编辑的状态了。

-   [dir](https://www.w3.org/TR/html5/dom.html#element-attrdef-global-dir)
dir属性规定元素中内容的文本的方向。如：``<div dir="rtl">哈哈哈</div>``rtl 的含义是right to left 该元素出现的位置在页面的右边
-   [draggable](https://www.w3.org/TR/html5/editing.html#element-attrdef-global-draggable)
规定在拖动被拖动数据时是否进行复制、移动或链接。
-   [hidden](https://www.w3.org/TR/html5/editing.html#element-attrdef-global-hidden)
规定元素仍未或不再相关。
-   [id](https://www.w3.org/TR/html5/dom.html#element-attrdef-global-id)
规定元素的唯一的id（按照标准定义，每个元素应该只有一个id且不重复）
-   [lang](https://www.w3.org/TR/html5/dom.html#element-attrdef-global-lang)
规定元素内容的语言。如 ``<html lang="en">``或者是``<html lang=zh_Hans>`` 两者的区别是``lang="en"`` 在某些浏览器打开时，会提示是否进行翻译。
-   [spellcheck](https://www.w3.org/TR/html5/editing.html#element-attrdef-global-spellcheck)
规定是否对元素进行拼写和语法检查。
-   [style](https://www.w3.org/TR/html5/dom.html#element-attrdef-global-style)
规定元素的行内CSS样式。
-   [tabindex](https://www.w3.org/TR/html5/editing.html#element-attrdef-global-tabindex)
规定元素的tab键的次序。
-   [title](https://www.w3.org/TR/html5/dom.html#element-attrdef-global-title)
规定有关元素的额外信息。
-   [translate](https://www.w3.org/TR/html5/dom.html#element-attrdef-global-translate)
规定是否应该翻译元素的内容。

HTML全局属性的含义就是这些属性对任一HTML元素

### 2:table标签
HTML中的table标签作用是将数据信息以二维表格的形式在页面上展现出来。HTML的table标签常常被用在页面布局中，但是这种用法在HTML4以后就不再被推荐使用了，而且table这个标签设计的初衷也不是用来进行页面布局的。table标签涉及到很多属性，这些属性现在都可以使用CSS样式来进行控制，比如align属性，bgcolor属性，border属性，cellpadding,cellspacing，frame等等，这些属性，在MDN上全部都是不再被推荐使用的属性，即它们都可以通过CSS样式来进行更好更合理的控制。而且学习这些属性也相当于浪费时间，所以，table标签 将主要介绍其子标签以及简单的应用为主。
````
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Table学习</title>
    <style>
        table{
            border-collapse: collapse;
        }
    </style>
</head>
<body>
<table border="1">
    <caption>课程表</caption>
    <colgroup>
        <col width="80px">
        <col width="80px">
        <col width="80px">
        <col width="80px">
        <col width="80px">
    </colgroup>
    <!--thead-->
    <thead>
        <tr>
            <th>星期一</th>
            <th>星期二</th>
            <th>星期三</th>
            <th>星期四</th>
            <th>星期五</th>
        </tr>
    </thead>
    <!--tbody-->
    <tbody>
        <tr>
            <td>语文</td>
            <td>数学</td>
            <td>英语</td>
            <td>计算机</td>
            <td>美术</td>
        </tr>
        <tr>
            <td>语文</td>
            <td>数学</td>
            <td>英语</td>
            <td>计算机</td>
            <td>美术</td>
        </tr>
        <tr>
            <td>语文</td>
            <td>数学</td>
            <td>英语</td>
            <td>计算机</td>
            <td>美术</td>
        </tr>
    </tbody>
    <!--tfoot-->
    <tfoot>
        <tr>
            <td>休息</td>
            <td>休息</td>
            <td>休息</td>
            <td>休息</td>
            <td>休息</td>
        </tr>
    </tfoot>
</table>
</body>
</html>
````
上面的例子，涵盖了我们暂时需要了解的有关于table标签的用法。首先来看几个标签。
1. caption 标签
``<caption></caption>``caption 标签是表格的标题，它通常作为table标签之后的第一个子元素出现。在没有指定任何CSS样式的前提下，标题会出现在表格上方并相对于表格宽度居中显示。
2. thead标签，tbody标签及tfoot标签
这三个标签是为table表格内容进行结构划分的标签，可以就语意对三个标签进行理解，thead即是 表格头部的结构，tbody是表格主体内容的结构，tfoot则是表格尾部的结构。三者顺序可以打乱，但是表格还是会按照 head->body->foot 这样的结构顺序在HTML页面上进行显示。
3. tr 标签，td标签以及th标签
``<tr></tr>`` tr标签代表的含义是：table row 即表示一行 ,``<td></td>`` td标签代表的含义是：table data 代表一个单元格的数据，``<th></th>`` th标签则表示table head 其含义是一个一列或一行的数据说明项。如上面的HTML文档，``<th></th>.``标签在第一行，其语意为星期，包括th标签，整张表格是一张5✖5的表格。
4. colgroup 标签和 col标签
colgroup标签为HTML表格的列组标签。col 则是 column定义表格当中列，并在colgroup标签内使用。在本例中，colgroup标签和 col标签定义了table当中每一列的宽度为80px。虽然现在不会这样用，但是此例的用法也可以帮助我们学习和理解colgroup 及 col标签的作用。
5. table的边框
在table中如果不写border="1" 这样的属性 那么默认是无边框样式的。在table标签中写上这样的一句话可以在页面中较为直观地看到表格具体的划分情况。在head中 style标签内又规定了table的样式即：``border-collapse: collapse;`` 。如果不加这样的样式，那么table在浏览器中会显示出表格单元格与单元格之间的缝隙。添加了table的样式为``border-collapse: collapse;`` 则会消除单元格与单元格之间的缝隙。
### 3:form标签
在HTML中，表单标签是``<form></form>``。表单的应用场景一般在网站的登陆注册页面上，表单是用来提交数据给服务器的，当一个用户填写表单的数据并点击提交后，浏览器会将用户填写的表单数据进行打包发送给服务器，并由服务器内部的程序进行处理。form表单的本质也是跳转链接，它和a标签的区别就是，a标签是浏览器发起的HTTP GET请求，form表单则是HTTP POST请求，当然这需要指定method属性的值为POST，但是form表单的作用就是提交数据，如果让method="GET" 那么就没有什么意义。因为GET请求会将所有的数据在URL地址栏中显示出来，保密性太差。
1. form标签的属性
- action 
action 属性规定了form提交到哪里。
- method
method属性规定了提交的表单的提交方式是get请求方式还是post请求方式。且表单只允许get方式或post方式进行提交
- target
form表单提交数据会发生链接的跳转，target属性规定了form表单跳转链接的位置。与a标签的target相同。 回顾内容：target属性有五种值 ``_self`` 是在当前页面跳转链接。``_blank``是在空页面（新的页面）跳转链接，``_parent``是在父级框架中跳转链接,``_top``是在顶级框架中跳转链接，同样，我们也可以自定义一个iframename,让target="iframename" 并指定 iframe标签当中的name属性，那么在提交表单时，就会在iframe内发生跳转。
- enctype
enctype默认的值为：``enctype="application/x-www-form-urlencoded"``是HTML表单传输的编码类型，即，它规定了提交表单传递数据的语法 即，其格式为：``xxx=xxx&yyy=yyy&zzz=zzz...``enctype属性的值有：
1. ``application/x-www-form-urlencoded``
2. ``multipart/form-data``
3. ``text/plain``
### 4:input标签
input标签是一个空标签，即input标签不能内嵌其他元素。一个input标签的属性有很多，但是input标签的类型即type属性的值是HTML标签中最多的。我们先从input标签的类型type属性值开始，然后再对input标签的其他属性进行学习。
- input标签的type属性
1. text:文字域
``type="text"``需要定义input标签的name属性
2. password:密码域
``type="password"``另外需要定义input标签的name属性
3. file:文件域
``type="file"``用来上传文件
4. checkbox:复选框
``type="checkbox"``需要定义input标签的name属性以及value属性，且name属性需要保持一致
5. radio:单选框
``type="radio"``需要定义input标签的name属性以及value属性，且name属性需要保持一致
6. button:按钮
``type="button"``按钮
7. submit:提交按钮
表单必须存在的元素就是提交按钮，不然表单则无法提交数据。在input标签中type属性值为按钮类型的 其value属性则是这个按钮的名字。当没有提交按钮``<input type="submit" value="提交">``时，未定义type属性值的button按钮可以升级为提交按钮``<button>提交</button>``。或是button 的type属性值为 submit，即：``<button type="submit">提交</button>`` 在没有``<input type="submit">`` 时也可以作为提交表单的按钮。另外``<input type="image">``即image图像域也可以代替提交按钮。
8. reset:重置按钮
``type="reset"``重置按钮，点击重置后，表单填写的数据在页面上清空
9. hidden:隐藏域
``<input type="hidden" name="xxx" value="例如：这是隐藏域"/>`` 隐藏域在用户的页面上是看不见的，但是用户在提交信息时，隐藏域的信息会同用户表单其他数据一同上传。
10. image:图像域
``<input type="image" name="xxx" src="imgurl"/>`` 在定义了type="image"后 必须要指定图片的URL即src属性的值。图像域可以替代提交按钮，并将图片本身作为一个提交按钮。
- checked属性
checked属性是一个布尔属性。当input标签的type属性为radio或checkbox时，checked属性表示该控件是否时默认选择的状态。
- disabled属性
input标签的disabled属性也是一个布尔属性，表示此表单控件不可用。
- multiple属性
multiple属性指用户是否能输入多个值。
- name属性
除了type="submit" 之外最重要的属性，指控件的名称，与表单一起提交，以name=value的形式传递给服务器。
- placeholder属性
提示文字。如:``<input type="text" placeholder="请输入密码">``
- value属性
在单选框和复选框中，value指定了传递给服务器的值，在按钮中，value代表的含义时按钮的名称。
- size属性
控件初始大小
### 5:label标签
举例说明label标签的用法：
````
<label for="man">男</label><input id="man" type="radio" name="sex" value="man">
````
label 标签的作用就是只要点击label标签的内容，在本例中为"男" ，就可以选中input标签，在本例中只要点击文字"男" 就可以选中单选框。
### 6:button标签
在上文已经提及过，button标签的简单用途，button 标签type属性也有 "button","submit","reset" 三个值，需要注意的是，当没有``<input type="submit">`` 时，``<button>提交</button>`` 或者``<button type="submit'>提交</button>``可以作为表单的提交按钮，而``<input type="button">``或者``<button type="button">提交</button>``则不行。
### 7:select标签,option标签及optgroup标签
input标签的作用即是输入，select标签的作用就是选择。虽然input标签可以是实现单选框和复选框，但是对于一些选择项比较多的情况，使用单选框和复选框则是很不合理的。select标签和option标签可以提供下拉列表的形式，如：城市的选择，就比较适合使用下拉列表。select，option 标签语法格式:
````
<select name="xxx">
    <option  value="111">北京</option>
    <option value="222">深圳</option>
     ......
</select>
````
- select标签常用的属性
1. name 设置提交的name值
2. multiple 设置是否可以多选，如果设置了multiple属性值，在选择时使用ctrl键既可以多选
3. size 设置列表中可见选项的数目
- option标签常用的属性
1. value 用户传递给服务器的值
2. selected 设置选项初始选中的状态
3. disabled 定义此option选项不能选择

例：
````
<select name="city1">
    <option selected>--请选择--</option>
    <option value="bj">北京</option>
    <option value="sh">上海</option>
    <option value="sz">深圳</option>
    <option value="cd">成都</option>
    <option value="sy">松原</option>
    <option value="jl">吉林</option>
    <option value="heb">哈尔滨</option>
    <option value="gz">广州</option>
</select>
````
optgroup标签则可以设置分组的下拉菜单，语法格式为：
````
<select name="xxx">                      
    <optgroup label="1">
        <option value="xx">xx</option>
        <option value="xx">xx</option>
        <option value="xx">xx</option>
        <option value="xx">xx</option>
        <option value="xx">xx</option>
    </optgroup>
    <optgroup label="2">
        <option value="xx">xx</option>
        <option value="xx">xx</option>
        <option value="xx">xx</option>
        <option value="xx">xx</option>
        <option value="xx">xx</option>
    </optgroup>
</select>
````
### 8:textarea 标签
textarea 标签是文字域标签与``<input type="text">``不同 ``<input type="text">``仅能输入一行文字内容，但是textarea 标签却可以输入多行文字内容，并且可以由用户随意拉伸输入框，自己定义文字域输入框的大小，但是这样也及其容易造成一些bug，所以我们一般都会在textarea标签内增加一个 style样式属性， 值为："resize:none".即：
````
<textarea name="info" id="info" style="resize: none;" placeholder="个人介绍"></textarea>
````
未完待续......