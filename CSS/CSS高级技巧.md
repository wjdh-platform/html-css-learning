## 1. 精灵图
### 1.1 精灵图（sprites）的使用
使用精灵图核心：

1.精灵技术主要针对于背景图片使用。就是把多个小背景图片整合到一张大图片中。

2.这个大图片也称为sprites 精灵图 或者 雪碧图

3.移动背景图片位置，此时可以使用background-position。

4.移动的距离就是这个目标图片的X和Y坐标。注意网页中的坐标有所不同

5.因为一般情况下都是往上往左移动，所以数值是负值。

6.使用精灵图的时候需要精确测量，每个小背景图片的大小和位置。
### 1.2 精灵图的使用
使用精灵图核心总结：

1. 精灵图主要针对于小的背景图片使用
2. 主要借助于背景位置来实现---background-position
3. 一般情况下精灵图都是负值。（千万注意网页中的坐标：X轴右边走是正值，左边走是负值，Y轴下边走是正值，上边走是正值）

## 2.字体图标
## 3. CSS三角

    div{
        width:0;
        height:0;
        line-height:0;
        font-size:0;
        border:50px solid transparent (只设置边框粗细 颜色改成透明)
        border-（要哪个角写哪个角）-left-color：pink；
    }
    
### 4.CSS用户界面样式
#### 4.1 鼠标样式 cursor

    li{ cursor:pointer; }
    
设置或检索在对象上移动的鼠标指针采用何种系统预定义的光标形状。
属性值|描述
---|:--:|
default|小白 默认
pointer|小手
move|移动
text|文本
not-aliiowed|禁止
直接写在行内样式表中
### 4.2 表单轮廓线 outline
给表单添加 outline：0； 或者outline：none；样式之后，就可以去掉默认的蓝色边框。

    input { outline：none；}
    
### 4.3 防止拖拽文本域 resize
实际开发中，我们的文本域右下角是不可以拖拽的。

    textarea{ resize：none;}
    
## 5.vertical-align 属性应用
CSS的vertical-align 属性使用场景：经常用于设置图片或者表单（行内块元素）和文字垂直对齐。

官方解释：用于设置一个元素的==垂直对齐方式==，但是它只针对于行内元素或者行内块元素有效。

语法:

    vertical-align:baseline | top | middle | bottom
    
属性值|描述
---|:--:|
baseline|默认。元素放置在父元素的基线上
top|吧元素的顶端与行中最高元素的顶端对齐
middle|把此元素防止在父元素的中部
bottom|把元素的顶端与行中最低的元素的顶端对齐
### 5.2 解决图片底部默认空白缝隙问题
bug:图片底测会有一个空白缝隙，原因是行内块元素会和文字的基线对齐。主要解决方式有两种：

1. 给图片添加**vertical-align：middle | top | bottom**等（提倡使用的）
2. 把图片转换为块级元素 **display：block**
## 6. 溢出的文字省略号显示
### 6.1 单行文本溢出显示省略号--必须满足三个条件

    /*1. 先强制一行内显示文本*/
    white-space：nowrap; （默认 normal 自动换行）
    /*2. 超出的部分隐藏*/
    overflow：hidden；
    /*3. 文字用省略号替代超出的部分*/
    text-overflow：ellipsis；
    
### 6.2 多行文本溢出显示省略号
多行文本溢出显示省略号，有较大兼容性问题，适合于webkit浏览器或移动端（移动端大部分是webkit内核）

    overflow：hidden
    text-overflow：ellipsis
    /*弹性伸缩盒子模型显示*/
    display：-webkit-box
    /*限制在一个块元素显示的文本的行数*/
    -webkit-line-clamp:2；
    /*设置或检索伸缩盒对象的子元素的排列方式*/
    -webkit-box-orient：vertical；
    
## 7. 常见的布局技巧
### 7.1 margin负值运用
1. 让每个盒子margin往左侧移动 -1px 正好压住相邻盒子边框。
2. 鼠标经过某个盒子的时候，提高当前盒子的层级即可（如果没有定位，则加相对定位（保留位置），如果有定位，则加z-index：1）

### 7.2 文字环绕效果
给盒子加上一个浮动，跟文字不起冲突
### 7.3 行内块巧妙运用
上一页下一页跳转
### 7.4 CSS 三角强化
直角三角形：

    border-bottom（去掉）
    border-top（加大边框数值）
