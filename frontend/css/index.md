### 记录一些可能遇到的css的面试问题

```text

BFC的规范(block formatting context)

定位方案：

    内部的Box会在垂直方向上一个接一个放置。
    Box垂直方向的距离由margin决定，属于同一个BFC的两个相邻Box的margin会发生重叠。
    每个元素的margin box 的左边，与包含块border box的左边相接触。
    BFC的区域不会与float box重叠。
    BFC是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。
    计算BFC的高度时，浮动元素也会参与计算。

满足下列条件之一就可触发BFC
根元素，即html
    float的值不为none（默认）
    overflow的值不为visible（默认）
    display的值为inline-block、table-cell、table-caption
    position的值为absolute或fixed

```

```text

浏览器是如何解析css选择器的？

```


```text

什么是响应式设计？响应式设计的基本原理是什么？

```

```text

 ::before 和 :after中双冒号和单冒号有什么区别？

```

```text

line-height是如何理解的？

```

```text

让页面里的字体变清晰，变细用CSS怎么做？

```

```text

display:inline-block 什么时候会显示间隙

有空格时候会有间隙 解决：移除空格
margin正值的时候 解决：margin使用负值
使用font-size时候 解决：font-size:0、letter-spacing、word-spacing

```

```text
png、jpg、gif 这些图片格式解释一下，分别什么时候用。有没有了解过webp？
```