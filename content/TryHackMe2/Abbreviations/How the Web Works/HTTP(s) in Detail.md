**What is HTTP(s)?

- What is HTTP? (HyperText Transfer Protocol)
	- Used whenever you visit a website.
	- Set of rules used for communicating with web servers
	- Transmits webpage data (HTML, Videos, Images ect)
	- Developed Tim Berners-Lee and his team between 1989-1991.

- What is HTTPS? (Hypertext Transfer Protocol Secure)
	- Secure version of HTTP
	- HTTPS data is encrypted
		- Stops people from seeing data you are sending and receiving
		- Gives assurance you're talking to the correct web server and not an impersonation.

**Requests and Responses

- What is a URL (Uniform Resource Locator)? 
	- An instruction of how to access a resource on the internet
	- Makes request to web servers for assets
		- HTML, images ect
	- Example of a URL:
		- ![[Pasted image 20241111074916.png]]
		- Scheme:
			- Instructs on what protocol to use when accessing the resource (HTTP, HTTPS, FTP)
		- User
			- Can put username and password into URL to log in.
		- Host
			- Domain name or IP of the server being accessed
		- Port
			- The port being connected to.
				- Usually port 80 for HTTP and 443 for HTTPS
				- Any port COULD be use between 1 - 65535
		- Path
			- The file name or location being accessed
		- Query String
			- Extra info
				- e.g *blog?id=1* tells the blog path you're looking for the the blog article with the ID *1*
		- Fragment
			- Reference to the location on the ACTUAL page requested.
				- Commonly used for pages with large amounts of content and would have a certain part of the page directly linked to it.
				- This makes it viewable to the user straight away when viewing.

- Making a request
	- It's Possible to make a request to a web server with a single line
		- e.g "*get /HTTP/1.1*"
	- ![[Pasted image 20241111075957.png]]
	- For a better web experience, other data must be sent as well.
		- These are called *headers* 
			- Headers contain extra info to give to the web server
	- An example request:
		*GET / HTTP/1.1
		Host: tryhackme.com
		User-Agent: Mozilla/5.0 Firefox/87.0*
		 - Breakdown of the request:
			 - Line 1 *GET* - request the home page with / and telling the web server we are using HTTP protocol version 1.1.
			 - Line 2 - Tell the web server we want to go to *tryhackme.com*
			 - Line 3 - Telling the web server what browser we're using
			 - Line 4 - Telling the web server the page requested to us is *.https://tryhackme.com*
	- Example Response:
		
		HTTP/1.1 200 OK
		Server: nginx/1.15.8
		Date: Fri, 09 Apr 2021 13:34:03 GMT
		Content-Type: text/html
		Content-Length: 98
		*expand below to see rest, this line is not part of the code*
		
		<html>
		<head>
	    <title>TryHackMe</title>
		</head>
		<body>
	    Welcome To TryHackMe.com
		</body>
		</html>
		- Request Breakdown
			- Line 1 - The version of the HTTP protocol being used
				- Status code "*200 Ok*" tells us the request has been successful
			- Line 2 - Tells us the web server and software number
			- Line 3 - The current date, time and timezone of the web server.
			- Line 4 - The Content-Type header tells the client what sort of information is going to be sent, such as HTML, images, videos, pdf, XML.
			- Line 5 - Content-Length tells the client how long the response is, this way we can confirm no data is missing.
			- Line 6 - HTTP response contains a blank line to confirm the end of the HTTP response.
			- Line 7-14 - The information that has been requested, in this instance the homepage.
	- HTTP methods
		- A way for the client to show their intended action when making HTTP request.
		- Common HTTP methods
			- *GET* Request
				- Used for getting info from the web server
			-  *POST* Request
				- Submitting data to the web server
					- Potentially creating new records
			-  *PUT* Request
				- Submitting data to a web server to update information
			- *DELETE* Request
				- Deleting info/records from a web server

**HTTP Status Codes**

- Codes are broken down into 5 specific ranges
	- |**100-199 - Information Response**|These are sent to tell the client the first part of their request has been accepted and they should continue sending the rest of their request. These codes are no longer very common.|
	- |**200-299 - Success**|This range of status codes is used to tell the client their request was successful.|
	- |**300-399 - Redirection**|These are used to redirect the client's request to another resource. This can be either to a different webpage or a different website altogether.|
	- |**400-499 - Client Errors**|Used to inform the client that there was an error with their request.|
	- |**500-599 - Server Errors**|This is reserved for errors happening on the server-side and usually indicate quite a major problem with the server handling the request.|
- Common HTTP status codes
	- |**200 - OK**|The request was completed successfully.|
	- |**201 - Created**|A resource has been created (for example a new user or new blog post).|
	- |**301 - Moved Permanently**|This redirects the client's browser to a new webpage or tells search engines that the page has moved somewhere else and to look there instead.|
	- **302 - Found**|Similar to the above permanent redirect, but as the name suggests, this is only a temporary change and it may change again in the near future.|
	- |**400 - Bad Request**|This tells the browser that something was either wrong or missing in their request. This could sometimes be used if the web server resource that is being requested expected a certain parameter that the client didn't send.|
	- |**401 - Not Authorised**|You are not currently allowed to view this resource until you have authorised with the web application, most commonly with a username and password.|
	- |**403 - Forbidden**|You do not have permission to view this resource whether you are logged in or not.|
		- ![[Pasted image 20241111125530.png]]
	- |**405 - Method Not Allowed**|The resource does not allow this method request, for example, you send a GET request to the resource /create-account when it was expecting a POST request instead.|
	- **404 - Page Not Found**|The page/resource you requested does not exist.|
		- ![[Pasted image 20241111125617.png]]
	- |**500 - Internal Service Error**|The server has encountered some kind of error with your request that it doesn't know how to handle properly.|
	- |**503 - Service Unavailable**|This server cannot handle your request as it's either overloaded or down for maintenance.|
		- ![[Pasted image 20241111125654.png]]

**Headers

- Additional bits of info sent to the web server when making a request
- Strictly not needed, but will have difficulty accessing HTML properly without it.

- *Common request Headers* (headers sent from the client device, normally through a browser, to the web server)
	- Host
		- Some web servers have multiple sites
		- Providing Host headers can tell the server which one you need
			- Otherwise, you're taken to the default website for the server
	- User-Agent
		- This is browser software and version number
			- Telling the site what browser you're using, helps with loading the site properly
			- Elements of HTML, Javascript and CSS are only available in certain browsers
	- Content-Length
		- Tells how much data to expect in the request
			- The server can then tell if theres data missing in the request
	- Accept-encoding
		- Tells what type of compression method the browser supports
			- So the data can be made smaller for transmit over the internet.
	- Cookie
		- Data sent to server to help remember info

- *Common Response Headers* (Headers that are returned to the client from the server after the request)
	- Set-Cookie
		- Info to store which gets sent back to the client from the server (after a request)
	- Cache-Control
		- How long to store the content of the response in the browser, before deleting it and needing to request again
	- Content-Type
		- What data is being returned (HTML, CSS, JavaScript, Image, Video, PDF ect)
			- With this info, the browser knows how to process the data.
	- Content-Encoding
		- What method was used to compress the data to make it smaller for transit across the internet.

**Cookies**

- Small piece of data stored on the PC
- Saved when a "Set-cookie" header from a web server is received
	- Every future request made, the cookie is sent back to the web server.
- HTTP is 'stateless' so the cookies can remind the web server of the user
	- Also some personal settings for the site or if you've been there before
- 
![[Pasted image 20241111132053.png]]
