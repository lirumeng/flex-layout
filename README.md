# flex基础语法介绍

2009年，W3C提出了一种新的方案----`flex`布局，可以简便、完整、响应式地实现各种页面布局。目前，它已经得到了所有浏览器的支持。

![image](imgs/1.jpg)

## flex布局是什么？
`flex`是`flexible box`的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。
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
Webkit内核的浏览器，必须加上`-webkit`前缀:
```css
.box{
  display: -webkit-flex; /* Safari */
  display: flex;
}
```
注意，设为`flex`布局以后，子元素的`float`、`clear`和`vertical-align`属性将失效

## 基本概念
采用`flex`布局的元素，称为`flex`容器（`flex container`），简称"容器"。它的所有子元素自动成为容器成员，称为`flex`项目（`flex item`），简称"项目"。

![image](imgs/2.png)

容器默认存在两根轴：水平的主轴（`main axis`）和垂直的交叉轴（`cross axis`）。主轴的开始位置（与边框的交叉点）叫做`main start`，结束位置叫做`main end`；交叉轴的开始位置叫做`cross start`，结束位置叫做`cross end`。
项目默认沿主轴排列。单个项目占据的主轴空间叫做`main size`，占据的交叉轴空间叫做`cross size`。

## 容器的属性
以下6个属性设置在容器上:
* flex-direction
* flex-wrap
* flex-flow
* justify-content
* align-items
* align-content

### flex-direction属性
`flex-direction`属性决定主轴的方向（即项目的排列方向）
```css
.box {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
![image](imgs/3.png)

它可能有4个值:
* row（默认值）：主轴为水平方向，起点在左端。
* row-reverse：主轴为水平方向，起点在右端。
* column：主轴为垂直方向，起点在上沿。
* column-reverse：主轴为垂直方向，起点在下沿。
### flex-wrap属性
默认情况下，项目都排在一条线（又称"轴线"）上。`flex-wrap`属性定义，如果一条轴线排不下，如何换行。
![image](imgs/4.png)
```css
.box{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```
它可能取三个值:
* nowrap（默认）：不换行。
![image](imgs/5.png)
* wrap：换行，第一行在上方。
![image](imgs/6.jpg)
* wrap-reverse：换行，第一行在下方。
![image](imgs/7.jpg)
### flex-flow属性
flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。
```css
.box {
  flex-flow: <flex-direction> || <flex-wrap>;
}
```