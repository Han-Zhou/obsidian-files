## What is HTTP?
- Hypertext Transfer Protocol (HTTP) is the foundation of the World Wide Web, and is used to load webpages using hypertext links.
- HTTP is an [application layer](https://www.cloudflare.com/learning/ddos/application-layer-ddos-attack/) protocol designed to transfer information between networked devices and runs on top of other layers of the network [protocol](https://www.cloudflare.com/learning/network-layer/what-is-a-protocol/)stack. [[Network Protocol]]
- A typical flow over HTTP involves a client machine making a request to a server, which then sends a response message.


## ## What is in an HTTP request?

- An HTTP request is the way Internet communications platforms such as web browsers ask for the information they need to load a website.

- Contains:
	1. HTTP version type
	2. a URL
	3. an HTTP method
	4. HTTP request headers
	5. Optional HTTP body.


### What is an HTTP method?

- Indicates the action that the HTTP request expects from the queried server.
- 
- For example, two of the most common HTTP methods are ‘GET’ and ‘POST’; a ‘GET’ request expects information back in return (usually in the form of a website), while a ‘POST’ request typically indicates that the client is submitting information to the web server (such as form information, e.g. a submitted username and password).

[[HTTP Request methods]]


### What are HTTP request headers?

- These headers communicate core information, such as what browser the client is using and what data is being requested.
- Contain text information stored in key-value pairs
- 
- Example from Google Chrome's network tab:
- ![[Pasted image 20230615161725.png]]




### What is in an HTTP request body?

- Part that contains the ‘body’ of information the request is transferring.
- The body of an HTTP request contains any information being submitted to the web server, such as a username and password, or any other data entered into a form.




### What is in an HTTP response?

- An HTTP response is what web clients (often browsers) <u>receive from an Internet server in answer to an HTTP request.</u> These responses communicate valuable information based on what was asked for in the HTTP request.

- A typical HTTP response contains:
1. an HTTP status code
2. HTTP response headers
3. optional HTTP body

#### What’s an HTTP status code?
HTTP status codes are 3-digit codes most often used to indicate whether an HTTP request has been successfully completed. Status codes are broken into the following 5 blocks:

1. 1xx Informational
2. 2xx Success
3. 3xx Redirection
4. 4xx Client Error
5. 5xx Server Error

#### What are HTTP response headers?
Headers that convey important information such as the language and format of the data being sent in the response body.

Example of HTTP response headers from Google Chrome's network tab:
![HTTP response headers](https://www.cloudflare.com/img/learning/ddos/glossary/hypertext-transfer-protocol-http/http-response-headers.png "HTTP response headers")


#### What is in an HTTP response body?
Successful HTTP responses to ‘GET’ requests generally have a body which contains the requested information. In most web requests, this is HTML data that a web browser will translate into a webpage.

