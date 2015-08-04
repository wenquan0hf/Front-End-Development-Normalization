# JavaScript

## 通用约定

### 注释

#### 原则

- As short as possible（如无必要，勿增注释）：尽量提高代码本身的清晰性、可读性。
- As long as necessary（如有必要，尽量详尽）：合理的注释、空行排版等，可以让代码更易阅读、更具美感。

#### 单行注释

必须独占一行。`//` 后跟一个空格，缩进与下一行被注释说明的代码一致。

#### 多行注释

避免使用 `/*...*/` 这样的多行注释。有多行注释内容时，使用多个单行注释。

#### 函数/方法注释

- 函数/方法注释必须包含函数说明，有参数和返回值时必须使用注释标识；
- 参数和返回值注释必须包含类型信息和说明；
- 当函数是内部函数，外部不可访问时，可以使用 @inner 标识；

```
/**
 * 函数描述
 *
 * @param {string} p1 参数1的说明
 * @param {string} p2 参数2的说明，比较长
 *     那就换行了.
 * @param {number=} p3 参数3的说明（可选）
 * @return {Object} 返回值描述
 */
function foo(p1, p2, p3) {
    var p3 = p3 || 10;
    return {
        p1: p1,
        p2: p2,
        p3: p3
    };
}
```

#### 文件注释

文件注释用于告诉不熟悉这段代码的读者这个文件中包含哪些东西。应该提供文件的大体内容，它的作者，依赖关系和兼容性信息。如下:

```
/**
 * @fileoverview Description of file, its uses and information
 * about its dependencies.
 * @author user@meizu.com (Firstname Lastname)
 * Copyright 2009 Meizu Inc. All Rights Reserved.
 */
```

### 命名

**变量**，使用 Camel 命名法。

```
var loadingModules = {};
```

**私有属性、变量和方法**以下划线 _ 开头。

```
var _privateMethod = {};
```

**常量**，使用全部字母大写，单词间下划线分隔的命名方式。

```
var HTML_ENTITY = {};
```

1. **函数**，使用 Camel 命名法。
2. 函数的**参数**，使用 Camel 命名法。

```
function stringFormat(source) {}

function hear(theBells) {}
```

1. 类，使用 Pascal 命名法
2. 类的 方法/属性，使用 Camel 命名法

```
function TextNode(value, engine) {
    this.value = value;
    this.engine = engine;
}

TextNode.prototype.clone = function () {
    return this;
};
```

1. **枚举变量**使用 Pascal 命名法。
2. **枚举的属性**，使用全部字母大写，单词间下划线分隔的命名方式。

```
var TargetState = {
    READING: 1,
    READED: 2,
    APPLIED: 3,
    READY: 4
};
```

由多个单词组成的**缩写词**，在命名中，根据当前命名法和出现的位置，所有字母的大小写与首字母的大小写保持一致。

```
function XMLParser() {}

function insertHTML(element, html) {}

var httpRequest = new HTTPRequest();
```

### 命名语法

**类名**，使用名词。

```
function Engine(options) {}
```

**函数名**，使用动宾短语。

```
function getStyle(element) {}
```

**boolean** 类型的变量使用 is 或 has 开头。

```
var isReady = false;
var hasMoreCommands = false;
```

**Promise** 对象用动宾短语的进行时表达。

```
var loadingData = ajax.get('url');
loadingData.then(callback);
```

### 接口命名规范

1. 可读性强，见名晓义；
2. 尽量不与 jQuery 社区已有的习惯冲突；
3. 尽量写全。不用缩写，除非是下面列表中约定的；（变量以表达清楚为目标，uglify 会完成压缩体积工作）

<table>
<tr>
<td><strong>常用词</strong></td>
<td><strong>说明</strong></td>
</tr>
<tr>
<td>options</td>
<td>表示选项，与 jQuery 社区保持一致，不要用 config, opts 等</td>
</tr>
<tr>
<td>active</td>
<td>表示当前，不要用 current 等</td>
</tr>
<tr>
<td>index</td>
<td>表示索引，不要用 idx 等</td>
</tr>
<tr>
<td>trigger</td>
<td>触点元素</td>
</tr>
<tr>
<td>triggerType</td>
<td>触发类型、方式</td>
</tr>
<tr>
<td>context</td>
<td>表示传入的 this 对象</td>
</tr>
<tr>
<td>object</td>
<td>推荐写全，不推荐简写为 o，obj 等</td>
</tr>
<tr>
<td>element</td>
<td>推荐写全，不推荐简写为 el，elem 等</td>
</tr>
<tr>
<td>length</td>
<td>不要写成 len，l</td>
</tr>
<tr>
<td>prev</td>
<td>previous 的缩写</td>
</tr>
<tr>
<td>next</td>
<td>next 下一个</td>
</tr>
<tr>
<td>constructor</td>
<td>不能写成 ctor</td>
</tr>
<tr>
<td>easing</td>
<td>示动画平滑函数</td>
</tr>
<tr>
<td>min</td>
<td>minimize 的缩写</td>
</tr>
<tr>
<td>max</td>
<td>maximize 的缩写</td>
</tr>
<tr>
<td>DOM</td>
<td>不要写成 dom，Dom</td>
</tr>
<tr>
<td>.hbs</td>
<td>使用 hbs 后缀表示模版</td>
</tr>
<tr>
<td>btn</td>
<td>button 的缩写</td>
</tr>
<tr>
<td>link</td>
<td>超链接</td>
</tr>
<tr>
<td>title</td>
<td>主要文本</td>
</tr>
<tr>
<td>img</td>
<td>图片路径（img 标签 src 属性）</td>
</tr>
<tr>
<td>dataset</td>
<td>html5 data-xxx 数据接口</td>
</tr>
<tr>
<td>theme</td>
<td>主题</td>
</tr>
<tr>
<td>className</td>
<td>类名</td>
</tr>
<tr>
<td>classNameSpace</td>
<td>class 命名空间</td>
</tr>
</table>


### True 和 False 布尔表达式

类型检测优先使用 typeof。对象类型检测使用 instanceof。null 或 undefined 的检测使用 == null。

下面的布尔表达式都返回 false:

- null
- undefined
- '' 空字符串
- 0 数字 0

但小心下面的，可都返回 true:

- '0' 字符串 0
- [] 空数组
- {} 空对象

### 不要在 Array 上使用 for-in 循环

for-in 循环只用于 `object/map/hash` 的遍历，对 `Array` 用 for-in 循环有时会出错. 因为它并不是从 0 到 length - 1 进行遍历, 而是所有出现在对象及其原型链的键值。

```
// Not recommended
function printArray(arr) {
  for (var key in arr) {
    print(arr[key]);
  }
}

printArray([0,1,2,3]);  // This works.

var a = new Array(10);
printArray(a);  // This is wrong.

a = document.getElementsByTagName('*');
printArray(a);  // This is wrong.

a = [0,1,2,3];
a.buhu = 'wine';
printArray(a);  // This is wrong again.

a = new Array;
a[3] = 3;
printArray(a);  // This is wrong again.

// Recommended
function printArray(arr) {
  var l = arr.length;
  for (var i = 0; i < l; i++) {
    print(arr[i]);
  }
}
```

### 二元和三元操作符

操作符始终写在前一行，以免分号的隐式插入产生预想不到的问题。

```
var x = a ? b : c;

var y = a ?
    longButSimpleOperandB : longButSimpleOperandC;

var z = a ?
        moreComplicatedB :
        moreComplicatedC;
. 操作符也是如此：

var x = foo.bar().
    doSomething().
    doSomethingElse();
```

### 条件 (三元) 操作符 (?:)

三元操作符用于替代 if 条件判断语句。

```
// Not recommended
if (val != 0) {
  return foo();
} else {
  return bar();
}

// Recommended
return val ? foo() : bar();
```

### && 和 ||

二元布尔操作符是可短路的，只有在必要时才会计算到最后一项。

```
// Not recommended
function foo(opt_win) {
  var win;
  if (opt_win) {
    win = opt_win;
  } else {
    win = window;
  }
  // ...
}

if (node) {
  if (node.kids) {
    if (node.kids[index]) {
      foo(node.kids[index]);
    }
  }
}

// Recommended
function foo(opt_win) {
  var win = opt_win || window;
  // ...
}

var kid = node && node.kids && node.kids[index];
if (kid) {
  foo(kid);
}
```

## jQuery 规范

### Latest jQuery

最新版本的 jQuery 会改进性能和增加新功能，若不是为了兼容旧浏览器，建议使用最新版本的 jQuery。以下是三条常见的 jQuery 语句，版本越新，性能越好：

```
$('.elem')
$('.elem', context)
context.find('.elem')
```

![](images/6.png)

分别使用 1.4.2、1.4.4、1.6.2 三个版本测试浏览器在一秒内能够执行多少次，结果 1.6.2 版执行次数远超两个老版本。

### jQuery Variables

1. 存放 jQuery 对象的变量以 `$` 开头；
2. 将 jQuery 选择器返回的对象缓存到本地变量中复用；
3. 使用驼峰命名变量；

```
var $myDiv = $("#myDiv");
$myDiv.click(function(){...});
```

### Selectors

1. 尽可能的使用 ID 选择器，因为它会调用浏览器原生方法 `document.getElementById` 查找元素。当然直接使用原生 `document.getElementById` 方法性能会更好；
2. 在父元素中选择子元素使用 `.find()`方法性能会更好, 因为 ID 选择器没有使用到 Sizzle 选择器引擎来查找元素；

```
// Not recommended
var $productIds = $("#products .class");

// Recommended
var $productIds = $("#products").find(".class");
```

### DOM Manipulation

1. 当要操作 DOM 元素的时候，尽量将其分离节点，操作结束后，再插入节点；
2. 使用字符串连接或 `array.join` 要比 `.append()`性能更好；

```
var $myList = $("#list-container > ul").detach();
//...a lot of complicated things on $myList
$myList.appendTo("#list-container");
// Not recommended
var $myList = $("#list");
for(var i = 0; i < 10000; i++){
    $myList.append("<li>"+i+"</li>");
}

// Recommended
var $myList = $("#list");
var list = "";
for(var i = 0; i < 10000; i++){
    list += "<li>"+i+"</li>";
}
$myList.html(list);

// Much to recommended
var array = [];
for(var i = 0; i < 10000; i++){
    array[i] = "<li>"+i+"</li>";
}
$myList.html(array.join(''));
```

### Events

1. 如果需要，对事件使用自定义的 `namespace`，这样容易解绑特定的事件，而不会影响到此 DOM 元素的其他事件监听；
2. 对 Ajax 加载的 DOM 元素绑定事件时尽量使用事件委托。事件委托允许在父元素绑定事件，子代元素可以响应事件，也包括 Ajax 加载后添加的子代元素；

```
$("#myLink").on("click.mySpecialClick", myEventHandler);
$("#myLink").unbind("click.mySpecialClick");
// Not recommended
$("#list a").on("click", myClickHandler);

// Recommended
$("#list").on("click", "a", myClickHandler);
```

### 链式写法

1. 尽量使用链式写法而不是用变量缓存或者多次调用选择器方法；
2. 当链式写法超过三次或者因为事件绑定变得复杂后，使用换行和缩进保持代码可读性；

```
$("#myDiv").addClass("error").show();
```

```
$("#myLink")
  .addClass("bold")
  .on("click", myClickHandler)
  .on("mouseover", myMouseOverHandler)
  .show();
```

### Miscellaneous

1. 多个参数使用对象字面量存储；
2. 不要将 CSS 写在 jQuery 里面；
3. 正则表达式仅准用 .test() 和 .exec()。不准用 "string".match()；

### jQuery plug template

```
// jQuery Plugin Boilerplate
// A boilerplate for jumpstarting jQuery plugins development
// version 1.1, May 14th, 2011
// by Stefan Gabos

// remember to change every instance of "pluginName" to the name of your plugin!
(function($) {

    // here we go!
    $.pluginName = function(element, options) {

        // plugin's default options
        // this is private property and is  accessible only from inside the plugin
        var defaults = {

            foo: 'bar',

            // if your plugin is event-driven, you may provide callback capabilities
            // for its events. execute these functions before or after events of your
            // plugin, so that users may customize those particular events without
            // changing the plugin's code
            onFoo: function() {}

        }

        // to avoid confusions, use "plugin" to reference the
        // current instance of the object
        var plugin = this;

        // this will hold the merged default, and user-provided options
        // plugin's properties will be available through this object like:
        // plugin.settings.propertyName from inside the plugin or
        // element.data('pluginName').settings.propertyName from outside the plugin,
        // where "element" is the element the plugin is attached to;
        plugin.settings = {}

        var $element = $(element), // reference to the jQuery version of DOM element
             element = element;    // reference to the actual DOM element

        // the "constructor" method that gets called when the object is created
        plugin.init = function() {

            // the plugin's final properties are the merged default and
            // user-provided options (if any)
            plugin.settings = $.extend({}, defaults, options);

            // code goes here

        }

        // public methods
        // these methods can be called like:
        // plugin.methodName(arg1, arg2, ... argn) from inside the plugin or
        // element.data('pluginName').publicMethod(arg1, arg2, ... argn) from outside
        // the plugin, where "element" is the element the plugin is attached to;

        // a public method. for demonstration purposes only - remove it!
        plugin.foo_public_method = function() {

            // code goes here

        }

        // private methods
        // these methods can be called only from inside the plugin like:
        // methodName(arg1, arg2, ... argn)

        // a private method. for demonstration purposes only - remove it!
        var foo_private_method = function() {

            // code goes here

        }

        // fire up the plugin!
        // call the "constructor" method
        plugin.init();

    }

    // add the plugin to the jQuery.fn object
    $.fn.pluginName = function(options) {

        // iterate through the DOM elements we are attaching the plugin to
        return this.each(function() {

            // if plugin has not already been attached to the element
            if (undefined == $(this).data('pluginName')) {

                // create a new instance of the plugin
                // pass the DOM element and the user-provided options as arguments
                var plugin = new $.pluginName(this, options);

                // in the jQuery version of the element
                // store a reference to the plugin object
                // you can later access the plugin and its methods and properties like
                // element.data('pluginName').publicMethod(arg1, arg2, ... argn) or
                // element.data('pluginName').settings.propertyName
                $(this).data('pluginName', plugin);

            }

        });

    }

})(jQuery);
```

此 jQuery 插件模板出自：[jQuery Plugin Boilerplate, revisited](http://stefangabos.ro/jquery/jquery-plugin-boilerplate-revisited/)。

## 性能优化

### 避免不必要的 DOM 操作

浏览器遍历 DOM 元素的代价是昂贵的。最简单优化 DOM 树查询的方案是，当一个元素出现多次时，将它保存在一个变量中，就避免多次查询 DOM 树了。

```
// Recommended
var myList = "";
var myListHTML = document.getElementById("myList").innerHTML;

for (var i = 0; i < 100; i++) {
  myList += "<span>" + i + "</span>";
}

myListHTML = myList;

// Not recommended
for (var i = 0; i < 100; i++) {
  document.getElementById("myList").innerHTML += "<span>" + i + "</span>";
}
```

### 缓存数组长度

循环无疑是和 JavaScript 性能非常相关的一部分。通过存储数组的长度，可以有效避免每次循环重新计算。

注: 虽然现代浏览器引擎会自动优化这个过程，但是不要忘记还有旧的浏览器。

```
var arr = new Array(1000),
    len, i;
// Recommended - size is calculated only 1 time and then stored
for (i = 0, len = arr.length; i < len; i++) {

}

// Not recommended - size needs to be recalculated 1000 times
for (i = 0; i < arr.length; i++) {

}
```

### 异步加载第三方内容

当你无法保证嵌入第三方内容比如 Youtube 视频或者一个 like/tweet 按钮可以正常工作的时候，你需要考虑用异步加载这些代码，避免阻塞整个页面加载。

```
(function() {

    var script,
        scripts = document.getElementsByTagName('script')[0];

    function load(url) {
      script = document.createElement('script');
      script.async = true;
      script.src = url;
      scripts.parentNode.insertBefore(script, scripts);
    }

    load('//apis.google.com/js/plusone.js');
    load('//platform.twitter.com/widgets.js');
    load('//s.widgetsite.com/widget.js');

}());
```

### 避免使用 jQuery 实现动画

1. 禁止使用 slideUp/Down() fadeIn/fadeOut()等方法；
2. 尽量不使用 animate()方法；