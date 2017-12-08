# WEB API #

## SOAP ##

Simple Object Access Protocol - XML base

SOAP use different transport protocols (HTTP, SMTP)

WSDL - Web service Description Language (description of the service)

使用Web Service的过程变成，获得该服务的WSDL描述，根据WSDL构造一条格式化的SOAP请求发送给服务器，然后接收一条同样SOAP格式的应答，最后根据先前的WSDL解码数据。绝大多数情况下，请求和应答使用HTTP协议传输，那么发送请求就使用HTTP的POST方法。

## REST ##

Representational State Transfer - architecture pattern for creating an API that users HTTP as underlying communication method

* HTTP is base protocol
* Http serve as platform for building APIs expose service and data

## HTTP detail ##

Request

* Resources - URL - addressable resource to define the structure of API
* Request Verbs - describe what you want to do with resource (GET, POST, PUT, DELETE)
* Request Headers - These are additional instructions with request (type of response or authorization details)
* Request Body - Data sent with the request

Response

* Response Body - Html or data in json XML format
* Response Status codes - issues with response and give the client details on status of request