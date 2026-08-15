What is the OSI model
 
- Provides a framework dictating how all network devices will send receive and interpret data.
- Devices can have different functions and designs on a network communicating with other devices. Data sent across networks that follows the OSI model can then be understood by other devices.
- Consists of 7 layers arranged 7-1.
- At every layer the data goes through, specific process' take place including bits of information being added. This is called encapsulation.

*Encapsulation*
	The process of Adding a header at every layer.
	Allows each layer to focus on it's intended function.
		Application data:
			User inputs data, the layer formats the data and sends it using the app protocol
		Transport protocol segment or datagram:
			Adds the proper header information and creates the TCP segment (or UDP datagram) then sent to...
		Network packet (the internet layer):
			Adds an IP header to the received packet. Then sent to...
		Data link frame:
			Ethernet or wifi receives the IP packet, adds the proper header and trailer.
			This creates a Frame.
![[Pasted image 20251105143410.png]]


 
What the OSI model looks like:

![4. 3. 2. 1. Application Presentation ess10 Transport Network Data link Physical ](Exported%20image%2020241107123848-0.png)   
**Physical**
1. Physical components of the hardware on a network
    - EG ethernet cables
    - Devices use electrical signals to transfer data in binary
 
 **Data Link**
	- Describes the agreement between different systems on the same network.
	- Physical addressing of the transmission
	- Receives the packet from the network layer (3) (Including the IP) and adds the physical MAC address.
	- Every network device has a NIC (network interface card) which all have a unique MAC address.
	    Mac address' are set and can't be changed (they can be spoofed)
		When info is sent across a network, it's the physical address that’s used to direct the information.
		Each frame in network communication contains two mac address'
			Destination data-link address 
			Source data link address 
	The job of the Data Link is to present the data in a Format that’s suitable for transmission

**Network**
	- Where routing and re-assembly of data happens.
	- Routing determines the optimal path where the re-assembled travels.
	- Protocols are in place to decide on the optimal path
		OSPF - Open Shortest Path First
			has routers exchange updates about state if connected links/networks.
			Each router can then find the quickest path
		EIGRP - Enhanced Interior Gateway Routing Protocol
			Is a cisco propriety routing protocol
			allows routers to share info and cost (bandwidth/delay)
		BGP - Boarder Gateway protocol
			Primary routing protocol for the internet
			Allows networks to exchange info on routing establishing paths. 
			Helps to ensure data on the web moves efficiently 
	    RIP - Routing Information Protocol
		    For small networks
		    Share information about what they can reach (routers)
		    Each router builds a routing table based on this info
- Factors that decide the fastest route
	    Shortest - Least amount of devices packets have to travel
		Reliable - Have packets been lost on a certain route before?
	    Fastest physical connection - one path may be using fibre opposed to copper
	Everything at this layer is deals with 192.168 IP address'
	Devices such as Routers are known as layer 3 devices as they are capable of working with the 3rd layer of OSI
	Examples of this layer include
		Internet Protocol (IP)
		Internet Message Protocol (ICMP)
		VPN (Virtual Private Network)
		Protocols such as IPSec and SSL/TLS VPN
![Computer A Computer B ](Exported%20image%2020241107123850-1.png)
   

**Transport**
	data travels on one of two different protocols based on certain factors.
		TCP - Transmission Control Protocol
			Reserves a constant connection between the 2 devices for the whole time it takes for data to be sent.
			Incorporates error checking
			Error checking is how TCP guarantees the data sent in small chunks (in the session layer 5) is reassembled in the same order.
		    **Advantages of TCP**:
			    Guarantees the accuracy of data
			    Can Sync 2 devices to prevent each other from being flooded.
				Performs a lot more process' for reliability
			**Disadvantages of TCP**:
		    Requires a reliable connection. If one small chunk of data is lost, none of it can be used.
		    Slow connection can bottleneck a device as the connection is reserved on the receiving device.
		    Slower than UDP as devices have to do more work. - TCP is used for situations:
			    File Sharing
			    Internet Browsing
			    Sending email

This is due to these services needing complete and accurate data.
 
Example of packets re-assembling

![Packet Webserver Final Computer ](Exported%20image%2020241107123854-2.png)  

UDP - User Datagram Protocol
	Limited features compared to TCP. No error checking and reliability.
	any data sent via UDP is sent to the device whether it gets there or not.
	No sync between the devices or a guarantee of the delivery. Hit and hope!
	 
Advantages of UDP:
    - Faster than TCP
    - Leaves the application layer (7) to see if there's control over how quick packets are sent.
    - Does not reserve a continuous connection. - Disadvantages of UDP
Disadvantages 
    - Doesn't care about the data delivery.
    - Flexible to software devs (due to layer 7)
    - Unstable connection = bad user experience 

Example of missing packets
   
![Computer Webserver ](Exported%20image%2020241107123855-3.png)  

UDP is useful for situations
- where small data pieces are being sent.
    - Eg Device discover protocols (ARP + DHCP) and Video streaming (pixelation is just missing packets of data) - Session
- Data is translated/formulated from Layer 6 (Presentation).
- The session (layer 5) creates and maintains the connection to the device/computer.
- While a connection is active, it creates a 'session'.
- Whist the connection is active, so is the session
- Also responsible for closing the connection if connection hasn't be used for a while or is DC'd.
- Can contain 'checkpoint'
    If data data is lost, only new data is required to be sent, saving bandwith.

**Sessions** 
	Responsible for establishing, maintaining and syncing communication between apps on different hosts.
	Data sync ensures data is communicated in the correct order
	Data cannot transfer between different sessions.
	Examples include:
		NFS (Network File System)
		RPC (Remote Procedure Call)

 **Presentation**
	Where 'standardisation' takes place
    Software (e.g. email client) can be developed differently but data still needs handling the same way.
    Acts as a translator for data to and from Layer 7 (Application).
    receiving device will understand data sent even if in a different format.
	    E.G sending an email, both email clients mat not be the same. But the contents have to be.
	    Use MIME (Multipurpose Internet Mail Extensions) to attach files to email
		    MIME encodes a binary file using 7-bit ASCII characters.
	Security features (E.G HTTPS) occur at this layer
 
 **Application**
	Layer where protocols and rules are placed to determine how a user interacts with data received.
	Everyday apps (E.G email clients, browsers ect) use a GUI (Graphical User Interface) for users to interact with the data that’s sent/received.
	Other protocols managed include DNS (Domain Name System)
	    DNS is how website address' are translated into IP's.
	Examples include:
		HTTP
		FTP
		DNS
		POP3
		SMTP
		IMAP

**OSI Summarised**
![[Pasted image 20251104142345.png]]


