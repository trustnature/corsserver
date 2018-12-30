***********简单请求***************
方法为:GET HEAD POST
请求header里面：
a) 无自定义头；
b) Content-Type为以下几种：text/plain 、multipart/form-data、application/x-www-form-urlencoded

**********非简单请求*************
a) PUT DELETE 方法的ajax请求；
b) 发送json格式的ajax请求；
c) 带自定义头的ajax请求；

***********浏览器对不同跨域请求的处理方式**********************
简单请求：浏览器先执行后判断  浏览器发现跨域请求则请求头会自动增加一个参数:
Orgin:http://locahost:8080
非简单请求：浏览器先发送 Request Method:OPTIONS 预检请求，通过后发送真正请求
Access-Control-Allow-Credentials:true
Access-Control-Allow-Headers:content-type
Access-Control-Allow-Methods:*
Access-Control-Allow-Origin:http://localhost:8081
Access-Control-Max-Age:3600

***********解决跨域问题方式*****************************
1、浏览器禁止检查(不推荐)
chrome.exe --disable-web-security --user-data-dir=D:\temp1

2、JSONP(协议约定 若参数包含callback参数 服务器认为是JSONP请求）
弊端：
a) 服务端需要改动
b) 只支持get
c) 发送的不是XHR请求（无法利用XHR特性）

3、被调用者允许（头信息加入参数）
共计5个参数　两个参数固定　　三个动态变化

4、代理（浏览器全是相对地址）
a) nginx 反向代理　　


注意：对于使用Spring 框架的程序来说：
@CrossOrigin  注解在controller上，一个注解全部搞定

附注：教程
https://www.imooc.com/video/16577