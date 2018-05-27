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

1. **wxss display(显示)**

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

2. **wxss position(定位)**

    |属性|说明|
    |:-|:-|
    |absolute|生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。|
    |relative|生成相对定位的元素，相对于其正常位置进行定位。因此，"left:20" 会向元素的 LEFT 位置添加 20 像素。|
    |fixed|生成绝对定位的元素，相对于浏览器窗口进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。|
    |static|默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）|
    |inherit|规定应该从父元素继承 position 属性的值|

3. **wxss float(浮动)**

    |属性|说明|
    |:-|:-|
    |left|元素向左浮动|
    |right|元素向右浮动|
    |none默认值|元素不浮动，并会显示在其在文本中出现的位置。|
    |inherit|规定应该从父元素继承 float 属性的值。|

4. **wxss background(背景)**

    |属性|说明|语法(属性值)|
    |:-|:-|:-|
    |background|简写属性，作用是将背景属性设置在一个声明中|background: color position size repeat origin clip attachment image;|
    |background-color|指定要使用的背景颜色|||
    |background-position|指定背景图像的位置|background-position:center|
    |background-size |指定背景图片的大小|background-size:80px 60px;宽度 高度|
    |background-repeat|指定如何重复背景图像|repeat,repeat-x,repeat-y,no-repeat,inherit|
    |background-origin|指定背景图像的定位区域|padding-box 背景图像填充框的相对位置<br>border-box 背景图像边界框的相对位置<br>content-box 背景图像的相对位置的内容框|
    |background-clip|指定背景图像的绘画区域|属性值，同上|
    |background-attachment|设置背景图像是否固定或者随着页面的其余部分滚动。|scroll 背景图片随页面的其余部分滚动。这是默认<br>fixed 背景图像是固定的<br>inherit 指定background-attachment的设置应该从父元素继承<br>local 背景图片随滚动元素滚动|
    |background-image|指定要使用的一个或多个背景图像|url('URL') 图像的URL<br>none 无图像背景会显示。这是默认<br>inherit 指定背景图像应该从父元素继承|

5. **wxss border(边框)**

    |属性|说明|语法(属性值)|
    |:-|:-|:-|
    |border|简写属性，用于把针对四个边的属性设置在一个声明|border:5px solid red;|
    |border-width|用于为元素的所有边框设置宽度，或者单独地为各边边框设置宽度|border-top-width 上右下左边框厚度<br>属性值：<br>thin<br>medium<br>thick|
    |border-style|设置元素所有边框的样式，或者单独地为各边设置边框样式。|border-top-width 上右下左边框样式<br>属性值：<br>none: 默认无边框<br>dotted: 定义一个点线框<br>dashed: 定义一个虚线框<br>solid: 定义实线边界<br>double: 定义两个边界。 两个边界的宽度和border-width的值相同<br>groove: 定义3D沟槽边界。效果取决于边界的颜色值<br>ridge: 定义3D脊边界。效果取决于边界的颜色值<br>inset:定义一个3D的嵌入边框。效果取决于边界的颜色值<br>outset: 定义一个3D突出边框。 效果取决于边界的颜色值|
    |border-color|元素的所有边框中可见部分的颜色，或为 4 个边分别设置颜色|border-top-width 上右下左边框颜色<br>属性值：<br>name - 指定颜色的名称，如 "red"<br>RGB - 指定 RGB 值, 如 "rgb(255,0,0)"<br>Hex - 指定16进制值, 如 "#ff0000"|

6. **wxss 轮廓（outline）**

    |属性|说明|语法(属性值)|
    |:-|:-|:-|
    |outline|在一个声明中设置所有的外边框属性|outline-color<br>outline-style<br>outline-width<br>inherit|
    |outline-color|设置外边框的颜色|color-name<br>hex-number<br>rgb-number<br>invert<br>inherit|
    |outline-style|设置外边框的样式。|none<br>dotted<br>dashed<br>solid<br>double<br>groove<br>ridge<br>inset<br>outset<br>inherit|
    |outline-width|设置外边框的宽度|thin<br>medium<br>thick<br>length<br>inherit|

7. **wxss 文本属性（text）**

    |属性|说明|语法(属性值)|
    |:-|:-|:-|
    |color|设置文本颜色||
    |direction|设置文本方向。|ltr:文本方向从左到右;rtl:文本方向从右到左|
    |letter-spacing|设置字符间距|
    |line-height|设置行高|
    |text-align|对齐元素中的文本|left：把文本排列到左边。默认值，由浏览器决定。<br>right：把文本排列到右边。<br>center：把文本排列到中间。<br>justify：实现两端对齐文本效果。<br>inherit: 规定应该从父元素继承 text-align 属性的值。<br>text-decoration	向文本添加修饰	underline 定义文本下的一条线。<br>overline 定义文本上的一条线。<br>line-through 定义穿过文本下的一条线。<br>blink 定义闪烁的文本。|
    |text-indent|缩进元素中文本的首行||
    |text-shadow|设置文本阴影|text-shadow: h-shadow<br>v-shadow blur color;<br>h-shadow:水平阴影的位置,允许负值;<br>v-shadow:垂直阴影的位置,允许负值;<br>blur:模糊的距离;<br>color:阴影的颜色|
    |text-transform|控制元素中的字母|capitalize 文本中的每个单词以大写字母开头。<br>uppercase 定义仅有大写字母。<br>lowercase 定义无大写字母，仅有小写字母。|
    |unicode-bidi|设置或返回文本是否被重写||
    |vertical-align|设置元素的垂直对齐||
    |white-space|设置元素中空白的处理方式||
    |word-spacing|设置字间距||

8. **wxss 字体属性（font）**

    |属性|说明|语法(属性值)|
    |:-|:-|:-|
    |font|在一个声明中设置所有字体属性|font:font-style font-variant font-weight font-size/line-height font-family(按顺序)|
    |font-style|指定文本的字体样式|normal 默认值。浏览器显示一个标准的字体样式。<br>italic 浏览器会显示一个斜体的字体样式。<br>oblique 浏览器会显示一个倾斜的字体样式。<br>inherit 规定应该从父元素继承字体样式。|
    |font-variant|以小型大写字体或者正常字体显示文本|normal 默认值。浏览器会显示一个标准的字体。<br>small-caps 浏览器会显示小型大写字母的字体。<br>inherit 规定应该从父元素继承 font-variant 属性的值。<br>font-weight	指定字体的粗细	normal 默认值。定义标准的字符。<br>bold 定义粗体字符。<br>bolder 定义更粗的字符。<br>lighter 定义更细的字符。<br>inherit 规定应该从父元素继承字体的粗细。|
    |font-size|指定文本的字体大小|smaller 把 font-size 设置为比父元素更小的尺寸。<br>larger 把 font-size 设置为比父元素更大的尺寸。<br>length 把 font-size 设置为一个固定的值。<br>% 把 font-size 设置为基于父元素的一个百分比值。|
    |font-family|指定文本的字体系列||

9. **wxss margin(外边距)（margin）**

    |属性|说明|语法(属性值)|
    |:-|:-|:-|
    |margin|在一个声明中设置所有外边距属性。|margin:10px 5px 15px 20px;(上边距，右边距，下边距，左边距)|
    |margin-top|设置元素的上外边距。||
    |margin-right|设置元素的右外边距。||
    |margin-bottom|设置元素的下外边距。||
    |margin-left|设置元素的左外边距||

10. **wxss padding(填充)（padding）**

    |属性|说明|语法(属性值)|
    |:-|:-|:-|
    |padding|使用缩写属性设置在一个声明中的所有填充属性|padding:10px 5px 15px 20px;(上填充，右填充，下填充，左填充)|
    |padding-top|设置元素的顶部填充。||
    |padding-right|设置元素的右部填充||
    |padding-bottom|设置元素的底部填充||
    |padding-left|设置元素的左部填充||

**css文档：** http://www.w3cschool.cn/css/css-tutorial.html

**微信小程序文档：** http://www.w3cschool.cn/weixinapp/9wou1q8j.html