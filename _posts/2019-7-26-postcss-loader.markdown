---
layout: post
title:  "postcss-loader配置时需要依赖browserslist"
categories: postcss-loader
tags:  loader
---

## postcss-loader配置时需要依赖browserslist

需要在package.json配置:

{% highlight ruby %}
"browserslist": [
  "> 1%",
  "last 2 versions",
  "not ie <= 8"
]
{% endhighlight %}

或者在文件根目录创建`.browserslistrc`文件

{% highlight ruby %}
"> 1%",
"last 2 versions"
"not ie <= 8"
{% endhighlight %}
