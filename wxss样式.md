# wxss样式

WXSS(WeiXin Style Sheets)是一套样式语言，用于描述 WXML 的组件样式。

`WXSS` 用来决定 `WXML` 的组件应该怎么显示。

## 尺寸单位

* rpx（responsive pixel）: 可以根据屏幕宽度进行自适应。规定屏幕宽为750rpx。如在 iPhone6 上，屏幕宽度为375px，共有750个物理像素，则750rpx = 375px = 750物理像素，1rpx = 0.5px = 1物理像素。

    |设备|rpx换算px (屏幕宽度/750)|px换算rpx (750/屏幕宽度)|
    |:-|:-|:-|
    |iPhone5|1rpx = 0.42px|1px = 2.34rpx|
    |iPhone6|1rpx = 0.5px|1px = 2rpx|
    |iPhone6 Plus|1rpx = 0.552px|1px = 1.81rpx|
    ||||

**建议：** 开发微信小程序时设计师可以用 iPhone6 作为视觉稿的标准。

**注意：** 在较小的屏幕上不可避免的会有一些毛刺，请在开发时尽量避免这种情况。

## 样式导入

使用`@import`语句可以导入外联样式表，`@import`后跟需要导入的外联样式表的相对路径，用`;`表示语句结束。

**示例代码：**

```css
/** common.wxss **/
.small-p {
  padding:5px;
}
```

```css
/** app.wxss **/
@import "common.wxss";
.middle-p {
  padding:15px;
}
```

## 内联样式

框架组件上支持使用 style、class 属性来控制组件的样式。

* style：静态的样式统一写到 class 中。style 接收动态的样式，在运行时会进行解析，请尽量避免将静态的样式写进 style 中，以免影响渲染速度。

    ```<view style="color:{{color}};" />```

* class：用于指定样式规则，其属性值是样式规则中类选择器名(样式类名)的集合，样式类名不需要带上.，样式类名之间用空格分隔。

    ```<view class="normal_view" />```

## 选择器

目前支持的选择器有：

|选择器|样例|样例描述|
|:-|:-|:-|
|.class|`.intro`|选择所有拥有 class="intro" 的组件|
|#id|`#firstname`|选择拥有 id="firstname" 的组件|
|element|`view`|选择所有 view 组件|
|element, element|`view, checkbox`|选择所有文档的 view 组件和所有的 checkbox 组件|
|::after|`view::after`|在 view 组件后边插入内容|
|::before|`view::before`|在 view 组件前边插入内容|
||||

## 全局样式与局部样式

app.wxss是全局样式，作用于每一个页面，而page下的每一个的wxss文件只作用于当前页面，并对全局样式中的相同属性会覆盖。

## wxss样式属性

1. wxss display(显示)

    |属性|说明||
    |:-|:-|:-|
    |flex|多栏多列布局||
    |flex-direction|布局方向|row/row-reverse/column/column-reverse|
    |inline-block|行内块元素||
    |inline|此元素会被显示为内联元素，元素前后没有换行符||
    |inline-table|作为内联表格来显示（类似\<table\>），表格前后没有换行符||
    |inline-flex|将对象作为内联块级弹性伸缩盒显示||
    |none|此元素不会被显示||
    |block|此元素将显示为块级元素，此元素前后会带有换行符||
    |list-item|此元素会作为列表显示||
    |table|会作为块级表格来显示（类似 \<table\>），表格前后带有换行符||
    |table-caption|作为一个表格标题显示（类似 \<caption\>）||
    |table-cell|作为一个表格单元格显示（类似 \<td\> 和 \<th\>）||
    |table-column|作为一个单元格列显示（类似 \<col\>）|
    |table-column-group|作为一个或多个列的分组来显示（类似 \<colgroup\>）|
    |table-row|作为一个表格行显示（类似 \<tr\>）|
    |table-row-group|作为一个或多个行的分组来显示（类似 \<tbody\>）|
    |table-header-group|作为一个或多个行的分组来显示（类似 \<thead\>）|
    |table-footer-group|作为一个或多个行的分组来显示（类似 \<tfoot\>）|
    |inherit|从父元素继承 display 属性的值|

**flex:多栏多列布局** http://www.360doc.com/content/14/0811/01/2633_400926000.shtml