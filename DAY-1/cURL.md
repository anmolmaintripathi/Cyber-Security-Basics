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
    ![curl 1](https://user-images.githubusercontent.com/45136496/77745657-af08dc00-7041-11ea-9aed-db6207bac619.gif)
      
    ###### NOTE: '--head' option will display only the head of the response
    ![curl 2](https://user-images.githubusercontent.com/45136496/77745663-b03a0900-7041-11ea-93a4-ee3155dd7eb5.gif)

    ###### NOTE: '-o' option is used to save the response in a file
    ![curl 3](https://user-images.githubusercontent.com/45136496/77746742-6c480380-7043-11ea-92ff-78d056b1a707.gif)
    
    ###### NOTE: '-O' will download the response file,as in the example it downloads the manual.html file 
    ![curl 4](https://user-images.githubusercontent.com/45136496/77746745-6d793080-7043-11ea-9827-ed7eea8617e4.gif)
    
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
