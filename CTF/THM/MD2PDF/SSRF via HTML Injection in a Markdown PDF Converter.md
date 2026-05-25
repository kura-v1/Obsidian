
A simple challenge where we have to get access to the server, The sever is running an application which converts  md file format to pdf

we launch the machine and then try to access it via the web and it loads up a user interface 

![](Pasted%20image%2020260525115057.png)

then we write something and convert it to pdf.

to see if there are other sub domains in the application we run a ghostbuster scan and we find that there is a admin page, but when we try to access it, it shows an error 

![](Pasted%20image%2020260525115551.png)

we get a forbidden error saying that we can only log in via localhost:5000 

so then we test the website and generate a pdf and  download to check the metadata using the exiftool 

![](Pasted%20image%2020260525115244.png)

here we can see that the creator of the file is wkhtmltopdf, which is the service that is running in the back end of the server, and when we google this we find that 

`wkhtmltopdf` and `wkhtmltoimage` are open source (LGPLv3) command line tools to render HTML into PDF and various image formats using the Qt WebKit rendering engine. These run entirely "headless" and do not require a display or display service.

after that using the iframe tag in html we give the input, 

then using the syntax of the iframe we create the payload and give generate pdf 
![](Pasted%20image%2020260525115423.png)

and boom we get the flag 

![](Pasted%20image%2020260525115812.png)

