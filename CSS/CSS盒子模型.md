## 1. 盒子模型
页面布局要学习三大核心，盒子模型，浮动和定位，学习好盒子模型能非常好的帮助我们布局页面
### 1.2 盒子模型（Box Model）组成
所谓盒子模型：就是把HTML页面中的布局元素看作是一个矩形的盒子，也就是一个承装内容的容器

CSS盒子模型本质上是一个盒子，封装周围的HTML元素，它包括：边框、外边距、内边距和实际内容
### 1.3边框（border）
border可以设置元素的边框。边框有三部分组成：边框宽度（粗细） 边框样式 边框颜色

语法：

    border：border-width || border-style || border-color
    
属性|作用
---|:--:|
border-width|定义边框粗细，单位是PX
border-style|边框的样式
border-color|边框颜色
### 1.4 表格的细线边框
border-collapse属性控制浏览器绘制表格边框的方法，它控制相邻单元格的边框

语法：

    border-collapse：collapse；
    
- collapse单词是合并的意思
- border-collapse：collapse；表示相邻边框合并在一起。

### 1.5 边框会影响盒子实际大小
1.测量盒子大小的时候，不量边框

2.如果测量的时候包含了边框，则需要width、height 减去边框宽度。
### 1.6 内边距（padding）
padding属性用于设置内边距，即边框与内容之间的距离。
属性|作用
---|:--:|
padding-left|左内边距
padding-right|右内边距
padding-top|上内边距
padding-bottom|下内边距

padding属性（简写属性）可以有一到四个值。

值的个数|表达意思
---|:--:|
padding：5px|1个值，代表上下左右都有5像素内边距；
padding：5px 10px|2个值，代表上下内边距是5 像素 左右内边距是10像素
padding：5px 10px 20px|3个值，代表上内边距5像素 左右内边距10像素 下内边距20像素
padding：5px 10px 20px 30px|4个值，上是5像素 右10像素 下20像素 左是30像素 顺时针

==顺序为上右下左==

### 1.7 外边距（margin）
margin属性用于设置外边距，即控制盒子和盒子之间的距离
属性|作用
---|:--:|
margin-left|左外边距
margin-right|右外边距
margin-top|上外边距
margin-bottom|下外边距

外边距可以让块级盒子水平居中，但必须满足两个条件：

①盒子必须指定了宽度（width）

②盒子左右的外边距都设置为auto

    .header{width：960px;margin：0 auto；}
    
常见的写法，以下三种都可以：

- margin-left：auto； margin-right：auto
- margin：auto
- margin：0 auto


**行内元素或者行内块元素水平居中给其父元素添加 ==text-align：center== 即可**


### 1.8外边距合并
使用margin定义块元素的垂直外边距时，可能会出现外边距的合并。
#### 1. 相邻块元素垂直外边距的合并
当上下相邻的两个块元素（兄弟关系）相遇时，如果上面的元素有下边距margin-bottom，下面的元素有上外边距margin-top，则他们之间的垂直间距不是margin-bottom与margin-top之和。娶两个值中的较大者这种现象被称为相邻元素垂直外边距的合并。
#### 2. 嵌套块元素垂直外边距的塌陷
对于两个嵌套关系（父子关系）的块元素，父元素有上外边距同事子元素也有上外边距，此时父元素会塌陷较大的外边距值。
#### 解决方案
①可以为父元素定义上边框
②可以为父元素定义上内边距
③可以为父元素添加overflow：hidden
### 1.9 清除内外边距

    *{
        padding：0；（清除内边距）
        margin：0；（清除外边距）
    }
    
注意：行内元素为了照顾兼容性，尽量只设置左右内外边距，不要设置上下内外边距。但是转换为块级和行内块元素就可以了


### 2. 圆角边框（重点）
在CSS3中，新增了圆角边框样式，这样我们的盒子就可以变成圆角了。

**border-radius**属性用于设置元素的外边框圆角

语法：

    border-radius：length（多少PX）；
    
- 参数值可以为数值或百分比的形式
- 如果是正方形，想要设置为一个圆，把数值修改为盖度或者宽度的一半即可，或者直接写50%
- 如果是个矩形，可以跟四个值，分别代表左上角、右上角、右下角、左下角
- 分开写：border-top-left-radius、border-top-right-radius、border-bottom-left-radius、border-bottom-left-radius

### 3. 盒子阴影（重点）
CSS3中新增了盒子阴影，我们可以使用box-shadow属性为盒子添加阴影。

语法：

    box-shadow：h-shadow v-shadow blur spread color inset;
    
值|描述
---|:--:|
h-shadow|必需。水平阴影的位置，允许负值
v-shadow|必需。垂直阴影的位置。允许负值
blur|可选。模糊距离（虚实）
spread|可选。阴影的颜色。请参阅CSS颜色值
inset|可选。将外部阴影（outset）改为内部阴影。
注意：

1.默认的是外阴影（outset）但是不可以写这个单词，否则导致阴影无效**（内阴影：inset）**

2.盒子阴影不占用空间，不会影响其他盒子排列
### 4. 文字阴影
CSS3我们可以使用text-shadow属性为文字添加阴影。

语法：

    text-shadow：h-shadow v-shadow blur spread color inset;
    
值|描述
---|:--:|
h-shadow|必需。水平阴影的位置，允许负值
v-shadow|必需。垂直阴影的位置。允许负值
blur|可选。模糊距离（虚实）
spread|可选。阴影的颜色。请参阅CSS颜色值
