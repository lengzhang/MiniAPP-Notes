## app.json

**app.json** 文件用来对微信小程序进行全局配置，决定页面文件的路径、窗口表现、设置网络超时时间、设置多 tab 等。

以下是一个包含了所有配置选项的 **app.json** ：

```
{
    "pages": [
        "pages/index/index",
        "pages/logs/index"
    ],
    "window": {
    "navigationBarTitleText": "Demo"
    },
    "tabBar": {
        "list": [{
        "pagePath": "pages/index/index",
        "text": "首页"
        }, {
        "pagePath": "pages/logs/logs",
        "text": "日志"
        }]
    },
    "networkTimeout": {
        "request": 10000,
        "downloadFile": 10000
    },
    "debug": true
}
```

|属性|类型|必选|描述|
|:-|:-|:-|:-|
|pages|String Array|是|设置页面路径|
|window|Object|否|设置默认页面的窗口表现|
|tabBar|Object|否|设置底部 tab 的表现|
|networkTimeout|Object|否|设置网络超时时间|
|debug|Boolean|否|设置是否开启 debug 模式|
|||||