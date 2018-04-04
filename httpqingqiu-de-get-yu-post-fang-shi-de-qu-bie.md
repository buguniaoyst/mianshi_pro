# HTTP请求的GET与POST方式的区别

---

## 1.HTTP协议

HTTP（即超文本传输协议）是现代网络中最常见和常用的协议之一，设计它的目的是保证客户机和服务器之间的通信。

HTTP 的工作方式是客户机与服务器之间的 “请求-应答” 协议。

客户端可以是 Web 浏览器，服务器端可以是计算机上的某些网络应用程序。

通常情况下，由浏览器向服务器发起 HTTP 请求，服务器向浏览器返回响应。响应包含了请求的状态信息以及可能被请求的内容。

## 2.GET请求

GET请求将请求的参数拼接在URL后面发送的，如：在百度上搜索github之后，会发现github被拼接到url后面发送出去

```
https://www.baidu.com/s?ie=utf-8&f=3&rsv_bp=1&rsv_idx=1&tn=baidu&wd=github
```

GET请求的特点：

* GET 请求可以被缓存

* GET 请求保留在浏览器历史记录中

* GET 请求可被收藏为书签

* GET 请求不应在处理敏感数据时使用（即通常所说的数据不加密）

* GET 请求有长度限制

* GET 请求只应当用于从服务器取回数据

## 3.POST请求

POST请求的参数被包含在请求体中发送：

```
POST https://www.baidu.com HTTP/1.1
Host: baidu.com
name1=value1&name2=value2
```

有关 POST 请求的一些特点：

* POST 请求不会被缓存

* POST 请求不会保留在浏览器历史记录中

* POST 请求不能被收藏为书签

* POST 请求对数据长度没有要求

* POST 请求可以用于处理敏感数据



