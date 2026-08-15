**What is a web server**
- Software that listens for incoming connections, then uses HTTP protocol to deliver.
- Most common
	- Apache, Nginx, IIS, NodeJS
- Delivers files from it's root directory defined by the software settings.
	- Nginx and Apache use the location /var/www/html in linux.
	- IIS uses C:\inetpub\wwwroot for windows.
	- When you request a file from a sit (/pic.jpg) it would send the file /var/www/html/pic.jpg from the local hard drive.

**Virtual Hosts**
- Used so web servers can host different domain names.
- Software on the server checks the hostname being requested from the http headers and matches to the virtual hosts. 
	- Virtual hosts are just text configuration files
	- If no match, the default website is provided
- Can have their root directory mapped in different locations on the hard drive
	- one.com mapped to /var/www/website_one and two.com being mapped to /var/www/website_two
- No limit to the number of websites on a server.
	- Performance will have to be taken into account.

**Static vs Dynamic content**
- Static is content that never changes
	- Pictures, javascript, CSS
	- can include HTML that doesn't change.
	- These are files that are direct from the server where no changes are made.
- Dynamic content changes with different requests
	- A blog is an example. Once posted the site changes to show the latest entries. It updates
	- A search page on a blog is another. Depending on the search term, different results are displayed.
- Both these changes are done in the backend with use of programming scripting language. 
	- You can't see the backend. Including the HTML source.
	- the HTML is the result of the backend processing.
- Everything seen in the browser is called the frontend.

**Scripting and Backend Languages**
- No limit to what backend can achieve. These make a website interactive to a user.
- Examples of languages:
	- PHP
	- Python
	- Ruby
	- NodeJS
	- Pearl
- These languages interact with databases
	- Call external services
	- Process user data
	- Lots more
- Basic php example, If you requested http://example.com/index.php?name=adam:
	
	if index.php was built like this![[Pasted image 20250707213809.png]]
	It would output this to the client
	![[Pasted image 20250707213948.png]]
	The client doesn't see the php code as it's on the backend.
- This can open up a lot of security issues for web apps that haven't been created securely 