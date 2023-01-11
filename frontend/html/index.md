### 记录一些html相关的面试题

1: 关于自定义标签

```text
 
 第一种方式：

 如index.html中的代码所示，加入你随便定义个标签，<goodTag> Chrome浏览器会正常的渲染，只不过没有任何的样式，
 这说明，浏览器对待自定义元素，就像对待标准元素一样，只是没有默认的样式和行为。这种处理方式是写入 HTML5 标准的。

 “User agents must treat elements and attributes that they do not understand as semantically neutral; leaving them in the DOM (for DOM processors), and styling them according to CSS (for CSS processors), but not inferring any meaning from them.”

 上面是标准文档的解释。

 事实上，浏览器提供了一个HTMLUnknownElement对象，所有自定义元素都是该对象的实例，
 var tabs = document.createElement('tabs');
 tabs instanceof HTMLUnknownElement // true
 tabs instanceof HTMLElement // true

 上面代码中，tabs是一个自定义元素，同时继承了HTMLUnknownElement和HTMLElement接口。

```

```text

第二种方式：HTML import
有了自定义元素，就可以写出语义性非常好的 HTML 代码。

<share-buttons>
  <social-button type="weibo">
    <a href="...">weibo</a>
  </social-button>
  <social-button type="weixin">
    <a href="...">wechat</a>
  </social-button>
</share-buttons>

上面的代码，一眼就能看出语义。

如果将<share-buttons>元素的样式与脚本，封装在一个 HTML 文件share-buttons.html之中，这个元素就可以复用了。
先引入share-buttons.html

<link rel="import" href="share-buttons.html"> (只有Chrome支持这个语法)

```
```text

HTML5 标准规定了自定义元素是合法的。然后，W3C 就为自定义元素制定了一个单独的 Custom Elements 标准。

它与其他三个标准放在一起—- HTML Imports，HTML Template、Shadow DOM—-统称为 Web Components 规范。目前，这个规范只有 Chrome 浏览器支持。
Custom Elements 标准对自定义元素的名字做了限制。
“自定义元素的名字必须包含一个破折号（-）所以<x-tags>、<my-element>和<my-awesome-app>都是正确的名字，而<tabs>和<foo_bar>是不正确的。
这样的限制使得 HTML 解析器可以分辨那些是标准元素，哪些是自定义元素。

```

```text

参考资料： https://web.dev/custom-elements-v1/
https://stackoverflow.com/questions/9845011/are-custom-elements-valid-html5


```