# Exercise 9

* Create the following folder/file structure:
```
/ex_9
  |-- index.js
```

## index.js
* Create a Express web server using port 3000
* Execute an HTTP request to the server using the browser
* The server will send the following text as response:
```
Congrats you're using your first Node.js and Express as Web Server
```
* When the server starts it needs to show the following message:
```
This HTTP server is running on port %port%
```
* In case there's an error show the following message:
```
Unable to start the server on port %port%
```
* Also update the server listen method to use [logplease module](https://github.com/haadcode/logplease)