# 前端html与css笔记

## HTML

### 块元素

块元素是指在页面中单独占一行（自上向下垂直排列），可设置width和height属性，可包含内联和其他块元素

> div、form、h1-h6、hr、p、table、ul等

### 内联元素（行内元素）

内联元素不会独占页面一行，只占自身大小，不能设置width和height属性，可包含内联元素不包含块元素

> a、b、em、i、span、strong等

### 行内块元素

行内块元素不会独占页面一行，但可以设置width和height属性

> button、input、img等

### HTML5的新结构标签

html5新加入的标签有利于seo（在seo中优先于div），结构也相对比div清晰。存在兼容问题（不支持IE8以下）

```html
<header>作为头部容器</header>
<nav>作为导航</nav>
<article>作为内容容器
    <section>部件</section>
</article>
<aside>作为侧内容的容器</aside>
<footer>作为底部内容容器</footer>
```

## CSS

CSS层叠样式表，又叫级联样式表

### 选择器

#### 全局选择器

作用于全局所有标签，但优先级最低，一般作用在初始化样式

```css
*{
    /* 样式 */
}
```

#### 元素选择器

元素标签选择器，这种选择器会作用整个项目所有指定的标签

```css
h1{
    /* 所有h1标签都应用这里的样式 */
}
a{
    /* 所有a标签都应用这里的样式 */
}
```

#### 类选择器

类选择器可被多种标签使用，类名不能以数字开头，同一个标签可使用多个类选择器用空格隔开；优先级高于元素选择器

```css
.classh1{
    /* 样式 */
}
```

```html
<h1 class="classh1">类选择器</h1>
```

#### ID选择器

针对特定的标签来使用，只能使用一次，在`css`中用`#`来定义；优先级高于类选择器

```css
#posw{
    /* 样式 */
}
```

```html
<span id="posw"></span>
```

#### 合并选择器

如果两个或多个样式相同，可以使用合并选择器的方式来减少代码的重复

```css
p,a,h1{
    /* 将p、a、h1标签的样式合并在一起 */
}
```

### 属性

#### 设置颜色

```css
p{
    /* 设置p标签的字体颜色 */
    color: #554040;
}
```

#### 设置字体属性

##### 设置字体大小

```css
p{
    font-size:14px;
}
```

##### 设置字体的粗细

包含的值有加粗`bold`、更粗`bolder`、细体`lighter`以及纯粹的数字从100到900（数字是最常用）

```css
p{

    font-weight:bolder; 
}
```

##### 设置字体样式

可以自定义斜体字

```css
p{
    font-style: italic;
}
```

##### 设置文本字体

可以自定义字体

```css
p{
    font-family: "Microsoft YaHei";;
}
```

#### 设置背景属性

##### 背景颜色

```css
.box{
    background-color: rgb(7, 169, 233);
}
```

##### 设置背景图片

```css
.box{
    background-image: url('../img/1.jpg');
}
```

##### 设置背景图片平铺方式

| 值         | 说明       |
| --------- | -------- |
| repeat    | 默认值      |
| repeat-x  | 只向水平方向平铺 |
| repeat-y  | 只向垂直方向平铺 |
| no-repeat | 不平铺      |

```css
.bos{
    background-repeat: no-repeat;
}
```

##### 设置背景图片大小

| 值          | 说明                                           |
| ---------- | -------------------------------------------- |
| length     | 设置背景图片的宽度和高度，第一个值宽度，第二个值高度，如果只是设置一个，第二个值auto |
| percentage | 计算相对位置区域的百分比，第一个值宽度，第二个值高度，如果只是设置一个，第二个值auto |
| cover      | 保持图片纵横比并将图片缩放成完全覆盖背景区域的最小大小（最常用）（推荐）👍       |
| contain    | 保持图片纵横比并将图像缩放成适合背景定位区域的最大大小                  |

```css
.ba-leng{
    /* length方式 */
    background-size: 120px 60px;
}
.ba-per{
    /* length方式 */
    background-size: 100% 70%;
}
.ba-cov{
    /* cover方式 */
    background-size: cover;
}
.ba-con{
    /* contain方式 */
    background-size: contain;
}
```

##### 设置图片渲染的位置

该属性不能与`background-size`同时生效

| 值             | 说明            |
| ------------- | ------------- |
| left top      | 左上角           |
| left center   | 左中            |
| left bottom   | 左下角           |
| right center  | 右中            |
| right top     | 右上角           |
| right bottom  | 右下角           |
| center bottom | 中下            |
| center top    | 中上            |
| center center | 中中            |
| x% y%         | 按百分比定位起始渲染的位置 |
| xpos ypos     | 按像素单位         |

```css
.ba-pos{
    /* 中中的位置 */
    background-position: center center;
}
```

#### 文本属性

##### 设置文本的水平对齐方式

| 值      | 说明         |
| ------ | ---------- |
| left   | 文本居左位置，默认值 |
| right  | 文本居右位置     |
| center | 文本居中间位置    |

```css
.text-box{
    text-align:center;
}
```

##### 添加文本修饰

| 值            | 说明    |
| ------------ | ----- |
| underline    | 定义下划线 |
| overline     | 定义上划线 |
| line-through | 定义删除线 |

```css
.text-bos{
    text-decoration:overline;
}
```

##### 控制英文文本的大小写

| 值          | 说明   |
| ---------- | ---- |
| capitalize | 开头大写 |
| uppercase  | 全部大写 |
| lowercase  | 全部小写 |

```css
.text-bos{
   text-transform: capitalize;
}
```

##### 设置文本首行缩进

```css
.text-bos{
    text-indent: 2.5rem;
}
```

#### 表格属性

##### 定义表格边框

语法格式：`border: [边框大小] [线的样式] [线的颜色]`

```css
table,td{
    border:1px solid red;
}
```

一般为了表格的边框好看一些，我们需要配合折叠边框使用

```css
table{
    border-collapse:collapse;
}
```

##### 表格文本调整

```css
td{
    /* 设置表格文本对齐方式 */
    text-align: center;
    /* 垂直对齐的方式 */
    vertical-align: top;
}
```

##### 表格填充

能够代替宽高设置将表格拓展起来

```css
td{
    padding: 20px;
}
```

#### 关系选择器

##### 后代选择器

选择器的格式为`[父选择器] [子选择器]{}`

```css
/* 该代码会在dv1-box这个类选择器下的所有h1子标签中生效 */
.dv1-box h1{
    text-align: right;
}
```

##### 子代选择器

作用在父选择器下的直接子选择器（可以理解为一级的子标签），选择器格式`[父选择器]>[子选择器]{}`

例如：

```html
<div>
    <p></p>
    <div>
        <p></p>
    </div>
</div>
```

```css
div>p{
    /*  */
}
```

上面这个例子中所添加的样式只会在第一层div下的第一层p标签中生效，而里面div标签中的p标签则不会生效

##### 相邻兄弟选择器

选择紧跟相邻的同级元素，语法`[选取元素]+[作用元素]{}`

```html
<div>
    <a></a>
    <p class="p-box"></p>
    <span></span><!--该标签会生效-->
    <span></span><!--该标签不会-->
</div>
```

```css
.p-box+span{
    /*  */
}
```

例子中类选择器`p-box`同级且相邻的`span`标签会应用该样式

> 注意相邻兄弟选择器只会向下查找，不会向上查找

```html
<div>
    <a></a>
    <span></span><!--这里并不会被选择器查找到-->
    <p class="p-box"></p>
    <span></span><!--该标签会生效-->
    <span></span><!--该标签不会-->
</div>
```

##### 通用兄弟选择器

所有同级兄弟选择器都会生效，语法`[选取元素]~[作用元素]{}`

```html
<div>
    <a></a>
    <span></span><!--这里并不会被选择器查找到-->
    <p class="p-box"></p>
    <span></span><!--该标签会生效-->
    <a></a>
    <span></span><!--该标签会生效-->
</div>
```

```css
.p-box~span{
    /*  */
}
```

上面例子中哪怕类选择器`p-box`下的兄弟标签`span`中第第二个与第一个隔着`a`标签也依旧会生效

> 注意通用兄弟选择器只会向下查找，不会向上查找

#### 盒子模型

##### 内边距

将盒子内容分为上下左右四个方向间距的空出

| 值              | 说明                                     |
| -------------- | -------------------------------------- |
| padding        | 单值设定上下左右四个方向同时应用，双值设定下第一个值应用上下第二个值应用左右 |
| padding-top    | 上内边距                                   |
| padding-left   | 左内边距                                   |
| padding-right  | 右内边距                                   |
| padding-bottom | 下内边距                                   |

语法：

单值设定，上下左右皆空出10个像素

```css
div{
    padding:10px;
}
```

双值设定，上下按照第一个值空出10个像素，左右按照第二个值空出5个像素

```css
div{
    padding:10px 5px;
}
```

##### 外边距

将盒子外边分为上下左右四个方向间距的空出

| 值             | 说明                                     |
| ------------- | -------------------------------------- |
| margin        | 单值设定上下左右四个方向同时应用，双值设定下第一个值应用上下第二个值应用左右 |
| margin-top    | 上外边距                                   |
| margin-left   | 左外边距                                   |
| margin-right  | 右外边距                                   |
| margin-bottom | 下外边距                                   |

语法基本与外边距差不多

单值设定

```css
div{
    margin:10px;
}
```

同样也有双值设置

```css
div{
    margin:10px 5px;
}
```

#### 弹性盒子模型（css3特性）

弹性盒子是CSS3的新特性，能够更好的帮助我们管理界面的布局

用法：

弹性盒子是通过父元素管理子元素，所以我们需要定义一个父元素将需要管理的盒子放进去

```html
<div class="container">
    <div class="box1"></div>
    <div class="box2"></div>
    <div class="box3"></div>
</div>
```

在父元素中定义样式`display: flex`即可开启弹性盒子

```css
.container {
    background-color: antiquewhite;
    width: 400px;
    height: 300px;
    /* 设置弹性盒子 */
    display: flex;
    /* 设置弹性盒子摆放的方向 */
    flex-direction: row;
    /* 设置弹性盒子的横轴方向的对齐方式 */
    justify-content: flex-end;
    /* 设置弹性盒子的纵轴方向的对齐方式 */
    align-items: center;
}
.box1 {
    width: 100px;
    height: 100px;
    background-color: blue;
}
.box2 {
    width: 100px;
    height: 100px;
    background-color: red;
}
.box3 {
    width: 100px;
    height: 100px;
    background-color: yellow;
}
```

`flex-direction`属性为设置子元素盒子的摆放方向，其中的值有如下：

| 值              | 说明         |
| -------------- | ---------- |
| row            | 横向水平排列，默认值 |
| row-reverse    | 横向水平排列排序反转 |
| column         | 纵向排列摆放     |
| column-reverse | 纵向排列摆放排序反转 |

`justify-content`属性设置弹性盒子的横轴方向上的对齐方式

| 值          | 说明          |
| ---------- | ----------- |
| flex-start | 位于容器的上方，默认值 |
| center     | 位于容器的中间     |
| flex-end   | 位于容器的下方     |

`align-items`属性设置弹性盒子的纵轴方向上的对齐方式

| 值          | 说明          |
| ---------- | ----------- |
| flex-start | 位于容器的上方，默认值 |
| center     | 位于容器的中间     |
| flex-end   | 位于容器的下方     |

##### 子元素上的属性

###### flex-grow/flex

`flex-grow`可以简写成`flex`，根据弹性盒子元素所设置的扩展因子作为比率来分配剩余空间（也就是设置子元素占父元素的空间比率）

默认为0，即如果存在剩余空间，也不放大

```html
<div class="container">
      <div class="box1"></div>
      <div class="box2"></div>
      <div class="box3"></div>
</div>
```

```css
.container {
        background-color: antiquewhite;
        width: 400px;
        height: 500px;
        /* 设置弹性盒子 */
        display: flex;
        /* 设置弹性盒子摆放的方向 */
        flex-direction: row;
        /* 设置弹性盒子的横轴方向的对齐方式 */
        justify-content: center;
        /* 设置弹性盒子的纵轴方向的对齐方式 */
        align-items: center;
      }
      .box1 {
        width: 100px;
        height: 100px;
        background-color: blue;
        flex: 3;
      }
      .box2 {
        width: 100px;
        height: 100px;
        background-color: red;
        flex: 1;
      }
      .box3 {
        width: 100px;
        height: 100px;
        background-color: yellow;
        flex: 1;
      }
```

#### 文档流

文档流的方式摆放标签元素会造成很多问题，如文本的空格只显示一个、高矮不齐，底边对齐等

因此，我们需要脱离文档流的方式来进行页面的开发布局

##### 脱离文档流

使一个元素脱离标准文档流有三种方式：

1. 浮动

2. 绝对定位

3. 固定定位

#### 浮动

`float`属性定义元素在哪个方向浮动，任何元素都可以浮动

| 值     | 说明     |
| ----- | ------ |
| left  | 元素向左浮动 |
| right | 元素向右浮动 |

浮动以后使元素脱离了文档流，浮动只有左右浮动，没有上下浮动

```html
<ul class="ul-box">
      <li>
        <a href=""><span>导航1</span></a>
      </li>
      <li>
        <a href=""><span>导航2</span></a>
      </li>
      <li>
        <a href=""><span>导航3</span></a>
      </li>
      <li>
        <a href=""><span>导航4</span></a>
      </li>
    </ul>
```

```css
.ul-box li {
        /* 设置浮动 */
        float: left;
        margin: 0 0.25rem;
      }
```

#### 清除浮动

浮动在使用的过程中存在着一些副作用，如：

1. 浮动元素会造成父元素高度塌陷

2. 后续元素会受到影响

清除浮动，抵消副作用的方法如下：

##### 1.给父元素设定高度

给父元素设定高度，直接撑开内容

```html
<div class="f-box">
      <div class="s-box"></div>
      <div class="s-box"></div>
      <div class="s-box"></div>
    </div>
    <!--后续的元素受到上面的浮动元素影响-->
<div class="s-box2"></div>
```

```css
.f-box {
        width: 500px;
        /* 清除浮动的方案：给父元素设定高度 */
        height: 500px;
        background-color: #666;
}
.s-box {
        width: 100px;
        height: 100px;
        background-color: aqua;
        margin: 0.5rem;
        float: left;
}
.s-box2 {
        width: 100px;
        height: 100px;
        background-color: rgb(214, 76, 22);
}
```

##### 2.给受影响的元素添加clear属性清除浮动的影响

```html
<div class="f-box">
      <div class="s-box"></div>
      <div class="s-box"></div>
      <div class="s-box"></div>
      <!--后续的元素受到上面的浮动元素影响-->
      <div class="s-box3"></div>
</div>
```

```css
.s-box3 {
        width: 100px;
        height: 100px;
        background-color: rgb(214, 76, 22);
        /* 使用clear属性清除对应浮动的影响 */
        clear: both;
}
```

##### 3.overflow清除浮动（推荐👍）

如果有父级塌陷，并且同级元素也受到了影响，可以使用`overflow`清除浮动

最好与`clear`同时使用

这种情况下，父布局不能设置高度

```html
<div class="f-box">
      <div class="s-box"></div>
      <div class="s-box"></div>
      <div class="s-box"></div>
    <!--后续的元素受到上面的浮动元素影响-->
      <div class="s-box3"><div>
</div>
    <!--后续的元素受到上面的浮动元素影响-->
<div class="s-box2"></div>
```

```css
.f-box {
        width: 500px;
      /* 父元素设定overflow，清除浮动对同级元素的影响 */
        overflow: hidden;
       /* 一般情况下与clear同时使用 */
        clear: both;
        background-color: #666;
}
.s-box {
        width: 100px;
        height: 100px;
        background-color: aqua;
        margin: 0.5rem;
        float: left;
}
.s-box2 {
        width: 100px;
        height: 100px;
        background-color: rgb(214, 76, 22);
        margin: 0.5rem;
     }
.s-box3 {
        width: 100px;
        height: 100px;
        background-color: rgb(214, 76, 22);
        /* 使用clear属性清除对应浮动的影响 */
        clear: both;
}
```

##### 伪对象方式

```html
<div class="f-box">
      <div class="s-box"></div>
      <div class="s-box"></div>
      <div class="s-box"></div>
</div>
    <!--后续的元素受到上面的浮动元素影响-->
<div class="s-box2"></div>
```

```css
.f-box {
        width: 500px;
        background-color: #666;
}
/* 通过伪对象的方式来清除浮动影响 */
.f-box::after {
        content: "";
        display: block;
        clear: both;
}
```

#### 定位

通过设置`position`属性指定元素的定位类型

其中定位类型分为以下几种：

| 值        | 说明   |
| -------- | ---- |
| relative | 相对定位 |
| absolute | 绝对定位 |
| fixed    | 固定定位 |

其中，绝对定位和固定定位会脱离文档流

设置定位后，可以使用四个方向值进行位置调整：`left、top、right、bottom`





#### ul与li标签的属性

将`li`标签中的实心圆点去掉

```css
ul {
        /* 去掉li标签默认的小圆点 */
        list-style-type: none;
      }
```
