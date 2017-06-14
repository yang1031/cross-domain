### 跨域的简单小demo
这是一个关于跨域的简单demo集合，在demo里面会加上自己的理解并添加相应的注释，尽量以简单的demo介绍跨域的方法，适合新手学习跨域的方法。所有demo都是使用基于nodeJs的Web开发框架Express，需要一点点nodeJS的知识，注释里面会详细说明。
> 如果还有其他没提及的跨域方法，欢迎PR，谢谢！

### Set Up
运行环境
- node.js 全局安装
- npm 全局安装

运行步骤
1. cross-domain目录下npm install，下载项目所需的依赖
2. 进入对应的demo目录，①node serverRes.js  ②重新开一个dos窗口   ③node serverReq.js
2. 或者在对应的demo目录下，dos窗口输入`run.bat`，直接一步完成上面的①②③

### 一、CROS跨域

项目运行起来之后，
- 请求数据页面地址： http://localhost:3000/
- 查看数据： http://localhost:3001/

### 二、JSONP跨域

项目运行起来后，
> 请求页面： http://localhost:3000/
> 响应页面为 http://localhost:3001/

### 三、location.hash跨域
在 http://localhost:3000/a.html 使用js动态生成一个隐藏的iframe，设置src属性为' http://localhost:3001/c.html#getdata '，在c.html判断hash值是否为'#getdata'，如果为'#getdata'，则生成一个隐藏的iframe，其src属性指向' http://localhost:3000/b.html '，因为a.html和b.html同源，所以可以在b.html里面修改a.html的hash值，这样a.html就可以通过获取自身的hash值得到数据
> 项目运行地址： http://localhost:3000/a.html

### 四、postMessage跨域
这是html5的新API，适用于不同窗口iframe之间的跨域，

> 项目运行地址： http://localhost:3000/

### 五、后端设置代理proxy跨域
因为JS同源策略是浏览器的安全策略，所以在浏览器客户端不能跨域访问，而服务器端调用HTTP接口只是使用HTTP协议，不会执行JS脚本，不需要同源策略，也就没有跨越问题。

- demo1
通过使用http-proxy-middleware插件设置后端的代理，在 http://localhost:3000/ 运行

- demo2
不使用插件配置代理，直接使用http模块发出请求， 在 http://localhost:3000/ 运行

### 六、window.name跨域
在 http://localhost:3000/a.html 使用js动态生成一个隐藏的iframe，设置src属性为' http://localhost:3001/c.html '，等这个iframe加载完之后，重新设置src属性为同源的地址' http://localhost:3000/b.html '，b.html是一个空的html文件。


> 项目运行地址： http://localhost:3000/a.html


> 还在更新中....
