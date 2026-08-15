Located in */var/log* dir.
Contains logging information on apps and services running.
Logs are auto managed by the OS in a process known as 'rotating'

Example of logs from an Ubuntu machine:
![[Pasted image 20251019182535.png]]

*apache2* - web server
*fail2ban* - monitors brute force attacks
*UFU* - SERVICE USED AS A FIREWALL

logs for services like a web server contain info on all requests (great for dev teams).
Also helps to diagnose issues or investigate intruder activity.

Two log types for intruder activity
	Access log
	error log
	![[Pasted image 20251019183139.png]]
	