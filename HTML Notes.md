### 1. What happend when accessing a web address?
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

### 2. What is http?
    Hypertext Transfer Protocol(HTTP) is an application protocol, the fundation of data communication for WWW.

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
### 3. What is https?
    Hypertext Transfer Protocol Secure is a communication protocol for secure communication.
    It consist of communication over HTTP with a connection encrypted by **Transport layer security or Secure Socket Layer**
    
    Basically, it's about authentication of visited web site and protection of privacy and integrity of exchange data

### 4. Differences between http and https?
    When communicating using HTTPS, the client and server need to generate a session key while building connection as authentication code.

    Then both side will encrypted the meesage using the key so that no one in between can read it. 

### 5. **Port** for http and https?
    HTTP 80
    HTTP 443

### 6. Difference between **margin** and **padding**?
    Padding is space between the border and element content. It's inside the element

    Margin is space between elements. It's outside the elements. (top and bottom margins are collapsible)

