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

