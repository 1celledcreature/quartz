**What are they?**
 
- Small pieces of data that come together and make a larger piece.
 
**Frames**

- A FRAME is at layer 2 (Data link) meaning there is no IP address.
    
    - Putting an envelope within an envelope and sending it
    - The 1st envelope is the packet, with the frame in the other stored inside (Frame)
- The encapsulation stage (From Layer 3, NETWORK) is when the packets are stripped away, with the frame inside.
    
    - In regards to IP address', we are usually talking about packets.

**Packets**

- An efficient way of communicating data
    
    - prevents bottlenecking (clogging up the network), when multiple large amounts of data is being sent.
- An example of this:
    
    - Images are not sent to a device as a whole, It's divided into small chunks then reconstructed when it reaches the device.
![Webserver Computer ](Exported%20image%2020241107123858-0.png)  
- Packets have a different structure depending on data being sent.
- Networking is full of standards and protocols
    
    - Acting as rules of how a packet is handled by a device.
    - Considering the amount of devices on the internet, chaos could occur without standardisation
- Internet Protocol
    
    - A packet using this protocol will have 'headers'.
    - 'Headers contain information about the packets being sent across a network.
   

- This information includes:

|                           |                                                                                                                                                                         |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Time to Live:             | This field sets an expiry timer for the packet to not clog up your network if it never manages to reach a host or escape!                                               |
| Checksum:                 | This field provides integrity checking for protocols such as TCP/IP. If any data is changed, this value will be different from what was expected and therefore corrupt. |
|                           |                                                                                                                                                                         |
| Source  <br>Address:      | The IP address of the device that the packet is being sent from so that data knows where to return to.                                                                  |
|                           |                                                                                                                                                                         |
| Destination  <br>Address: | The device's IP address the packet is being sent to so that data knows                                                                                                  |
**The life of a packet**
1. On the TryHackMe search page, you enter your search query and hit enter.
2. Your web browser, using HTTPS, prepares an HTTP request and pushes it to the layer below it, the transport layer.
3. The TCP layer needs to establish a connection via a three-way handshake between your browser and the TryHackMe web server. After establishing the TCP connection, it can send the HTTP request containing the search query. Each TCP segment created is sent to the layer below it, the Internet layer.
4. The IP layer adds the source IP address, i.e., your computer, and the destination IP address, i.e., the IP address of the TryHackMe web server. For this packet to reach the router, your laptop delivers it to the layer below it, the link layer.
5. Depending on the protocol, The link layer adds the proper link layer header and trailer, and the packet is sent to the router.
6. The router removes the link layer header and trailer, inspects the IP destination, among other fields, and routes the packet to the proper link. Each router repeats this process until it reaches the router of the target server.