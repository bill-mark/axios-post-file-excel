# axios-post-file-excel
axios post方式下载文件

# 导语
当你点进这篇文章说明你的http基础很烂,该去补http的知识了.

  网上搜了一堆肯本就不好使
  
# 直接上干货
例子:点击DIV,下载Excel文件

url地址为:http:www.xxx.com/api/download

参数:id:11,time:2018.9.1
![basic](https://github.com/bill-mark/axios-post-file-excel/blob/master/static/1.png)

1.参数少,不超过浏览器get长度限制

思路:借助a标签的原生功能,写成div嵌套a标签,a标签的href指向URL.

![basic](https://github.com/bill-mark/axios-post-file-excel/blob/master/static/2.png)
![basic](https://github.com/bill-mark/axios-post-file-excel/blob/master/static/3.png)

注意参数的拼接,URL后面跟?,参数之间跟&,记得跨域

2.参数非常多,采用post

多讲一点,文件属于流文件不是json,所以要改响应类型responseType为arraybuffer而不是改header.拿到二进制文件还需要按照服务器响应头的数据类型转换.

第一步:写好请求

![basic](https://github.com/bill-mark/axios-post-file-excel/blob/master/static/4.png/)

第二步:复制接口的response headers的content-type放在上图中type的字符串中

![basic](https://github.com/bill-mark/axios-post-file-excel/blob/master/static/5.png/)
![basic](https://github.com/bill-mark/axios-post-file-excel/blob/master/static/6.png/)

出错排查建议:

1.检测请求的参数是不是json格式

2.后端接口的响应类型是不是文件格式

3.有没有跨域,为了直观教程中写的是完整URL,实际开发是写代理接口的

求个start 谢谢
