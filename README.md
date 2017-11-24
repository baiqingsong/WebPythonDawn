# Python 中web开发

* [web.py的简介](#web.py的简介)
* [web开发基础](#web开发基础)
* [URL映射](#URL映射)
* [请求处理](#请求处理)
* [响应处理](#响应处理)

## web.py的简介
web.py:一个非常轻量级的Python web框架，它简单而且功能强大  
官网[http://webpy.org/](http://webpy.org/)  
安装命令行
```
pip install web.py
```

## web开发基础

## URL映射
URL完全匹配：/index  
URL模糊匹配：/post/\d+  
URL带组匹配：/post/(\d+)  

## 请求处理
请求参数获取：web.input(),get和post都可以  
请求头获取：web.ctx.env  

## 响应处理
html中的地址直接添url映射即可  
模板文件读取：render.index("参数")  
```
render = web.template.render('templates')
```
其中temlates是当前文件同级目录  
调用模板HTML需要放到templates文件夹下  
```
return render.demo()
``` 
可以传递参数，例如：  
```
return render.demo(name)
``` 
模板中首行需要添加,然后可以使用变量  
``` 
$def with(name)
``` 
后面使用name变量需要$name  
同样，如果用到for循环，也要在for前加`$`,并且循环中参数也同样加`$`  
结果数据获取：model.select("sql")  
URL跳转：web.seeother("/"),参数直接天url即可，也可以跳转到外部网站  
