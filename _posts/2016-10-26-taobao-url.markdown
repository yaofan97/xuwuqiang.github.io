---
layout: post
title:  "html实体坑!"
date:   2016-10-25 19:45:06 +0800
categories: jekyll update
---
> 客户在后台添加的淘宝链接，传到手机端再打开就提示商品不存在了。



 1. 先查看了一下数据库，里面的链接有些是有```&amp;```这种html实体的。

 2. 用一下 
 ```
 htmlspecialchars_decode();
 ```
发现问题解决

### 总结
- 手机端跳浏览器的链接没有将html实体转化为HTML代码。