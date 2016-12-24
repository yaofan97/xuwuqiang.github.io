---
layout: post
title:  "html实体与转义"
subtitle:   "subtitle"
date:   2016-10-25 19:45:06 +0800
author:     "Lockiee"
header-img: "img/6679647_1431413582772_1920x1080.jpg"
header-mask: 0.3
catalog:    true
tags:
    - php
    - 日常小bug
    - html
---
> 客户在后台添加的淘宝链接，传到手机端再打开就提示商品不存在了。



 1. 先查看了一下数据库，里面的链接有些是有```&amp;```这种html实体的。

 2. 用一下
 ```
 htmlspecialchars_decode();
 ```
发现问题解决

## 总结
- 手机端跳浏览器的链接没有将html实体转化为HTML代码。

## 附录
> php函数：
```htmlspecialchars()可以将字符转换成html实体，htmlspecialchars_decode()相反。```


字符     | html实体
-------- | ---
```&```    | ```&amp;```
```"```    | ```&quot;```  ```非(ENT_NOQUOTES)```
```'```    | ```&#039;```  ```(ENT_QUOTES)```
```<```    | ```&lt;```
```>```    | ```&gt;```