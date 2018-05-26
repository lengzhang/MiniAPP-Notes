# pages

接受一个数组，每一项都是字符串，来指定小程序由哪些页面组成。每一项代表对应页面的【路径+文件名】信息，**数组的第一项代表小程序的初始页面。小程序中新增/减少页面，都需要对 pages 数组进行修改。**

文件名不需要写文件后缀，因为框架会自动去寻找路径下 .json, .js, .wxml, .wxss 四个文件进行整合。

如开发目录为：

 pages

 pages/index/index.wxml
 
 pages/index/index.js
 
 pages/index/index.wxss
 
 pages/logs/logs.wxml
 
 pages/logs/logs.js
 
 app.js
 
 app.json
 
 app.wxss

则需要在 **app.json** 中写

```
{
    "pages":[
        "pages/index/index",
        "pages/logs/logs"
    ]
}
```