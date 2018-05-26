# networkTimeout

可以设置各种网络请求的超时时间。

**属性说明：**

|属性|类型|必填|说明|
|:-|:-|:-|:-|
|request|Number|否|[wx.request](https://developers.weixin.qq.com/miniprogram/dev/api/network-request.html)的超时时间，单位毫秒，默认为：60000|
|connectSocket|Number|否|[wx.connectSocket](https://developers.weixin.qq.com/miniprogram/dev/api/network-socket.html)的超时时间，单位毫秒，默认为：60000|
|uploadFile|Number|否|[wx.uploadFile](https://developers.weixin.qq.com/miniprogram/dev/api/network-file.html#wxuploadfileobject)的超时时间，单位毫秒，默认为：60000|
|downloadFile|Number|否|[wx.downloadFile](https://developers.weixin.qq.com/miniprogram/dev/api/network-file.html#wxdownloadfileobject)的超时时间，单位毫秒，默认为：60000|
|||||