**TELNET** (Teletype network)

Protocol used for remote terminal connection. 
	allowing to connect to a remote system and enter commands

Can use telnet to connect to any server listening on a TCP port number. (see ports)

*Example*: telnet 10.10.34.211 **7** (port 7, which is echo, is an example port)
	to leave **CTRL + ]** then 'quit'

*Web page requests*
	- Connect to port 80 using telnet. **telnet ≤ipaddress≥ 80**
		- after connecting, example connection *GET / HTTP/1.1* and hit enter
		- Then specify the host *Host: telnet.thm* and hit enter twice.
			- Can also use *Host: anything* for any page
		Can also specify files if you know the name
			e.g. **GET /flag.html HTTP/1.1
