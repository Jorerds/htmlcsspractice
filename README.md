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

#### 设置文本大小

```css
p{
    font-size:14px;
}
```

#### 设置文本的粗细

包含的值有加粗`bold`、更粗`bolder`、细体`lighter`以及纯粹的数字从100到900（数字是最常用）

```css
p{
    
    font-weight:bolder; 
}
```

#### 设置文本字体样式

可以自定义斜体字

```css
p{
    font-style: italic;
}
```

#### 设置文本字体

可以自定义字体

```css
p{
    font-family: "Microsoft YaHei";;
}
```
