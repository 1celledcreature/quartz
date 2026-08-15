**Devices on a Local Area Network**
 
**Router**
 
- Operates at layer 3 of the OSI Model (Network)
- Have an interactive interface (Website/console)
    
    - Allows admins to configure rules for port forwarding and/or firewalls

**Switch**
 
- Can facilitate between 3 - 63 devices using ethernet
- Operate at Layer 2 (Data Link) + Layer 3 (Network) of OSI Model
    
    - Layer 2 switches cannot operate at layer 3
- Layer 2 switch
    
    - Forward frames (no longer packets as IP protocol has been stripped) to devices using the MAC address
    - Soley responsible for sending frames to the correct device.
![Exported image](Exported%20image%2020241107123830-0.png)
 
- Layer 3 Switch
    
    - More sophisticated that layer 2
        
        - Due to being able to do some of the things a router can do
    - Will send frames (same as layer 2) and route packets using IP Protocol - VLAN - Virtual Local Area Network
    
    - Allows devices within a network to be split up, virtually.
    - Can use the same internet connection but are treated separately.
    - Provides security
        
        - Rules can be put in place to determine how devices communicate
    ![Exported image](Exported%20image%2020241107123834-1.png)