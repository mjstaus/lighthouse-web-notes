## Intro to HTTP
---
HyperText
- Text that contains links to other texts
- Is the "HT" in HTTP, HTML
- Is a protocol for reading/writing data in a simple text-based way

MDN overview of HTTP: https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview#http_flow

### HTTP Flow
---
- Request/Response based protocol
- Client makes a request to the server, and the server sends a response

### HTTP Requests
---
When client  wants to communicate with a server, it sends a request

Request includes (among other things):
1. Path: What resource the client wants to act on
2. Method: What action the client wants to perform

### HTTP Methods
---
There are 9 HTTP Methods (only going to talk about 4 today)

1. **GET**: Gets data from server
2. **POST**: Create some new data
3. **PUT**: Update some existing data
4. **DELETE**: Delete some data

### Paths and URL Structures
---
URL = Uniform Resource Locator
- Is the address for a given resource on the internet

### Anatomy of a URL

**1. Scheme**
  - Usually http or https
  - Indicates the protocol that brower needs to use for accessing the resource
  - Protocol = method for exchanging or transferring data around a computer network

**2. Authority**
- eg. www.something.com:80
- Includes **domain** (eg. www.something.com) and **port** (eg. :80)
- Port is usually omitted if server uses standard ports of HTTP protocol (80 for HTTP, 443 for HTTPS), otherwise is mandatory

**3. Resource Path**
- eg. /path/to/myfile.html
- Path to the resource on the web server (now usually an abstraction as opposed to an actual server file)

**4. Query Parameters**
- eg. ?key1=value1&key2=value2
- List of key value pairs separated by & symbol
- Web server uses the parameters to do stuff before returning the resource
- Each server has its own rules about how it's handling params

**5. Anchor**
- eg. #SomewhereInTheDocument
- Represents a "bookmark" in the resource, giving directions for the browser to show the content on the bookmarked spot. 

### HTTP Responses
---
When the server receives the request from the user, it reads the path and method to decide what to do. 

It then sends a response to the client, including (among other things):

**1. HTTP Status Codes**

Three digit number sent by the server to let the client know whether the request was successful or not. 

Here are some main ones:
- 200: "Everything went great!"
- 201: "The request has succeeded and a new resource has been created as a result."
- 404: "Resource was not found."
- 500: "The server had an error."

**2. Response Body**
Usually contains some data (like what was requested by the client in the first place)

Data in body may be stored in various formats

### Headers
---
- Can be includied in a request or response
- Way of storing data in the req/res
- Format of key:value pairs

That's all on headers for now, but we'll be coming back to it later




