NSM - Network Security Monitoring  
MAC - Media access control address  
ICMP - Internet control message protocol (used by 'ping')  
ARP - Address Resolution Protocol  
DHCP - Dynamic Host Configuration Protocol  
OSI - Open Systems Interconnection Model  
NIC - Network Interface card  
OSPF - Open Shortest Path First  
RIP - Routing Information Protocol  
TCP - Transmission Control Protocol  
UDP - User Datagram Protocol  
PPP - Point to Point Protocol  
VLAN - Virtual Local Area Network
SSH - Secure shell
	- **Secure authentication**: Besides password-based authentication, SSH supports public key and two-factor authentication.
	- **Confidentiality**: OpenSSH provides end-to-end encryption, protecting against eavesdropping. Furthermore, it notifies you of new server keys to protect against man-in-the-middle attacks.
	- **Integrity**: In addition to protecting the confidentiality of the exchanged data, cryptography also protects the integrity of the traffic.
	- **Tunneling**: SSH can create a secure “tunnel” to route other protocols through SSH. This setup leads to a VPN-like connection.
	- **X11 Forwarding**: If you connect to a Unix-like system with a graphical user interface, SSH allows you to use the graphical application over the network.