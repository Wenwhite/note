# CSS选择器

## 选择器  

### 选择器的分组  

&ensp;&ensp;&ensp;&ensp;对选择器进行分组，被分组的选择器将使用同样的样式声明，案例如下：

``` CSS
h1,h2,h3,h4,h5,h6 {
  color: green;
}
```

&ensp;&ensp;&ensp;&ensp;此时所有标题元素都是绿色。  
  
### 派生选择器  

&ensp;&ensp;&ensp;&ensp;通过依据元素在其位置的上下文关系来定义样式。  
&ensp;&ensp;&ensp;&ensp; ***Eg1:*** 比如，你希望列表中的`strong`元素变为斜体字而不是通常的粗体字，可以定义一个派生选择器如下：

``` CSS
li strong {
  font-style: italic;
  font-weight: normal;
}
```

&ensp;&ensp;&ensp;&ensp;此时，代码效果如下：  

``` HTML
<p>
  <strong>我是粗体字，不是斜体字，因为我不在列表当中，所以这个规则对我不起作用</strong>
</p>

<ol>
  <li>
    <strong>我是斜体字。这是因为 strong 元素位于 li 元素内。</strong>
  </li>
  <li>我是正常的字体。</li>
</ol>
```

&ensp;&ensp;&ensp;&ensp;只有`li`元素中的`strong`元素的样式为斜体字，无需为`strong`元素定义特别的`class`或`id`。  

&ensp;&ensp;&ensp;&ensp; ***Eg2:*** CSS代码如下：  

```CSS
strong {
  color: red;
}

h2 {
  color: red;
}

h2 strong {
  color: blue;
}
```

&ensp;&ensp;&ensp;&ensp;下面是受影响的HTML：  

``` HTML
<p>The strongly emphasized word in this paragraph is
  <strong>red</strong>.
</p>
<h2>This subhead is also red.</h2>
<h2>The strongly emphasized word in this subhead is
  <strong>blue</strong>.
</h2>
```

### ID选择器  

&ensp;&ensp;&ensp;&ensp;id选择器可以为标有特定`id`的HTML元素指定特定的样式。以`#`来定义。  

#### ID选择器和派生选择器

&ensp;&ensp;&ensp;&ensp;id选择器常用于建立派生选择器。如下：

``` CSS
#sidebar p {
  font-style: italic;
  text-align: right;
  margin-top: 0.5em;
}
```

&ensp;&ensp;&ensp;&ensp;上面的样式只会应用于出现在`id`是`sidebar`的元素内的段落。  

##### 一个选择器，多种用法

&ensp;&ensp;&ensp;&ensp;即使被标注为`sidebar`的元素只能在文档中出现一次，这个id选择器作为派生选择器也可以被使用很多次：  

``` CSS
#sidebar p {
  font-style: italic;
  text-align: right;
  margin-top: 0.5em;
}

#sidebar h2 {
  font-size: 1em;
  font-weight: normal;
  font-style: italic;
  margin: 0;
  line-height: 1.5;
  text-align: right;
}
```

&ensp;&ensp;&ensp;&ensp;与其他`p`元素明显不同的是，`sidebar`内的`p`元素得到了特殊的处理，同时，与其他所有`h2`元素明显不同的是，`sidebar`中的`h2`元素也得到了不同的特殊处理。  

#### 单独的选择器

&ensp;&ensp;&ensp;&ensp;id选择器即使不被用来创建派生选择器，它也可以独立发挥作用：  

``` CSS
#sidebar {
  border: 1px dotted #000;
  padding: 10px;
}
```

&ensp;&ensp;&ensp;&ensp;此时，`id`为`sidebar`的元素将拥有一个像素宽的黑色点状边框，同时其周围会有10个像素宽的内边距（`padding`，内部空白）。

### 类选择器  

&ensp;&ensp;&ensp;&ensp;CSS中，类选择器以一个点`.`显示。

``` CSS
.center {
  text-align: center;
}
```

&ensp;&ensp;&ensp;&ensp;效果如下，h1和p元素都有`center`类。这意味着两者都将遵守`.center`选择器中的样式：

``` HTML
<h1 class="center">
This heading will be center-aligned
</h1>

<p class="center">
This paragraph will also be center-aligned.
</p>
```