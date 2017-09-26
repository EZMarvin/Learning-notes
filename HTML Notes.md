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
Hypertext Transfer Protocol(HTTP) is an ***stateless*** application protocol, the fundation of data communication for WWW. (stateless for example, send two same request, server won't response it just served the object, it will resend the previous response again) - 不保存用户的信息，发送不带状态，每次请求都要重发

Hypertext is structure text used between nodes containing text, HTTP is the protocol to exchange or transfer hypertext 

- Request message:
        Request line;
        Request header fields;
        Empty line;
        Optional message body;
- Response message:
        Status line include status code and reason message;
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

3XX means Request need send to another server need further action

------
4XX means Client Error request have syntax error or can't fulfilled

5XX means Server Error Server failed to fulfill valid request

### **Port** for http and https?
Port number is a 16 bit number, used to associate with IP address to complete the destination address

HTTP 80
HTTP 443

### Socket?
Socket is nothing but a combination of IP and port. <font color = #DC143C>PORT + IP </font>

HTML PART
=============

### TAG
### Difference between **margin** and **padding**?
Padding is space between the border and element content. It's inside the element

Margin is space between elements. It's outside the elements. (top and bottom margins are collapsible)

------


