A firewall is a device in a network that’s responsible for what traffic is allowed in or out the network. Like a security boarder.
 
We can configure the firewall to permit or deny traffic based on many factors including:
 
- Where traffic is coming from and to
    
    - Accept/deny traffic from certain networks
- Ports
    
    - Can accept or deny access via certain ports
- Protocols
    
    - Accept or deny access from TCP/UDP?
 
Firewalls use 'packet inspection' to answer these questions.
 
- Firewalls can be dedicated pieces of hardware that can handle massive amounts of data, to simple routers or even software (Snort - which is an IDS)  
Two primary categories of firewalls:

- Stateful
    
    - Uses the entire information from a connection rather than single packets.
        
        - Determines behaviour based on entire connection
    - Consumes many resources as the decision making is dynamic.
        
        - It could let the 1st parts of a TCP handshake that would later fail.
    - If the connection from the host is bad, it blocks the whole device.
- Stateless
    
    - Uses statin rules for individual packets.
        
        - If a device sends a bad packet, the whole device is not always blocked.
    - Don't use many resources.
    - Are not that smart
        
        - Unless the rules are specifically defined, it's essentially useless
    - Great for receiving large amounts of traffic from a set of hosts
        
        - Such as a DDOS attack