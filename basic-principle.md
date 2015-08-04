# 基本原则

## 结构、样式、行为分离

尽量确保文档和模板只包含 `HTML` 结构，样式都放到样式表里，行为都放到脚本里。

## 缩进

统一两个空格缩进（总之缩进统一即可），不要使用 Tab 或者 Tab、空格混搭。

## 文件编码

使用不带 `BOM` 的 **UTF-8** 编码。

- 在 HTML 中指定编码`<meta charset="utf-8">`；
- 无需使用`@charset` 指定样式表的编码，它默认为 `UTF-8`（参考 [@charset](https://developer.mozilla.org/en-US/docs/Web/CSS/@charset)）；

## 一律使用小写字母

```
<!-- Recommended -->
<img src="google.png" alt="Google">

<!-- Not recommended -->
<A HREF="/">Home</A>
/* Recommended */
color: #e5e5e5;

/* Not recommended */
color: #E5E5E5;
```

## 省略外链资源 URL 协议部分

省略外链资源（图片及其它媒体资源）URL 中的 `http` / `https` 协议，使 URL 成为相对地址，避免 [Mixed Content](https://developer.mozilla.org/en-US/docs/Security/MixedContent) 问题，减小文件字节数。

其它协议（`ftp` 等）的 **URL** 不省略。

```
<!-- Recommended -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>

<!-- Not recommended -->
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>
/* Recommended */
.example {
  background: url(//www.google.com/images/example);
}

/* Not recommended */
.example {
  background: url(http://www.google.com/images/example);
}
```

## 统一注释

通过配置编辑器，可以提供快捷键来输出一致认可的注释模式。

### HTML 注释

- 模块注释

```
<!-- 文章列表列表模块 -->
<div class="article-list">
...
</div>
```

- 区块注释

```
<!--
@name: Drop Down Menu
@description: Style of top bar drop down menu.
@author: Ashu(Aaaaaashu@gmail.com)
-->
```

### CSS 注释

组件块和子组件块以及声明块之间使用一空行分隔，子组件块之间三空行分隔；

```
/* ==========================================================================
   组件块
 ============================================================================ */

/* 子组件块
 ============================================================================ */
.selector {
  padding: 15px;
  margin-bottom: 15px;
}



/* 子组件块
 ============================================================================ */
.selector-secondary {
  display: block; /* 注释*/
}

.selector-three {
  display: span;
}
```

### JavaScript 注释

##代码验证

- 使用 [W3C HTML Validator](http://validator.w3.org/) 来验证你的 HTML 代码有效性；
- 使用 [W3C CSS Validator](http://jigsaw.w3.org/css-validator/validator.html.zh-cn) 来验证你的 CSS 代码有效性；

代码验证不是最终目的，真的目的在于让开发者在经过多次的这种验证过程后，能够深刻理解到怎样的语法或写法是非标准和不推荐的，即使在某些场景下被迫要使用非标准写法，也可以做到心中有数。