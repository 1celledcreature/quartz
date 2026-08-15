User Data Protocol is a protocol used to communicate data between devices.
Operates at the Transport Layer (layer 4)

- Is a Stateless protocol
    
    - Meaning it doesn't require a constant connection between devices.
    - A 3 way handshake does not occur
    - Synchronisation also doesn't occur
- UDP is used in apps that can handle data being lost (Video, streaming VOIP)
 
- Advantages:
    
    - Faster than TCP
    - Leaves the software to decide if there's any control over sent packet speed
    - Doesn't reserve continuous connection like TCP
- Disadvantages
    
    - UDP doesn't care if data is received.
    - Unstable connections result in bad user experience. - No process happens when setting up a connection between 2 devices
- Data integrity is looked passed.
- UDP packets are simpler than TCP and have fewer headers.
- Both protocols do share some standard headers.
   

TTL - Time to Live

- An expiry timer for the packet. Doesn't clog up network if it doesn't reach the destination

Source Address

- IP address of the device the packet is being sent to.

Destination address

- Where the packet is being sent to

Source port

- Port opened by the sender

Destination port

- The port number the app is running. Not chosen at random

Data

- Where the bytes of the file being transported are kept  
Example of UDP:
 ![Alice REQUEST RESPONSE RESPONSE RESPONSE Bob ](Exported%20image%2020241107123908-0.png)