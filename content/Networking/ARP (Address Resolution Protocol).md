- Associates a MAC address with an IP address on a network.
- Every device on the network keeps a log of all other devices MAC address'
- The device shouts out to the network looking for the specific device.
    
    - Devices use the ARP protocol to find the MAC address of a device
 
How it works:

- Every device has a ledger to store info, called a cache (ARP cache)
    
    - The cache stores/remembers the previous MAC address' used and the IP address' associated with them
    
- ARP request/reply
    
    - When this is sent, the device is asking the network "what is the MAC address of this IP)"
    - When the device with that IP responds, it then gives its MAC address using an ARP reply.
    - The requesting device can now remember the associated IP with the MAC address
    - This information is the stored in the ARP Cache

![SRC MAC: DST MAC: MSG; who Address 2 SRC MAC: DST MAC: MSG: 1 Address ](Exported%20image%2020241107123842-0.png)

ARP requests and replies are not encapsulated in UDP or IP packet. They use Ethernet frames.
example:
	![[Pasted image 20251110133619.png]]
ARP are Layer 2 as it deals with MAC address'
ARP allows the translation from layer 3 addressing to layer 2