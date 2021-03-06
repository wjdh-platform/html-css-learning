## 1. Emmet 语法
Emmet语法的前身是Zen coding,它使用缩写，来提高html/css的编写速度，Vscode内部已经集成该语法。
### 1.1 快速生成HTML结构语法
1.生成标签，直接输入标签名按tab键即可 比如 div 然后tab键，就可以生成`<div></div>`

2.如果想要生成多个相同标签 加上 * 就可以了 比如 div*3就可以快速生成3个div

3.如果有父子级关系的标签，用+就可以了 比如 div+p

4.如果有兄弟关系的标签，用 + 就可以了 比如 div+p

5.如果生成带有类名或者id名字的，直接写 .demo 或者 #two tab键就可以了

6.如果生成的div类名是有顺序的，可以用自增符号$

7.如果想要在生成的标签内部写内容可以用{}表示
### 1.2快速生成CSS样式语法

CSS基本采取简写形式即可

1. 比如w200 按tab 可以生成 width：200px;

2. 比如lh26 按tab 可以生成 line-height：26px；
## 2. CSS的复合选择器
### 1.1 什么是复合选择器
在CSS中，可以根据选择器的类型把选择器分为基础选择器和复合选择器，复合选择器是建立在基础选择器之上，对基本选择器进行组合形成的。

- 复合选择器可以更准确、更高效的选择目标元素(标签)
- 复合选择器是由两个或多个基础选择器，通过不同的方式组合而成的
- 常用的复合选择器包括：后代选择器、子选择器、并集选择器、为类选择器等等
### 1.2 后代选择器(重要)
后代选择器又称为包含选择器，可以选择父元素里面子元素。其写法就是把外层标签写在前面，内层标签在后面，中间用空格分隔。当标签发生嵌套时，内层标签就成为外层标签的后代

语法：

    元素1 元素2 {
        样式声明
    }
    
上述语法表示选择元素1里面的所有元素2(后代元素)

例如：

    ul li {
        样式声明
    }

/*  选择ul里面所有的li标签元素  */

- 元素1和元素2中间用**空格**隔开
- 元素1是父级，元素2是子集，最终选择的是**元素2**
- 元素2可以是儿子，也可以是孙子等，只要是元素1的后代即可
### 1.3 子选择器
子元素选择器(子选择器)只能作为某元素的最近一级子元素。简单理解就是选亲儿子元素。
子元素选择器(子选择器)只能选择作为某元素的最近一级子元素。简单理解就是选亲儿子元素。
语法：

    元素1 > 元素2{
        样式声明
    }
    
上述语法表示选择元素1里面的所有直接后代(子元素)元素2

例如：

    div > p {
        样式声明
    }
    
/* 选择div里面所有最近一级p标签元素  */

- 元素1和元素2中间用**大于号**隔开
- 元素1是父级，元素2是子集，最终选择的是**元素2**
- 元素2必须是**亲儿子**，其孙子、重孙之类都不归他管.你也可以叫他亲儿子选择器。
### 1.4 并集选择器（重要）
并集选择器可以选择多组标签，同时为它们定义相同的样式。通常用于集体声明

并集选择器是各选择器通过英文逗号(,)连接而成，任何形式的选择器都可以作为并集选择器的一部分。

语法

    元素1 ,元素2{
        样式声明
    }
    
上述语法表示选择元素1和元素2

例如：

    ul,div{
        样式声明
    }
    
/*  选择ul 和 div标签元素  */

- 元素1和元素2中间用**逗号隔开**
- 逗号可以理解为**和**的意思
- 并集选择器通常用于集体声明
### 1.5 伪类选择器
伪类选择器用于向某些选择器添加特殊的效果，比如给链接添加特殊效果，或选择第1个，第n个元素。

伪类选择器书写最大的特点是用冒号(:)表示，比如：hover、：first-child

因为伪类选择器很多，比如有链接伪类、结构伪类等，所以这里先给大家讲解常用的链接伪类选择器。
### 1.6 链接伪类选择器

    a:link         /* 选择所有未被访问的链接 */
    a:visited      /* 选择所有已被访问的链接 */
    a:hover        /* 选择鼠标指针位于其上的链接 */
    a:active       /* 选择活动链接（鼠标按下未弹起的链接） */
    
**链接伪类选择器注意事项**

1.为了确保生效，请按照==LVHA==的顺序进行声明：（:link-  :visited-  :hover-  :active）

3.因为a链接在浏览器中具有默认样式，所以我们实际工作中都需要给链接单独指定样式。
### 1.7 `focus` 伪类选择器
：focus伪类选择器用于选取获得焦点的表单元素
焦点就是光标，一般情况下`<input>`类表单元素才能获取，因为这个选择器也主要针对于表单元素来说

语法

    input：focus{
        background-color：red
    }
    
### 1.8 复合选择器总结
选择器|作用|特征|使用情况|隔开符号及用法
---|:--:|---|:--:|---|:--:|
后代选择器|用来选择后代元素|可以是子孙后代|较多|符号是**空格** .nav a
子代选择器|选择最近一级元素|只选亲儿子|较少|符号是**大于** .nav>p
并集选择器|选择某些相同样式的元素|可以用于集体声明|较多|符号是**逗号** .nav,header
链接伪类选择器|选择不同状态的链接|跟链接有关|较多|重点记住a{}和a：hover 实际开发的写法
：focus选择器|选择获得光标的表单|跟表单有关|较少|input：focus 记住这个写法
## 2. CSS 的元素显示模式
### 2.1 什么是元素显示模式
作用：网页的标签非常多，在不同的地方会用到不同类型的标签，了解他们的特点可以更高的布局我们的网页。

元素显示模式就是元素(标签)以什么方式进行显示，比如div自己占一行，比如一行可以放多个span
### 2.2 块元素
常见的块元素有`<h1>~<h6>`、`<p>`、`<div>`、`<ul>`、`<ol>`、`<li>`等，其中`<div>`标签是最典型的块元素。

块级元素特点

①比较霸道，自己独占一行
②高度、宽度，外边距及内边距都可以控制。
③宽度默认是容器(父级宽度)的100%
④是一个容器及盒子，里面可以放行内或者块级元素

**注意**

- 文字类的元素内不能使用块级元素
- `<p>`标签主要用于存放文字，因此`<p>`里面不能放块级元素，特别是不能放`<div>`
- 同理，`<h1>`~`<h6>`等都是文字类块级标签，里面也不能放其他块级元素
### 2.2行内元素
常见的行内元素有`<a>`、`<strong>`、`<b>`、`<em>`、`<i>`、`<del>`、`<s>`、`<ins>`、`<u>`、`<span>`等，其中`<span>`标签是最典型的行内元素。有的地方也将行内元素称为内联元素。

行内元素的特点：
①相邻行内元素在一行上，一行可以显示多个。


②宽、高直接设置是无效的

③默认宽度就是它本身内容的宽度

④行内元素智能容纳文本或其他行内元素

**注意：**

- 链接里面不能再放链接
- 特殊情况链接`<a>`里面可以放块级元素，但是给`<a>`转换一下块级模式最安全
### 2.3 行内块元素
在行内元素中有几个特殊的标签----`<img />`、`<input />`、`<td>`,它们同时具有块元素和行内元素的特点。有些资料称它们为行内块元素。

行内块元素的特点：

①和相邻行内元素（行内块）在一行上，但是他们之间会有空白缝隙。一行可以显示多个（行内元素特点）
②默认宽度就是它本身内容的宽度（行内元素特点）
③高度，行高、外边距以及内边距都可以控制（块级元素特点）
### 2.4元素显示模式总结
元素模式|元素排列|设置样式|默认宽度|包含
---|:--:|---|:--:|---|:--:|
块级元素|一行内只能放一个块级元素|可以设置宽度高度|容器的100%|容器级可以包含任何标签
行内元素|一行可以放多个行内元素|不可以直接设置宽度|它本身内容的宽度|容纳文本或其他行内元素
行内块元素|一行放多个行内块元素|可以设置宽度和高度|它本身内容的宽度

### 2.5 元素显示模式转换
特殊情况下，我们需要元素模式的转换，简单理解：一个模式的元素需要另外一种模式的特性

比如想要增加链接`<a>`的触发范围。

- 转换为块元素：display：block
- 转换为行内元素：display：inline
- 转换为行内块：display：inline-block
### 2.6 单行文字垂直居中的代码
CSS没有给我们提供文字垂直居中的代码，这里我们可以使用一个小技巧来实现。

解决方案：让文字的行高等于盒子的高度 就可以让文字在当前盒子内垂直居中

例如：

height：40px;   

line-height:40px

就可以实现
## 3.CSS背景
通过CSS背景属性，可以给页面元素添加背景样式。

背景属性可以设置背景颜色、背景图片、背景平铺、背景图片位置、背景图像固定等
### 3.1 背景颜色
background-color属性定义了元素的背景颜色

    background-color:颜色值；
    
一般情况下元素背景颜色默认值是transparent(透明)，我们也可以手动指定背景颜色为透明色。
### 3.2 背景图片
background-image属性描述了元素的背景图像，实际开发常见于logo或者一些装饰性的小图片或者是超大的背景图片，优点是非常便于控制位置（精灵图也是一种运用场景）

    background-image:none | url(url)；
    
参数值|作用|
---|:--:|
none|无背景图（默认的）
url|使用绝对或相对地址指定背景图像
### 3.3 背景平铺
如果需要在HTML页面上对背景图像进行平铺，可以使用background-repeat属性。

    background-repeat | no-repeat | repeat-x | repeat-y

    
参数值|作用|
---|:--:|
repeat|背景图像在纵向和横向上平铺（默认的）
no-repeat|背景图像不平铺
repeat-x|背景图像在横向上平铺
repeat-y|背景图像在纵向平铺
### 3.4 背景图片位置
利用background-position属性可以改变图片在背景中的位置

    background-position： x y;
    
参数值|作用|
---|:--:|
length|百分数|由浮点数字和单位标识符组成的长度值
position|top、center、bottom、left、center、right 方位名词

1.参数是方位名词

- 如果指定的两个值都是方位名词，则两个值前后顺序无关，比如left top和top left 效果一致
- 如果只指定了一个方位名词，另一个值省略，则第二个值默认居中对齐
（给body写样式）

2.参数是精准单位

- 如果参数值是精确坐标，那么第一个肯定是x坐标，第二个一定是y坐标。
- 如果是指定一个数值，那该数值一定是X坐标，另一个默认垂直居中

3.参数混合单位

- 如果指定的两个值是精确单位和方位名词混合使用，则第一个值是X坐标，第二个值是Y坐标

### 3.5 背景图像固定(背景附着)
background-attachment属性设置背景图像是否固定或者随着页面的其余部分滚动

background-attachment 后期可以制作视差滚动的效果

    background-attachment：scroll | fixed
    
参数值|作用|
---|:--:|
scroll|背景图像是随对象内容滚动
fixed|背景图像固定
### 3.6 背景复合写法
为了简化背景属性的代码，我们可以将这些属性合并简写在同一个属性**background**中。从而节约代码量，当使用简写属性时，没有特定的书写顺序，一般习惯约定顺序为：

background：背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置

### 3.7 背景色透明
CSS3为我们提供了背景颜色半透明的效果。

    background：rgba（0,0,0,0.3）;
    
- 最后一个参数是alpha透明度，取值范围在0~1之间
- 我们习惯把0.3的0省略掉，写为background：rgba（0,0,0,.3）;
- 注意：背景半透明指盒子背景半透明，盒子里面的内容不受影响。

属性|作用|值
---|:--:|:--|
background-color|背景颜色|预定义的颜色值/十六进制/RGB代码
background-image|背景图片|url（图片路径）
background-repeat|是否平铺|repeat/no-repeat/repeat-X/repeat-Y
background-position|背景位置|length/position 分别是X和Y坐标
background-attachment|北京附着|scroll（背景滚动）/fixed（背景固定）
背景简写|书写更简单|背景颜色 背景图片地址 背景平铺 背景滚动 背景位置；
背景色半透明|背景颜色半透明|background：rgba（0,0,0,0.3）；后面必须是4个值
背景图片：实际开发常见于 LOGO 或者一些装饰性的小图片或者是超大的背景图片，优点是非常便于控制位置
