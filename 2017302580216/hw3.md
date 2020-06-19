**1、telnet whu.edu.cn 25**
```
执行telnet whu.edu.cn 25
输入 ehlo 发送端主机名
输入 auth login 登陆邮箱，并输入base64后的用户名和密码
依次输入发送者和接受者邮箱
输入DATA命令，开始输入邮件内容
按照格式输入后以<CR><CF>.<CR><CF>结束，并发送邮件。
输入quit关闭连接
```
!(1.png)
**2、telnet maths.whu.edu.cn 80**
```
执行 telnet maths.whu.edu.cn 80
构造HTTP报文，并发送

GET /index.htm HTTP/1.1\r\n
Host:maths.whu.edu.cn\r\n
\r\n

收到服务器响应内容。
```
!(2.png)

## 课后习题  
### p1:  
(1)错误，客户端会发送四个请求，文本与三幅图像各一个请求，并且接收四个响应。  
(2)正确。持续连接可以供两个不同web页面使用  
(3)错误。使用非持续连接时，每次一个TCP报文只能携带一个HTTP服务请求报文  
(4)错误。HTTP响应报文的Data中包含的是所请求页面的数据信息。  
(5)错误。存在空的响应报文体。  
### p3:  
在应用层还需要DNS的参与，需要利用DNS将域名解析为对应的IP地址。在传输层需要TCP协议或UDP协议的参与来传输数据请求等。  
### p4: 
a:gaia/cs/umass/edu/cs453/index.html。第一行首部中包含  
b:1.1 。根据HTTP/1.1  
c:是一条持续的连接，由于存在保持连接keep-alive的信息;Connection:keep-alive  
d:报文中未包含运行主机的IP地址.  
e:浏览器类型为Mozilla/5.0。由于服务器可以可以针对不同的浏览器发送不同版本的网页。  
### p5: 
a:浏览器成功找到了那个文档。根据Date: Tue所得。回答的时间为响应浏览器的时间07 Mar 2008  
b:最后修改时间为Sat, 10 Dec 2005 18:27:46 GMT。根据Last-Modified的值而得  
c:被返回的字节为3874，根据Content-Length所得  
d:前五个字节为<!doc，服务器同意一条持续连接根据keep-alive可看出  
