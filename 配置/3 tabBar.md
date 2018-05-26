# TabBar

如果小程序是一个多 tab 应用（客户端窗口的底部或顶部有 tab 栏可以切换页面），可以通过 tabBar 配置项指定 tab 栏的表现，以及 tab 切换时显示的对应页面。

## **Tip:**

当设置 position 为 top 时，将不会显示 icon
tabBar 中的 list 是一个数组，**只能配置最少2个、最多5个 tab**，tab 按数组的顺序排序。

## 属性说明：

|属性|类型|必选|默认值|描述|
|:-|:-|:-|:-|:-|
|color|HexColor|是||tab 上的文字默认颜色|
|selectedColor|HexColor|是||tab 上的文字选中时的颜色|
|backgroundColor|HexColor|是||tab 的背景颜色|
|borderStyle|String|否|balck|tabBar 上边框颜色，仅支持 balck/white|
|list|Array|是||tab 的列表，详见 list 属性说明，最少2个，最多5个|
|position|String|是|bottom|可选 top/bottom|
||||||

其中 list 接受一个数组，数组中的每个项都是一个对象，其属性值如下：

|属性|类型|必选|描述|
|:-|:-|:-|:-|
|pagePath|String|是|页面路径，必须在 page 先定义|
|text|String|是|tab 上按钮文字|
|iconPath|String|否|图片路径，icon 大小限制为40kb，建议尺寸为 81px * 81px|
|selectedIconPath|String|否|选中时的图片路径，icon 大小限制为40kb，建议尺寸为 81px * 81px|

![TabBar](../images/tabbar.png)

图标资源: [www.iconfont.cn](www.iconfont.cn)