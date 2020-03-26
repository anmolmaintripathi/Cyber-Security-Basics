# cURL COMMAND
  * cURL is a computer software project providing a library and command-line tool for transferring data using various network protocols. The name stands for "Client URL"
  
### INSTALLATION OF cURL :
  * cURL can be installed using the following command
  
  ```console
  sudo apt install curl
  ```
  
### Getting started with cURL :
  - Accept Requests send by the server : 
    - In all of the below examples, the request is sent using the 'GET' method of http request and are just focusing on the response we get from the server.
    
    ###### NOTE: cURL command when executed will return the body of the response sent by the server
    ```console
    fiesta@fiesta-VirtualBox:~/Desktop$ curl https://www.example.com
    <!doctype html>
    <html>
    <head>
      <title>Example Domain</title>
      <meta charset="utf-8" />
      <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    ....
    ```
  
    ###### NOTE: '--head' option will display only the head of the response
    ```console
    fiesta@fiesta-VirtualBox:~/Desktop$ curl --head http://www.example.com
    HTTP/1.1 200 OK
    Accept-Ranges: bytes
    Age: 413251
    Cache-Control: max-age=604800
    Content-Type: text/html; charset=UTF-8
    D ate: Tue, 11 Feb 2020 09:55:06 GMT
    Etag: "3147526947"
    Expires: Tue, 18 Feb 2020 09:55:06 GMT
    Last-Modified: Thu, 17 Oct 2019 07:18:26 GMT
    Server: ECS (nyb/1D13)
    X-Cache: HIT
    Content-Length: 1256

    fiesta@fiesta-VirtualBox:~/Desktop$
    ```
    ###### NOTE: '-o' option is used to save the response in a file
    ```console
    fiesta@fiesta-VirtualBox:~/Desktop$ curl -o output.txt http://www.example.com
      % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                     Dload  Upload   Total   Spent    Left  Speed
    100  1256  100  1256    0     0    437      0  0:00:02  0:00:02 --:--:--   437
    fiesta@fiesta-VirtualBox:~/Desktop$ cat output.txt
    <!doctype html>
    <html>
    <head>
        <title>Example Domain</title>
        <meta charset="utf-8" />
        <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    ....
    ```
    
    ###### NOTE: '-O' will download the response file,as in the example it downloads the manual.html file 
    ```console
    fiesta@fiesta-VirtualBox:~/Desktop$ ls
    output.txt
    fiesta@fiesta-VirtualBox:~/Desktop$ curl -O https://curl.haxx.se/docs/manual.html
      % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                     Dload  Upload   Total   Spent    Left  Speed
    100 44194  100 44194    0     0   9781      0  0:00:04  0:00:04 --:--:--  9783
    fiesta@fiesta-VirtualBox:~/Desktop$ ls
    manual.html  output.txt
    fiesta@fiesta-VirtualBox:~/Desktop$ cat manual.html
    <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
    <html>
    <head> <TITLE>curl - Tutorial</TITLE>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta content="text/html; charset=UTF-8" http-equiv="Content-Type">
    <link rel="stylesheet" type="text/css" href="https://curl.haxx.se/curl.css">
    .....
    ```
    ###### NOTE: multiple URLs can we entered in the single commands
    ```console
    fiesta@fiesta-VirtualBox:~$ curl https://www.example.com https://www.google.com
    <!doctype html>
    <html>
        <head> <TITLE>curl - Tutorial</TITLE>
    ..... 
    ```
### Sending POST request :
 - As we have seen previous topic examples, when http requests are sent using 'GET' method, it is used to only to retrieve information from the given server using a given URL. Requests using GET would only retrieve data and should have no other effect on the data stored in the server.
    
  - But when we send the a http request using the 'POST' method, this means that we are trying to send the data from our side i.e client side to the server side for example "search options" or "login information"
    
  #### For example : 
  ![Simple login page](https://wsvincent.com/assets/images/django-user-authentication-tutorial/login.png)
  
  
  ###### Let's consider that the above login page has the following HTML code
  
  ```html
  <form method="POST" action="junk.cgi">
    <h1> Login Page </h1>
    <text>Username:</text>
    <input type=text name="username">
    <text>Password:</text>
    <input type=text name="password">
    <input type=submit name=press value=" Login ">
  </form>
  ```
  
  ###### NOTE : In order to send a 'POST' request we will have to send the values of username and password. We can use the option '--data' in order to send the required data, as shown before. 
  ###### NOTE : 'username' and 'password' is the name for the input box, and these names can be known by seeing the html code of the website.
  
  ```console
  fiesta@fiesta-VirtualBox:~$ curl --data "username=admin&password=admin" http://www.stealmylogin.com/demo.html
  <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
  <html>
  <head>
  
  ....
  ```
  - More on how to use curl to send "POST" request [Link to cURL : POST request](https://curl.haxx.se/docs/httpscripting.html#POST)
  
  
  
- Refer for more: [Link to cURL Documentation](https://curl.haxx.se/docs/httpscripting.html)
- Refer for more: [Link to cURL Options](https://curl.haxx.se/docs/manual.html)
