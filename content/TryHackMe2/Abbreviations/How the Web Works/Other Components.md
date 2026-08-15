**Load Balancers** 
	Ensure high traffic websites can handle the load
	Providing a failover if the server becomes unresponsive
	- When requesting a website with a load balancer, it will forward the request to one of the servers behind it.
	- Uses algorithms to decide which server is best to deal with the request.
	- can be configured in different ways
		- *Round robin* - try's each server in turn
		- *weighted*- sends to the least busy server
	Also performs checks on the servers performance. This is called a *health check*. If the server doesn't respond appropriately/at all, the balancer will stop sending traffic there.

**CDN (Content Delivery Networks)**
	- Allows to host static files from a website (Java/CSS/images/video) and hosts them all over the world.
	- When user request comes in, the CDN looks for the closest server opposed to across the world.

**Databases**
	- Ways websites store data on users.
	- web servers communicate with the databases.
	- Range from plain text files to server clusters.
	- examples:  MySQL, MSSQL, MongoDB, Postgres, and more; each has its specific features.

**WAF (Web Application Firewall)**
	- Sits between web request and web server
	- It's purpose is to protect the server from hacking or DOS attack.
	- Analyses web requests for common attack techniques (eg from a bot)
	- Uses *Rate Limiting*
		- will only allow a certain amount of requests from an IP per second.
	- If deemed a potential threat, it will be dropped and not sent tot the web server.