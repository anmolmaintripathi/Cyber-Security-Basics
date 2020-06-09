# DNS
- DNS, or Domain Name Service, is used to translate human readable domain names (for example - `www.example.com`) to its machine readable IP Address (for example - `192.0.2.44`)
- Refer this video for more : [What is DNS ?](https://www.youtube.com/watch?v=e2xLV7pCOLI)

### How Does DNS Route Traffic To Your Web Application?

The following diagram gives an overview of how recursive and authoritative DNS services work together to route an end user to your website or application.

![](https://d1.awsstatic.com/Route53/how-route-53-routes-traffic.8d313c7da075c3c7303aaef32e89b5d0b7885e7c.png)

1.  A user opens a web browser, enters `ww.example.com`in the address bar, and presses Enter.
2.  The request for `www.example.com` is routed to a ***DNS resolver***, which is typically managed by the user's Internet service provider (ISP), such as a cable Internet provider, a DSL broadband provider, or a corporate network.
3.  The DNS resolver for the ISP forwards the request for `www.example.com` to a ***DNS root name server***.
4.  The DNS resolver for the ISP forwards the request for `www.example.com` again, this time to one of the ***Top Level Domain (TLD)*** name servers for .com domains. The name server for .com domains responds to the request with the names servers that are associated with the `example.com` domain.
5.  The DNS resolver for the ISP chooses an name server and forwards the request for `www.example.com` to that name server.
6.  The name server looks in the `example.com` hosted zone for the `www.example.com` record, gets the associated value, such as the IP address for a web server, `192.0.2.44`, and returns the IP address to the DNS resolver.
7.  The DNS resolver for the ISP finally has the IP address that the user needs. The resolver returns that value to the web browser. The DNS resolver also caches (stores) the IP address for `example.com` for an amount of time that you specify so that it can respond more quickly the next time someone browses to `example.com`. For more information, see ***`time to live (TTL).`***
8.  The web browser sends a request for `www.example.com` to the IP address that it got from the DNS resolver. This is where your content is, for example, a web server running on an Amazon EC2 instance or an Amazon S3 bucket that's configured as a website endpoint.
9.  The web server or other resource at `192.0.2.44` returns the web page for `www.example.com` to the web browser, and the web browser displays the page.
