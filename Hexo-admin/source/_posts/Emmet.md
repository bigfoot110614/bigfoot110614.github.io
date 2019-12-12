---
title: Emmet
date: 2019-12-11 17:49:46
tags:
    - 工具
---
<font color=red size=3 face="黑体">现在很多代码编辑器都内置了emmet语法, 使我们可以快速生成结构块</font>
### (Emmet)代码快捷方式
官方文档: https://docs.emmet.io

### Nesting operators
#### 1.Child: 子元素 >
##### div>ul>li
```
<div>
    <ul>
        <li></li>
    </ul>
</div>

```

#### 2.Sibling 同级兄弟元素 +
##### div+p+bq
```
<div></div>
<p></p>
<blockquote></blockquote>
```

##### div+div>p>span+em 
...will be expanded to

```
<div></div>
<div>
    <p><span></span><em></em></p>
</div>
```
#### 3. Climb-up 上移一个层级 ^
##### div+div>p>span+em^bq
...outputs to

```
<div></div>
<div>
    <p><span></span><em></em></p>
    <blockquote></blockquote>
</div>
```

##### div+div>p>span+em^^^bq

```
<div></div>
<div>
    <p><span></span><em></em></p>
</div>
<blockquote></blockquote>
```

#### 4.Multiplication: 多个元素 *
##### ul>li*5

```
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

#### 5.Grouping: 分组 ()
##### div>(header>ul>li*2>a)+footer>p
```
<div>
    <header>
        <ul>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
        </ul>
    </header>
    <footer>
        <p></p>
    </footer>
</div>
```

##### (div>dl>(dt+dd)*3)+footer>p

```
<div>
    <dl>
        <dt></dt>
        <dd></dd>
        <dt></dt>
        <dd></dd>
        <dt></dt>
        <dd></dd>
    </dl>
</div>
<footer>
    <p></p>
</footer>
```

### Attribute operators

#### 1.ID and CLASS
##### div#header+div.page+div#footer.class1.class2.class3
```
    <div id="header"></div>
    <div class="page"></div>
    <div id="footer" class="class1 class2 class3"></div>
```

##### td[title="Hello world!" colspan=3]
```
    <td title="Hello world!" colspan="3"></td>
```
##### ul>li.item$*5
```
    <ul>
        <li class="item1"></li>
        <li class="item2"></li>
        <li class="item3"></li>
        <li class="item4"></li>
        <li class="item5"></li>
    </ul>
```

##### ul>li.item$$$*5
```
<ul>
    <li class="item001"></li>
    <li class="item002"></li>
    <li class="item003"></li>
    <li class="item004"></li>
    <li class="item005"></li>
</ul>
```
##### ul>li.item$@-*5

```
    <ul>
        <li class="item5"></li>
        <li class="item4"></li>
        <li class="item3"></li>
        <li class="item2"></li>
        <li class="item1"></li>
    </ul>
```

##### ul>li.item$@3*5

```
    <ul>
        <li class="item3"></li>
        <li class="item4"></li>
        <li class="item5"></li>
        <li class="item6"></li>
        <li class="item7"></li>
    </ul>
```

##### ul>li.item$@-3*5

```
    <ul>
        <li class="item7"></li>
        <li class="item6"></li>
        <li class="item5"></li>
        <li class="item4"></li>
        <li class="item3"></li>
    </ul>
```

##### a{Click me}
```
    <a href="">Click me</a>
```
##### p>{Click }+a{here}+{ to continue}
```
    <p>Click <a href="">here</a> to continue</p>
    In this example, to write Click here to continue inside <p> element we have explicitly move down the tree with > operator after p, but in case of a element we don’t have to, since we need <a> element with here word only, without changing parent context.
```

##### p{Click }+a{here}+{ to continue}

```
    <p>Click </p>
    <a href="">here</a> to continue
```

