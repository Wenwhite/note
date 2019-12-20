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

&ensp;&ensp;&ensp;&ensp;只有 li 元素中的 strong 元素的样式为斜体字，无需为 strong 元素定义特别的 class 或 id。  

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
