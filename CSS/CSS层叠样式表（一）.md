## 1.CSS简介
css的主要使用场景就是美化网页，布局页面的。
### 1.1 HTML的局限性
说起HTML，这其实是个非常单纯的家伙，他只关注内容的语义。比如`<h1>`表明这是一个大标题，`<p>`表明这是一个段落，`<img>`表明这有一个图片，`<a>`表示此处有链接。
### 1.2 CSS
CSS是层叠样式表的简称。有时我们也会称之为CSS样式表或级联样式表。

CSS也是一种标记语言

CSS主要用于设置HTML页面中的文本内容（字体、大小、对齐方式等）、图片的外形（宽高、边框样式、边距等）以及版面的布局和外观显示样式。
### CSS 语法规范
使用HTML时，需要遵从一定的规范，CSS也是如此。要想熟练的使用CSS对网页进行修饰，首先需要了解CSS样式规则。

CSS规则由两个主要部分构成：选择器以及一条或多条声明。

- 选择器是用于指定CSS样式的HTML标签，花括号内是对该对象设置的具体样式
- 属性和属性值以“键值对”的形式出现。
- 属性是指对指定的对象设置的样式属性，例如字体大小、文本颜色等
- 属性和属性值之间用英文“；”分开
## 2. CSS基础选择器
### 2.1 CSS选择器的作用
选择器（选择符）就是根据不同需求把不同的标签选出来这就是选择器的作用，简单来说，就是选择标签用的。
### 2.2 选择器的分类
选择器分为基础选择器和复合选择器两个大类，我们这里先讲解一下基础选择器。

- 基础选择器是由单个选择器组成的。
- 基础选择器又包括：标签选择器、类选择器、id选择器和通配符选择器。
### 2.3标签选择器
标签选择器（元素选择器）是指用HTML标签名称作为选择器，按标签名称分类，为页面中某一类标签指定统一的CSS样式。

**作用**

标签选择器可以把某一类标签全部选择出来，比如所有的`<div>`标签和所有的`<span>`标签

**优点**

能快速为页面中同类型的标签统一设置样式

**缺点**

不能设计差异化样式，只能选择全部的当前标签。
### 2.4类选择器
如果想要差异化选择不同的标签，单独选一个或者某几个标签，可以用类选择器。

类选择器在HTML中以class属性表示，在CSS中，类选择器以一个点“.”
号显示。
**
注意**
①类选择器使用“.”（英文点号）进行标识，后面紧跟类名（自定义，我们自己命名的）
②长名称或词组可以使用中横线来为选择器命名。
③不要使用纯数字、中文等命名，尽量使用英文字母来表示。

    .类名{
        属性1：属性值1；
    }
    
### 2.4类选择器-多类名
我们可以给一个标签指定多个类名，从而达到更多的选择目的，这些类名都可以选出这个标签。（简单理解就是一个标签有多个名字）

1.多类名使用方法

    <div class="red font20">亚瑟</div>
    
(1)在标签class属性中写多个类名

(2)多个类名中间必须用空格分开

(3) 这个标签就可以分别具有这些类名的样式
### 2.5 id选择器
id选择器可以为标有特定id的HTML元素指定特定的样式。HTML元素以id属性来设置id选择器，CSS中id选择器以 “#”来定义。
#### 语法

    #id名{
        属性1：属性值1；
        ...
    }
    
### 通配符选择器
在CSS中，通配符选择器使用“*”定义，它表示选取页面中所有元素（标签）
#### 语法

    *{
        属性1：属性值1
        ...
    }
    
- 通配符选择器不需要调用，自动就给所有的元素使用样式
- 特殊情况下才使用，后面讲解使用场景（以下是清楚所有元素标签的内外边距）


    *{
        margin:0;
        padding:0;
    }
    
### 2.7 基础选择器

标签选择器|可以选出所有相同的标签|不能差异化选择|较多|p{color:red} 
---|:--:|---|:--:|---|:--:|
类选择器|可以选出1个或多个标签|可以根据需求选择|非常多|.nav{color:red}
id选择器|1次只能选择1个标签|ID属性只能在每个HTML文档中出现一次|一般和is搭配|#nav{color:red}
通配符选择器|选择所有的标签|需要的太多，有部分不需要|特殊情况使用|*nav{color:red}
## 3. CSS 字体选择
CSS Font(字体)属性用于定义字体系列、大小、粗细、和文字样式（如斜体）
### 3.1 字体系列
CSS使用font-family属性定义文本的字体系列

    p{ font-family："微软雅黑"；}
    div{font-family:Arial,"Microsoft Yahei","微软雅黑"}
    
- 各种字体之间必须使用英文状态下的逗号隔开
- 一般情况下，如果有空格隔开的多个单词组成的字体，加引号
- 尽量使用系统默认自带字体，保证在任何用户的浏览器中都能正确显示。
### 3.2字体大小
CSS使用font-size属性定义字体大小

    p{
        font-size:20px;
    }
    
- px(像素)大小是我们网页的最常用的单位。
- 谷歌浏览器默认的文字大小是16px
- 不同的浏览器可能默认显示的字号大小不一致，我们尽量给一个明确值的大小，不要默认大小。
- 可以给body指定整个页面文字的大小
### 3.3 字体粗细
CSS使用font-weigh属性设置文本字体的粗细

    p{
        font-weight:bold;
    }
    
属性值|描述|
---|:--:|
normal|默认值（不加粗的）
bold|定义加粗（加粗的）
100-900|400等同于normal，而700等同于bold 注意这个数字后面不跟单位
### 3.4 文字样式
CSS使用font-style属性设置文本的风格

    p{
        font-style:normal;
    }
    
属性值|作用|
---|:--:|
normal|默认值，浏览器会显示标准的字体样式 font-style；normal； 
italic|浏览器会显示斜体的字体样式
### 3.5 字体复合属性
字体属性可以把以上文字样式综合来写，这样可以更节约代码

    body{
        font：font-style font-weight font-size/line-height font-family;
    }
    
- 使用font属性时，必须按上面语法格式中的顺序书写，**不能更换顺序**，并且各个属性间以空格隔开。
- 不需要设置的属性可以省略（取默认值），但**必须保留font-size和font-family属性**，否则font属性将不起作用
### 3.6 字体属性总结
    
属性|表示|注意点
---|:--:|---|:--:|
font-size|字号|我们通常用的单位是px像素，一定要跟上单位 
font-family|字体|实际工作中按照团队约定来写字体
font-weight|字体粗细|加粗是700或者bold  不加粗是normal 或者400  记住**数字不要跟单位**
font-style|字体样式|记住倾斜式italic   不倾斜是normal  工作中我们最常用 normal
font|字体连写|1.字体连写是有顺序的 不能随意换位置 2.其中字号 和字体 必须同时出现
## 4. CSS文本属性
CSS Text(文本)属性可以定义文本的外观，比如文本的颜色、对齐文本、装饰文本、文本缩进、行间距等
### 4.1 文本颜色
color属性用于定义文本的颜色

    div{
        color：red；
    }
    
表示|属性值|
---|:--:|
预定义的颜色值|red,green,blue,pink
十六进制|#FF6600,#29D794
RGB代码|rgb(255,0,0)或rgb(100%,0%,0%)
### 4.2 对齐文本
text-align属性用于设置元素内文本内容的水平对齐方式

    div{
        text-align：center；
    }
    
属性值|解释|
---|:--:|
left|左对齐（默认值）
right|右对齐
center|居中对齐
### 4.3 装饰文本
text-decoration属性规定添加到文本的修饰。可以给文本添加下划线、删除线、上划线等

    div{
        text-decoration:underline;
    }
    
属性值|描述|
---|:--:|
none|默认，没有装饰线(最常用)
underline|下划线，链接a自带下划线
overline|上划线(几乎不用)
line-through|删除线(不常用)
### 4.4 文本缩进
text-indent属性用来指定文本的第一行缩进，通常是将段落首行缩进。

    div{
        text-indent：10px;
    }
通过设置该属性，所有元素的第一行都可以缩进一个给定的长度，甚至该长度可以是负值

    p{
        text-indent：2em;
    }
em是一个相对单位，就是当前元素(font-size)1个文字的大小，如果当前元素没有设置大小，则会按照父元素的1个文字大小
### 4.5 行间距
line-height属性用于设置行间的距离（行高）可以控制文字行与行之间的距离。

    p{
        line-height：26px;
    }
### 4.6 文本属性总结
属性|表示|注意点
---|:--:|--:|
color|文本颜色|我们通常用 十六进制 比如 而且是简写形式 #fff
text-align|文本对齐|可以设定文字水平的对齐方式
text-indent|文本缩进|通常我们用于段落首行缩进2个字的距离 text-indent：2em；
text-decoration|文本修饰|记住添加下划线 underline 取消下划线 none
line-height|行高|控制行与行之间的距离
## CSS 引入方式
### 5.1 CSS的三种样式表
按照CSS样式书写的位置(或者引入的方式)，CSS样式表可以分为三大类：

1.行内样式表(行内式)

2.内部样式表(嵌入式)

3.外部样式表(链接式)
### 5.2 内部样式表
内部样式表（内嵌样式表）是写到html页面内部，是将所有的CSS代码抽取出来，单独放到一个`<style>`标签中。

    <style>
       div{
           color：red；
           font-size：12px
       }
    </style>
- <style>标签理论上可以放在HTML文档的任何一个地方，但一般会放在文档的<head>标签中
- 通过此种方式，可以方便控制当前整个页面中的元素样式设置。
- 代码结构清晰，但是并没有实现结构与样式完全分离
- 使用内部样式表设置CSS，通常也被称为嵌入式引入，这种方式是我们练习时常用的方式
### 5.3 行内样式表
行内样式表(内联样式表)实在元素标签内部的style属性中设定CSS样式。适合于修改简单样式

    <div style="color:red; font-size:12px;">青春不常在，抓紧谈恋爱</div>
- style 其实就是标签的属性
- 在双引号中间，写法要符合CSS规范
- 可以控制当前的标签设置样式
- 由于书写繁琐，并且没有体现出结构与样式分离的思想，所以不推荐大量使用，只有对当前元素添加简单样式的时候，可以考虑使用
- 使用行内样式表设定CSS，通常也被称为行内式引入
### 5.4 外部样式表
实际开发都是外部样式表，适合于样式比较多的情况，核心是：样式单独写到CSS文件中，之后把CSS文件引入到HTML页面中使用。

引入外部样式表分为两步：

1.新建一个后缀名为.css的样式文件，把所有CSS代码都放入此文件中。
2.在HTML页面中，使用`<link>`标签引入这个文件。

    <link rel="stylesheet" href="css文件路径">
    
属性|作用|
---|:--:|
rel|定义当前文件与被链接文档之间的关系，在这里需要指定为“stylesheet”，表示被链接的文档是一个样式表文件|
href|定义所链接外部样式表文件的URL，可以是相对路径，也可以是绝对路径。
- 使用外部样式表设定CSS，通常也被称为外链式或链接式引入，这种方式是开发中最常用的方式。
### 5.5 CSS引入方式总结

样式表|优点|缺点|使用情况|控制范围
---|:--:|---|:--:|---|:--:
行内样式表|定义当前文件与被链接文档之间的关系，在这里需要指定为“stylesheet”，表示被链接的文档是一个样式表文件|结构样式混写|较少|控制一个标签|
内部样式表|部分结构和样式相分离|没有彻底分离|较多|控制一个页面
外部样式表|完全实现结构和样式相分离|需要引入|最多，吐血推荐|控制多个页面
