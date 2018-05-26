# page.json

每一个小程序页面也可以使用 **.json** 文件来对本页面的窗口表现进行配置。 页面的配置比 **app.json** 全局配置简单得多，只是设置 app.json 中的 window 配置项的内容，页面中配置项会覆盖 app.json 的 window 中相同的配置项。

页面的 **.json** 只能设置 **window** 相关的配置项，以决定本页面的窗口表现，所以无需写 **window** 这个键，如：

|属性|类型|默认值|描述|
|:-|:-|:-|:-|
|navigationBarBackgroundColor|HexColor|#000000|导航栏背景颜色，如"#000000"|
|navigationBarTextStyle|String|white|导航栏标题颜色，仅支持 black/white|
|navigationBarTitleText|String||导航栏标题文字内容|
|backgroundColor|HexColor|#ffffff|窗口的背景色|
|backgroundTextStyle|String|dark|下拉 loading 的样式，仅支持 dark/light|
|enablePullDownRefresh|Boolean|false|是否开启下拉刷新，详见[页面相关事件处理函数。](https://developers.weixin.qq.com/miniprogram/dev/framework/app-service/page.html#页面相关事件处理函数)|
|disableScroll|Boolean|false|设置为 true 则页面整体不能上下滚动；只在 page.json 中有效，无法在 app.json 中设置该项|
|onReachBottomDistance|Number|50|页面上拉触底事件触发时距页面底部距离，单位为px|
|||||

```
{
    "navigationBarBackgroundColor": "#ffffff",
    "navigationBarTextStyle": "black",
    "navigationBarTitleText": "微信接口功能演示",
    "backgroundColor": "#eeeeee",
    "backgroundTextStyle": "light"
}
```