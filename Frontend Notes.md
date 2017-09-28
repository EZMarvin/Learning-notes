HTTP
=============
### What happend when accessing a web address?
- client side: 
        1. Browser get URL
        2. Browser check cache to see if the request resources already exist
        3. DNS look up and get IP address

- client to server: 
        1. Wrip http request
        2. Build connection with server using IP address (tcp/IP)
        3. Send http request
        4. Get response
        5. Close the connection

- sercer back to client:
        1. Browser receive response
        2. Check the response to see whether the response is not valid or return error 
        3. Parse the response for display (HTML content and CSS Js rendering)

### What is www
World Wide Web is a network of infomation resources.
- Naming schema for location of resources -> URL
- Protocol for access to resources -> HTTP
- HyperText for easy scan or navigation resources -> HTML

### What is http?
Hypertext Transfer Protocol(HTTP) is an ***stateless*** **application** protocol, the fundation of data communication for WWW. (stateless for example, send two same request, server won't response it just served the object, it will resend the previous response again) - 不保存用户的信息，发送不带状态，每次请求都要重发

Hypertext is structure text used between nodes containing text, HTTP is the protocol to exchange or transfer hypertext 

- Request message:
        Request line (method field, URL, HTTP version);
        Request header fields;
        Empty line;
        Optional message body;
- Response message:
        Status line include protocol version, status code and reason message;
        Response header field;
        Empty line;
        Optional message body;
### What is https?
Hypertext Transfer Protocol Secure is a communication protocol for secure communication.

It consist of communication over HTTP with a connection encrypted by **Transport layer security or Secure Socket Layer**
    
Basically, it's about authentication of visited web site and protection of privacy and integrity of exchange data

### Differences between http and https?
When communicating using HTTPS, the client and server need to generate a session key while building connection as authentication code.

Then both side will encrypted the meesage using the key so that no one in between can read it. 

### Status code 
Used in response message status line

1XX means receive request still processing

2XX means Action successfully received, understood and accepted
        
        200 request receive and return response

3XX means Request need send to another server need further action

        301 move permanently, response new URL

------
4XX means Client Error request have syntax error or can't fulfilled

        400 bad request, don't understood request
        404 not found, request documnet doest not exist

5XX means Server Error Server failed to fulfill valid request

        505 HTTP version not supported

### **Port** for http and https?
Port number is a 16 bit number, used to associate with IP address to complete the destination address

HTTP 80
HTTP 443

### Socket?
Socket is nothing but a combination of IP and port. <font color = #DC143C>PORT + IP </font>

### Persistent and Non-Persistent
how many request/response pair during one TCP connection 

HTML PART
=============
### HTML
HyperText Markup Language, all computer my understand
### HTML 5
2012 support responsive application
<!doctype html>
```html
<html>
  <head>
     <title></title>
  </head>
  <body>
  </body>
</html>
```

### TAG
Tag is reference in HTML which describe the style and structure of document.
```html
        <h1> biggest
        <p>
        <hr> 上加横线
        <div> container
        <ul> <ol>
                <li></li>
        </ul> </ol>
        <br/>

        <span>
        <strong>
        <em>
        <a href = ""></a>

        <table> 
                <tr>
                        <th>header</th>
                </tr>
                <tr>
                        <td></td>
                        <th></th>
                </tr>
        </table>

        <form action= "" method= "POST">
        <intput type="text, password, hidden, checkbox, radio, button, submit, reset" >

        </form>
```

### Inline element and Bolck element
- Block element
        * Always start on a new line
        * Takes up full width available
- Inline element 
        * Not start with new line 
        * Takes up the width as necessary
### Button and Submit difference
submit
* add for form, submit info to address at action

button
* used anywhere, can used to redirect to any link and not restricted to form action

CSS
=============
### CSS
Cascading Style Sheets, how to display
* sparate structure from presentation
* advance control of presentation
* easy maintance
* fast loading

### Attaching
* inline <p style = > perference
* internal < style >
* external < link type ="text/css"  href = "">
* imported CSS < head > <@IMPORT url("") < /head >

### Selector
1. type selector, tag element h1{} p{}
2. class selector, .name {}
3. id selector, #id {}
4. universal selector, * {} all element
5. descendent selector, div p{} <div> <p> 中间可以有其他tag
6. child selector, div > p 必须相邻
7. attribute selector span[lang] {} span[lang = "zh"]{}
### PROPERTY 
* color
* background-color -image **-repeat**:repeat-x -attachment:fixed/scroll
* font -family -style -variant -weight -size -stretch
* text-align word-spacing letter-spacing
* table {border
* margin: up right bottom left
* padding
### Difference between **margin** and **padding**?
Padding is space between the border and element content. It's inside the element

Margin is space between elements. It's outside the elements. (top and bottom margins are collapsible)

### CSS link
        a:link
        a:visited
        a:hover
        a:active
### visibility
        hidden
        visible
        collapse
### CSS overflow
        box content larger than box
        { 
                visible: over the border (default)
                hidden: not showing
                scroll: box size not change, apply scroll
                auto: The auto value is similar to scroll, only it add scrollbars when necessary 
        }

### CSS positioning
* static - is not positioned in any special way
* absolute - is positioned relative to the nearest positioned ancestor
* relative - is positioned relative to its normal position/ element next to
* fixed -  is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled.
* sticky - based on scroll position
        
### Layers
z-index 数字小在下
### pseudo
放置鼠标
### @rules
        @import css file
        @charset character set the style sheet uses
        !important
### rounded corner
        border-radius

Javascript
=============
### advantage
* less server interaction
* fast feedback
* increase interact with user
* rich interfaces

### loading
* head part < sctipt type="text/javascript"> 
* body part < script >
* external files < script type= src="">
### Scope
local value prefer first
### outerloop: for { innerloop for { break innerloop; break outerloop}}
### prompt() alert() write() confirm()
### function name() {} [
        *[name();] 
        *[var object = new function(); var object2 = object();]
        *[var object = function() {};]
### onsubmit (form validation)

### cookies escape()
maintain session information among different pages
### page re-direction
window.location = "url"
### void fun(); javascript: void()
### String
        indexOf() -1
        slice() 克负数
        substr(index, number of char)
        substring(index, endindex) 无负数
        split()
### Array
        var a = new Array(a, b, c);
### DOM 
        window.print() /.onerror()
        documnet.getElementById().

### Closure   
### This
### Session, Cookies and Token
session
  session的中文翻译是“会话”，当用户打开某个web应用时，便与web服务器产生一次session。服务器使用session把用户的信息临时保存在了服务器上，用户离开网站后session会被销毁。这种用户信息存储方式相对cookie来说更安全，可是session有一个缺陷：如果web服务器做了负载均衡，那么下一个操作请求到了另一台服务器的时候session会丢失。
 
cookie
  cookie是保存在本地终端的数据。cookie由服务器生成，发送给浏览器，浏览器把cookie以kv形式保存到某个目录下的文本文件内，下一次请求同一网站时会把该cookie发送给服务器。由于cookie是存在客户端上的，所以浏览器加入了一些限制确保cookie不会被恶意使用，同时不会占据太多磁盘空间，所以每个域的cookie数量是有限的。
     cookie的组成有：名称(key)、值(value)、有效域(domain)、路径(域的路径，一般设置为全局:"\")、失效时间、安全标志(指定后，cookie只有在使用SSL连接时才发送到服务器(https))。下面是一个简单的js使用cookie的例子:
用户登录时产生cookie:
document.cookie = "id="+result.data['id']+"; path=/";
document.cookie = "name="+result.data['name']+"; path=/";
document.cookie = "avatar="+result.data['avatar']+"; path=/";
使用到cookie时做如下解析：
var cookie = document.cookie;var cookieArr = cookie.split(";");var user_info = {};for(var i = 0; i < cookieArr.length; i++) {
    user_info[cookieArr[i].split("=")[0]] = cookieArr[i].split("=")[1];
}
$('#user_name').text(user_info[' name']);
$('#user_avatar').attr("src", user_info[' avatar']);
$('#user_id').val(user_info[' id']);
 
token
     token的意思是“令牌”，是用户身份的验证方式，最简单的token组成:uid(用户唯一的身份标识)、time(当前时间的时间戳)、sign(签名，由token的前几位+盐以哈希算法压缩成一定长的十六进制字符串，可以防止恶意第三方拼接token请求服务器)。还可以把不变的参数也放进token，避免多次查库
 cookie 和session的区别
1、cookie数据存放在客户的浏览器上，session数据放在服务器上。
2、cookie不是很安全，别人可以分析存放在本地的COOKIE并进行COOKIE欺骗
   考虑到安全应当使用session。
3、session会在一定时间内保存在服务器上。当访问增多，会比较占用你服务器的性能
   考虑到减轻服务器性能方面，应当使用COOKIE。
4、单个cookie保存的数据不能超过4K，很多浏览器都限制一个站点最多保存20个cookie。
5、所以个人建议：
   将登陆信息等重要信息存放为SESSION
   其他信息如果需要保留，可以放在COOKIE中
token 和session 的区别
    session 和 oauth token并不矛盾，作为身份认证 token安全性比session好，因为每个请求都有签名还能防止监听以及重放攻击，而session就必须靠链路层来保障通讯安全了。如上所说，如果你需要实现有状态的会话，仍然可以增加session来在服务器端保存一些状态
    App通常用restful api跟server打交道。Rest是stateless的，也就是app不需要像browser那样用cookie来保存session,因此用session token来标示自己就够了，session/state由api server的逻辑处理。 如果你的后端不是stateless的rest api, 那么你可能需要在app里保存session.可以在app里嵌入webkit,用一个隐藏的browser来管理cookie session.
 
   Session 是一种HTTP存储机制，目的是为无状态的HTTP提供的持久机制。所谓Session 认证只是简单的把User 信息存储到Session 里，因为SID 的不可预测性，暂且认为是安全的。这是一种认证手段。 而Token ，如果指的是OAuth Token 或类似的机制的话，提供的是 认证 和 授权 ，认证是针对用户，授权是针对App 。其目的是让 某App有权利访问 某用户 的信息。这里的 Token是唯一的。不可以转移到其它 App上，也不可以转到其它 用户 上。 转过来说Session 。Session只提供一种简单的认证，即有此 SID，即认为有此 User的全部权利。是需要严格保密的，这个数据应该只保存在站方，不应该共享给其它网站或者第三方App。 所以简单来说，如果你的用户数据可能需要和第三方共享，或者允许第三方调用 API 接口，用 Token 。如果永远只是自己的网站，自己的 App，用什么就无所谓了。
  token就是令牌，比如你授权（登录）一个程序时，他就是个依据，判断你是否已经授权该软件；cookie就是写在客户端的一个txt文件，里面包括你登录信息之类的，这样你下次在登录某个网站，就会自动调用cookie自动登录用户名；session和cookie差不多，只是session是写在服务器端的文件，也需要在客户端写入cookie文件，但是文件里是你的浏览器编号.Session的状态是存储在服务器端，客户端只有session id；而Token的状态是存储在客户端。






