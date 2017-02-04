# flex基础语法介绍

2009年，W3C提出了一种新的方案----`flex`布局，可以简便、完整、响应式地实现各种页面布局。目前，它已经得到了所有浏览器的支持。

![image](imgs/bg2015071003.jpg)

## flex布局是什么？
`flex是`flexible box`的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。
任何一个容器都可以指定为`flex`布局:
```css
.box{
  display: flex;
}
```
行内元素也可以使用flex布局:
```css
.box {
    display:inline-flex;
}
```
Webkit内核的浏览器，必须加上-webkit前缀:
```css
.box{
  display: -webkit-flex; /* Safari */
  display: flex;
}
```