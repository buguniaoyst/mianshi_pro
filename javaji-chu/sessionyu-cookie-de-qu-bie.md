# Session与Cookie的区别

---

## 1.Session

Session对象存储特定用户会话所需的属性及配置信息。这样，当用户在应用程序的Web页之间跳转时，存储在Session对象中的变量

将不会丢失，而是在整个用户会话中一直存在下去。当用户请求来自应用程序的Web页时，如果该用户还没有会话，则Web服务器将

自动创建一个 Session 对象。当会话过期或被放弃后，服务器将终止该会话。

## 2.Cookie

Cookie意为“甜饼”，是由W3C组织提出，最早由Netscape社区发展的一种机制。Cookie实际上是一小段的文本信息。客户端请求服务

器，如果服务器需要记录该用户状态，就使用response向客户端浏览器颁发一个Cookie。客户端浏览器会把Cookie保存起来。当浏览

器再请求该网站时，浏览器把请求的网址连同该Cookie一同提交给服务器。服务器检查该Cookie，以此来辨认用户状态。服务器还可

以根据需要修改Cookie的内容。Cookie的maxAge决定着Cookie的有效期，单位为秒（Second）。Cookie具有不可跨域名性。

![](https://images.cnblogs.com/cnblogs_com/andy-zhou/811282/o_Cookie_Session002.jpg)

## 3.Cookie与Session的区别 {\#cookie与session的区别}

* cookie数据存放在客户的浏览器上，session数据放在服务器上

* cookie不是很安全，别人可以分析存放在本地的cookie并进行cookie欺骗，考虑到安全应当使用session

* session会在一定时间内保存在服务器上。当访问增多，会比较占用你服务器的性能。考虑到减轻服务器性能方面，应当使用cookie

* 单个cookie在客户端的限制是3K，就是说一个站点在客户端存放的cookie不能超过3K

  


