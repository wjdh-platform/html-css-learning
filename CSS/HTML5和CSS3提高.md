## HTML5和CSS3提高
### 1.1 HTML5 新增的语义化标签

    <header>：头部标签
    <nav>：导航标签
    <article>：内容标签
    <section>：定义文档某个区域
    <aside>：侧边栏标签
    <footer>：尾部标签
    
**注意：**
- 这种语义化标准主要是针对**搜索引**擎的
- 这些新标签页面中可以**使用多次**
- 在IE9中，需要把这些元素转换为**块级元素**
- 其实，我们移动端更喜欢使用这些标签
- HTML5还增加了很多其他标签，我们后面再慢慢学

### 1.2 HTML5新增的多媒体标签
HTML5在不使用插件的情况下，也可以原生的支持视频格式文件的播放，当然，支持的格式是有限的

#### 1.视频<video>
当前`<video>`元素支持三种视频格式：尽量使用mp4

语法：

    <video src="文件地址" controls="controls"></video>
    
常见属性：
属性|值|描述
---|:--:|---|:--:|
autoplay|autoplay|视频就绪自动播放（谷歌浏览器需要添加muted来解决自动播放的问题）
controls|controls|向用户显示播放控件
width|px(像素)|设置播放器的宽度
height|px(像素)|设置播放器的高度
loop|loop|播放完是否据需播放该视频，循环播放
preload|auto(预先加载视频)    none（不应加载视频）|规定是否预加载视频（如果有了autoplay 就忽略该属性）
src|url|视频url地址
poster|imgurl|加载等待的画面图片
muted|muted|静音播放
### 2.音频 <audio>
当前`<audio>`元素支持三种音频格式：尽量用mp3
语法：

    <audio src="文件地址" controls="controls"></audio>
    
常见属性：
属性|值|描述
---|:--:|---|:--:|
autoplay|autoplay|如果出现该属性，则音频就在绪后马上播放
controls|controls|如果出现该属性，则向用户显示控件，比如播放按钮
loop|loop|如果出现该属性，则每当音频结束时重新开始播放
src|url|要播放的音频的URL
### 3. 多媒体标签总结
- 音频标签和视频标签使用方式基本一致
- 浏览器支持情况不同
- 谷歌浏览器把音频和视频自动播放禁止了
- 我们可以给视频标签添加muted属性来静音播放视频，音频不可以（可以通过JS解决）
- 视频标签是重点，我们经常设置自动播放，不适用controls控件，循环和设置大小属性

### 1.3 HTML5新增的input类型
属性值|说明
---|:--:|---|
 type=“email”| 限制用户输入必须为Email类型
 type=“url”| 限制用户必须输入为URL类型
 type=“date”|限制用户输入必须为日期类型
 type=“time”|限制用户输入必须为时间类型
 type=“month”|限制用户输入必须为月类型
 type=“week”|限制用户输入必须为周类型
 type=“number”|限制用户输入必须为数字类型
 type=“tel”|手机号码
 type=“search”|搜索框
 type=“color”|生成一个颜色选择表单
 - 重点记住：number  tel   search   这三个
 
 ### 1.4 HTML5 新增的表单属性
属性|值|说明
---|:--:|---|
required|required|表单拥有该属性表示其内容不能为空，必填写
**placeholder**|提示文本|表单的提示信息，存在默认值将不显示
autofocus|autofocus|自动聚焦属性，页面加载完成自动聚焦到指定表单
autocomplete|off/on|当用户在字段开始键入时，浏览器基于之前键入过得值，应该显示出在字段中填写的选项。   默认已经打开，如autocomplete=“on”,关闭autocomplete=“off” 需要放在表单内，同时加上name属性，同时成功提交
**multiple**|multiple|可以多选文件提交

可以通过一下设置方式修改placeholder里面的字体颜色：

`input::placeholder{
    color:pink;
}`
# 2.CSS3的新特性
- 新增的CSS3特性有兼容性问题，IE9+才支持
- 移动端支持优于PC端
- 不断改进中
- 应用相对广泛
- 现阶段主要学习：**新增选择器**和**盒子模型**以及**其他特性**
### 2.1 属性选择器
属性选择器可以根据元素特定属性来选择元素。这样就可以不用借助于类或者id选择器。
选择符|简介|
---|:--:|---|
E[att]|选择具有att属性的E元素
E[att="val"]|选择具有att属性且属性值等于val的E元素
E[att^="val"]|匹配具有att属性且值以val开头的E元素
E[att$="val"]|匹配具有att属性且值以val结尾的E元素
E[att*="val"]|匹配具有att属性且值中那个含有val的E元素
### 2.2 结构伪类选择器
结构伪类选择器主要根据文档结构来选择器元素，常用于根据父级选择器里面的子元素
选择符|简介|
---|:--:|---|
E:first-child|匹配父元素中的第一个子元素E
E:last-child|匹配父元素中的最后一个E元素
E:nth-child(n)|匹配父元素中的第n个子元素E
E:first-of-type|指定类型E的第一个
E:last-of-type|指定类型E的最后一个
E:nth-of-type(n)|指定类型E的第n个

#### nth-child（n）选择某个父元素的一个或多个特定的子元素
- n可以是数字，关键字和公式
- n如果是数字，就是选择第n个子元素，里面数字从1开始……
- n可以是关键字：even偶数，odd奇数
- n可以是公式：常见的公式如下（如果n是公式，则从0开始计算，但是第0个元素或者超出了元素的个数会被忽略）

公式|取值|
---|:--:|---|
2n|偶数
2n+1|奇数
5n|5  10  15 ......
n+5|从第5个开始（包含第五个）到最后
-n+5|前5个（包含第5个）
区别：
1. nth-child对父元素里面所有孩子排序选择（序号是固定的）先找到第n个孩子，然后看看是否和E匹配。
2. nth-of-type对父元素里面指定子元素进行排序选择，先去匹配E，然后再根据E找第n个孩子

#### 小结
- 结构伪类选择器一般用于选择父级里面的第几个孩子
- nth-child对父元素里面所有孩子排序选择（序号是固定的）先找到第n个孩子，然后看看是都和E匹配
- nth-of-type对父元素里面指定子元素进行排序选择。先去匹配E，然后再根据E找第n个孩子
- 关于nth-child（n）我们要知道n是从0开始计算的，要记住常用的公式
- 如果是无序列表，我们肯定用nth-child更多
- 类选择器、属性选择器、伪类选择器权重为10
### 2.3 伪元素选择器（重点）
伪元素选择器可以帮助我们利用CSS创建新标签元素，而不需要HTML标签，从而简化HTML结构
选择符|简介|
---|:--:|---|
::before|在元素内部的前面插入内容
::after|在元素内部的后面插入内容

**注意：**
- before和after创建一个元素，但是属于行内元素
- 新创建的这个元素在文档树中是找不到的，所以我们称为伪元素
- **语法`·element::before{}`**
- before和after必须有content属性
- before在父元素内容的前面创建元素，after在父元素内容的后面插入元素
- 伪元素选择器和标签选择器一样，权重为1

### 2.4 CSS的盒子模型
CSS3中可以通过`<box-sizing>`来指定盒模型，有两个值：即可指定为`<content-box>`、`boeder-box`，这样我们计算盒子大小的方式就发生了改变。

可以分成两种情况：
1. box-sizing：content-box 盒子大小为width+padding+border(以前默认的)
2. box-sizing:border-box 盒子大小为width

如果盒子模型我们改为了box-sizing：border-box，那padding和border就不会撑大盒子了（前提padding和border不会超过width宽度）

### 2.5 CSS3其他特性（了解）

#### CSS3滤镜filter：
filter CSS属性将模糊或颜色偏移等图形效果应用于元素。

    filter：函数(); 例如：filter：blue(5px); blur模糊处理 数值越大越模糊
    
#### CSS3 calc函数：
calc()此CSS函数让你在声明CSS属性值时执行一些计算

    width：calc(100%-80px);
    
括号里面可以使用 + - * / 来进行计算
    
#### CSS3 过渡（重点）
过渡动画：是从一个状态 渐渐地过渡到另外一个状态

可以让我们页面更好看，更动感十足，经常和：hover一起搭配使用

    transition：要过渡的属性 花费时间 运动曲线 何时开始；
    
1. **属性** ：想要变化的css属性，宽度高度 背景颜色 内外边距 都可以。如果想要所有的属性都变化过渡，写一个 all 就可以
2. **花费时间** ：单位是 秒 （必须写单位） 比如 0.5s
3. **运动曲线** ：默认是 edse（可以省略）
4. **何时开始** ：单位是 秒（必须写单位）可以设置延迟触发时间 默认是0s（可以省略）

### 3. CSS3  2D转换
转换（transform）是CSS3中具有颠覆性的特征之一，可以实现元素的位移、旋转、缩放等效果。
- 移动：translate
- 旋转：rotate
- 缩放：scale

#### 3.1 二维坐标系
2D转换是改变标签在二维平面上的位置和形状的一种技术，先来学习二维坐标系
#### 3.2 2D转换之移动 translate
2D移动是2D转换里面的一种功能，可以改变元素在页面中的位置，类似定位。

##### 1.语法
    
    transform：translate（x,y）；或者分开写
    transform：translateX（n）；
    transform：translateY（n）；
    
##### 2.重点
- 定义2D转换中的移动，沿着X和Y轴移动元素
- translate最大的优点：不会影响到其他元素的位置
- translate中的百分比单位是相对于自身元素的translate：（50%，50%）
- 对行内标签没有效果

 #### 3.3 转换之旋转 rotate
 2D旋转指的是让元素在2维平面内顺时针旋转或者逆时针旋转
 
##### 1.语法
 
    transform：rotate（度数）
    
##### 2.重点
- rotate里面跟度数，单位是deg 比如 rotate（45deg）
- 角度为正时，顺时针，负时，为逆时针
- 默认旋转的中心点是元素的中心点

#### 3.4 2D转换中心点 transform-origin
我们可以设置元素转换的中心点
##### 1. 语法

    transform-origin：x y；
    
##### 2.重点
- 注意后面的参数 x 和 y 用空格隔开
- x y默认转换的中心点是元素的中心点（50% 50%）
- 还可以给x y 设置像素或者方位名词 （top bottom left right center）

#### 3.5 2D转换之缩放scale
缩放，顾名思义，可以放大和缩小。只要给元素添加上了这个属性就能控制它放大还是缩小
##### 1. 语法

    transform：scale（X,Y）；
    
##### 2.注意
- 注意其中的x和y用逗号分隔
- transform：scale（1,1）：宽和高都放大了一倍，相当于没有放大
- transform：scale（2,2）：宽和高都放大了2倍
- transform：scale（2）：只写一个参数，第二个参数则和第一个参数一样，相当于scale（2,2）
- transform：scale（0.5,0.5）：缩小
- scale缩放最大的优势：可以设置转换中心点缩放，默认以中心点缩放的，而且不影响其他盒子

#### 3.6 2D转换综合写法
##### 注意
 1. 当我们使用多个转换，其格式为：transform：translate（） rotate（）scale（）...等。（中间用==空格隔开==）
 2. 其顺序会影响转换的效果。（先旋转会改变坐标轴方向）
 3. **当我们同时有位移和其他属性的时候，记得要将位移放到最前。**

#### 3.7 2D转换总结
- 转换transform 我们简单理解就是变形 有2D 和3D之分
- 我们暂且学了三个 分别是位移 旋转和缩放
- 2D旋转rotate（度数） 可以实现旋转元素 度数的单位是deg
- 2D缩放scale（x,y）里面参数是数字 不跟单位 可以是小数 最大的优势 不影响其他盒子
- 设置转换中心点 transform-origin：x y； 参数可以百分比、像素或者是方位名词
- 当我们进行综合写法，同时有位移和其他属性的时候，记得要将位移放到最前面

### 4.动画
动画（animation）是CSS3中具有颠覆性的特性之一，可通过设置多个节点来精确控制一个或一组动画，常用来实现复杂的动画效果。
相比较过渡，动画可以实现更多变化，更多控制，连续自动播放等效果。
#### 4.1 制作动画的步骤
##### 一、用keyframes定义动画（类似定义类选择器）

    @keyframes 动画名称 {
        0%{
            width：100px;
        }
        100%{
            width：200px
        }
    }
    
##### 二、元素调用这个动画

    div{
        width：200px;
        height:200px;
        background-color:pink;
        margin:100px auto;
        <!--调用动画-->
        animation-name:动画名称；
        <!--持续时间-->
        animation-duration:持续时间；
    }
    

##### 动画序列
- 0%是动画的开始，100%是动画的完成。这样的规则就是动画序列
- 在@keyframes中规定某项CSS样式，就能创建由当前样式逐渐改为新样式的动画效果
- 动画是使元素从一种样式逐渐变化为另一种样式的效果。您可以改变任意多的样式任意多的次数
- 请用百分比来规定变化发生的时间，或用关键词 “from” 和 “to”，等同于 0% 和 100%

#### 4.2 动画常用属性
选属性|描述|
---|:--:|---|
@keyframes|规定动画
animation|所有动画属性的简写属性，除了animation-play-state属性
animation-name|规定@keyframes动画的名称（必须的）
animation-duration|规定动画完成一个周期所花费的秒或毫秒，默认是0（必须的）
animation-timing-function|规定动画的速度曲线，默认是“ease”
animation-delay|规定动画何时开始，默认是0
animation-iteration-count|规定动画被播放的次数，默认是1，还有infinite
animation-direction|规定动画是否在下一周期逆向播放，默认是“normal”，“alternate”逆播放
animation-play-state|规定动画是否正在运行或暂停。默认是“running”，还有“paused”
animation-fill-mode|规定动画结束后状态，保持forward回到起始backwards

#### 4.3 动画简写属性
animation：动画名称 持续时间 运动曲线 何时开始 播放次数 是否反方向 动画起始或者结束的状态；

    animation： move 5s linear infinite alternate;
    
- 简写属性里面不包括 animation-play-state
- 暂停动画：animation-play-state：puased; 经常和鼠标经过等其他配合使用
- 想要动画走回来，而不是直接跳回来：animation-direction：alternate
- 盒子动画结束后，停在结束位置：animation-fill-mode：forwards

#### 4.4 速度曲线细节
animation-timing-function：规定动画的速度曲线，默认是“ease”
值|描述|
---|:--:|---|
linear|动画从头到尾的速度是相同的。匀速
ease|默认 动画以低速开始，然后加快，在结束前变慢
ease-in|动画以低速开始
ease-out|动画以低速结束
ease-in-out|动画以低俗开始和结束
steps()|指定了时间函数中的间隔数量（步长）
### 5. 3D转换
#### 5.1 三维坐标系
三维坐标系其实就是指立体空间，立体空间是由3个轴共同组成的

- x轴：水平向右  ==注意：x右边是正值，左边是负值==
- y轴：垂直向下  ==注意：y下面是正值，上面是负值==
- z轴：垂直屏幕  ==注意：往外面是正值，往里面是负值==

#### 5.2 3D移动 translate3D
3D移动在2D移动的基础上多加了一个可以移动的方向，就是Z轴方向

- translform:translateX(100px):仅仅是在X轴上移动
- translform:translateY(100px):仅仅是在Y轴上移动
- translform:translateZ(100px):仅仅是在Z轴上移动 ( 注意：translateZ一般用px单位)
- translform:translate3d:其中x、y、z分别指要移动的轴的方向的距离

#### 5.3 透视 perspective
在2D平面产生近大远小视觉立体，但是只是效果二维的

- 如果想要在网页产生3D效果需要透视（理解成3D物体投影在2D平面内）
- 模拟人类的视觉位置，可认为安排一只眼睛去看
- 透视我们也称为视距：视距就是人的眼睛到屏幕的距离
- 距离视距点越近的在电脑平面成像越大，越远成像越小
- 透视的单位是像素

##### 透视写在被观察元素的父盒子上面的
 d : 就是视距，视距就是一个局里人的眼睛到屏幕的距离。
 
 z : 就是z轴，物体距离屏幕的距离，z轴越大（正值）我们看到的物体就越大
 
#### 5.4 3D旋转 rotate3d
3D旋转指可以让元素在三维平面内沿着x轴，y轴，z轴或者自定义轴进行旋转

##### 语法
- transform：rotateX（45deg）:沿着x轴正方向旋转45度
- transform：rotateY（45deg）:沿着y轴正方向旋转45度
- transform：rotateZ（45deg）:沿着z轴正方向旋转45度
- transform：rotate3d（x,y,z,deg）:沿着自定义轴旋转deg为角度（了解即可）

#### 5.5 3D呈现 transform-style
- 控制子元素是否开启三维立体环境
- transform-style:flat子元素不开启3d立体空间 默认的
- transform-style：preserve-3d；子元素开启立体空间
- 代码写给父级，但是影响的是子盒子
- 这个属性很重要，后面必用

### 6.浏览器私有前缀
浏览器私有前缀是为了兼容老版本的写法，比较新版本的浏览器无须添加。

#### 6.1 私有前缀
- -moz-：代表firefox 浏览器私有属性
- -ms-：代表IE 浏览器私有属性
- -webkit-：代表Safari、Chrome私有属性
- -o-：代表Opera私有属性

#### 6.2 提倡的写法

    -moz-border-radius:10px;
    -webkit-border-radius:10px;
    -o-border-radius:10px;
    border-radius:10px;
    
