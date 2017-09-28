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

### Difference between **margin** and **padding**?
Padding is space between the border and element content. It's inside the element

Margin is space between elements. It's outside the elements. (top and bottom margins are collapsible)

### CSS link
        a:link
        a:visited
        a:hover
        a:active

### CSS overflow
        {
                overflow: hidden; scroll; visible; 
        }
### CSS positioning
* relative
        changes the position of HTML to the element's left
* absolute
        to the screen
* fixed 
        to particular postion
        
### Layers
z index

Javascript
=============
### Session, Cookies and Token






