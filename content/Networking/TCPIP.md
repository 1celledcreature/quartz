**TCP - Transmission Control Protocol**
 
A rule used in networking, like the handling of packets
 
- Similar to the OSI model TSP/IP protocol is made up of 4 layers.
    
    - Application
    - Transport
    - Internet
    - Network interface - Similar to OSI model, info is added to TCP as a piece of data travels through it.
    ![[Pasted image 20251104142810.png]]
    - Proccess know as encapsulation
        
        - Reverse of encapsulation is decapsulation. - TCP is connection based
    
    - Has to have a connection between client and device before sending data
        
        - This process is known as the 'three-way handshake - Advantages of TCP
    
    - Guarantees data integrity
    - Can sync 2 devices which prevents them from being flooded with data in the wrong order
    - Performs a lot more process' reliably
- Disadvantages of TCP
    
    - Needs a reliable connection
        
        - If one small bit of data isn't received, the entire amount must be re-sent.
    - A slow connection can cause a bottleneck.
        
        - As the connection is reserved with the other device the whole time during transfer.
    - TCP is slower than UDP
        
        - More computing (work) has to be done by the devices using this protocol.
      

TCP packets contain information know as headers.  
Headers are added from encapsulation.  
Some crucial headers include:
 
- Source Port
    
    - The randomly chosen port opened to send the packet (from ports 0-65535). Obviously, the port has be free and available for transfer
- Destination Port
    
    - The port the destination application or service is running.
        
        - EG a webserver running on Port 80
    - Different from the source port as the port ISN'T chosen randomly.
- Source IP
    
    - The IP the device is sending the packet.
- Destination IP
    
    - The IP of where the packet is going.
- Sequence number
    
    - When a connection happens, the 1st piece of data is given a random number.
- Acknowledgement Number
    
    - When the first piece of data has been given it's sequence number, the next piece will be the sequence number +1.
- Checksum
    
    - This gives TCP integrity
    - A math calculation is made where the output is remembered.
        
        - If the receiving device makes the same calculation and the result is different, the data will be corrupt.
- Data
    
    - Where data (bytes) of a file that's being transmitted is stored.
- Flag
    
    - Determines how the packet should be handled by either device during the handshake process.
    - Specific flags determine specific behaviours.
 
**Three-way Handshake** - A term given to the process of establishing a connection between 2 devices.
 
The handshake communicates using special messages. Main ones include:
 
- SYN
    
    - The initial packet sent to initiate a connection and sync 2 devices
- SYN/ACK
    
    - The packet sent back by the receiving device (server) to acknowledge the sync attempt.
- ACK
    
    - A packet either device sends to confirm receipt that messages/packets have been received.
- DATA
    
    - When connection is established, data (bytes) is sent via the "DATA" message.
- FIN
    
    - The packet used to cleanly and properly close the connection after transfer is complete.
- RST
    
    - The packet ends all communication abruptly.
    - This usually indicates there was a problem during the process.
        
        - EG If the service/application is not working correctly or the system has low resources.
 
Example between 2 devices:

![Alice SYN/ACK ACK Bob ](Exported%20image%2020241107123901-0.png)  

Sent data is reconstructed using a random number sequence, which is incremented by 1. Both devices must agree on the number sequence for data to be sent in the correct order.  
This happens in 3 steps:

- SYN - Client device
    
    - Gives Initial sequence number (ISN) to SYNchronise with (0)
- SYN/ACK server
    
    - Gives initial sequence number (0) to SYNchronise (5000) with and ACKnowledges the ISN
- ACK - Client
    
    - ACKnowledges the ISN of 5000 and offers data that is ISN+1 (0+1)
![Device Client (Sender) Client (Sender) Client (Sender) Initial Number Sequence (ISN) 1 2 Final Number Sequence 0+1=1 1+1=2 ](Exported%20image%2020241107123902-1.png)
 
**Closing a Connection (TCP)**
 
- TCP will clos a connection once the device being sent to has received all the data.
- Due to TCP using a lot of hardware resources, the connections need to be closed ASAP
- To close the connection, TCP sends the 'FIN' packet and needs to receive acknowledgment from the device.

![Alice FIN ACK FIN ACK Bob ](Exported%20image%2020241107123904-2.png)

