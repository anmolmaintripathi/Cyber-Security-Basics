# Client-Server Architecture
Client Server Architecture is a computing model in which the server hosts, delivers and manages most of the resources and services to be consumed by the client.

![CSA](https://cio-wiki.org/wiki/images/3/34/ClientServerArchitecture1.png)


* CLIENT : A **client** is hardware or software which "**sends a request**" to get information / data from the server.

* SERVER : A **server** is also a hardware or software which is reponsible for "**processing the request**" of the client reply.

# How does a client and server interact with each other?
- The client sends an http request to the server and once the server recives an http request from the client, it reponds by sending back and http response back to the client.
- There are different types of http request that can we sent by the client based on the usage and the conditions :
  1. **GET:** The GET method is used to retrieve information from the given server using a given URI. Requests using GET should only retrieve data and should have no other effect on the data. 
  2. **POST:** A POST request is used to send data to the server, for example, customer information, file upload, etc. using HTML forms.
  3. **PUT:** Replaces all current representations of the target resource with the uploaded content.
  4. **DELETE:** Removes all current representations of the target resource given by a URL.
  5. **CONNECT:** Establishes a tunnel to the server identified by a given URL.
  6. **HEAD:** Same as GET, but transfers the status line and header section only.
  7. **OPTIONS:** Describes the communication options for the target resource.
  8. **TRACE:** Performs a message loop-back test along the path to the target resource.
  
FOR IN DETAIL INFORMATION REFER : [HTTP - METHODS](https://www.tutorialspoint.com/http/http_methods.htm)
