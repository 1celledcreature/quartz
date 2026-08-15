- DHCP assigns an IP address to a network.
**DORA** - Discover, offer, request, acknowledgement  
	- When a new device connects to a network, it sends out a request (DHCP discover) asking if there are any DHCP servers offering IP address'
	- The server replies with an IP address they can use (DHCP offer)
	- The device then has to confirm it wants this IP (DHCP Request)
	- The server then acknowledges to the device this is complete.
	- The device can use the IP address (DHCP ACK (acknowledgment))

![j•"Od3HO ](Exported%20image%2020241107123844-0.png)

Example of an IP address being requested:
![[Pasted image 20251110132341.png]]
	Client sends packet from 0.0.0.0 to 255.255.255.255
	The 1st and 3rd packets broadcast to MAC address *ff:ff:ff:ff:ff:ff* 
	DHCP offers IP along with network config.