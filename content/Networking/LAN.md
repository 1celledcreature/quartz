**Topology - the design and look of a network**
 
Star Topology

- Devices connected via a central device (switch/hub)
- Advantages:
    
    - Scalable
    - Easy to add devices to
- Disadvantages
    
    - More expensive than others (lots of equipment required)
    - Bigger the network, more the maintenance
    - If the central hub fails, devices can no longer send or receive data
    ![Exported image](Exported%20image%2020241107123821-0.png)
 
Bus topology

- Relies on a single cable known as 'backbone cable'
- Like a tree, devices 'leaf' off the one branch
- Advantages
    
    - Easy to set up
    - Cost effective
- Disadvantages
    
    - All data travels down 1 cable. If it breaks, no data flow to any device
    - Prone to being slow when simultaneous data requests from devices
    - difficult to troubleshoot with so much data on one cable
    ![Exported image](Exported%20image%2020241107123822-1.png)  
    
 
Ring Topology (also known as 'token topology)

- Devices are connected to form a loop
- Sends data through one device to another (forwards) until target is reached
- Advantages
    
    - Little cabling needed
    - Less dependence on dedicated hardware
    - Less prone to 'bottlenecks' (like the bus) due to large amounts of data not being sent.
    - Easy to troubleshoot (all data going one way)
- Disadvantages
    
    - Device will only send data if that same device isn't already
    - Data has to travel through multiple devices to get to target
    - One cable or device goes down, whole network goes down
 ![Exported image](Exported%20image%2020241107123825-2.png)  

**Switch - What is it?**

- Dedicated devices that help connect multiple devices to one router via ethernet
- Found in larger networks (business, school ect)
- Usually come in multiples of 4 (4 8 16 24 32 ect)
- Switches and routers can be connected to each other, increasing redundancy
- More efficient than hubs/repeaters
    
    - Easy to keep track of where devices are connected (which port)
    - Packets are sent direct to target device
    ![The Internet Router #1 Switch #1 switch #2 ](Exported%20image%2020241107123826-3.png)
 
**Router - What is it?**

- Connects networks to pass data
- Routing is a label given to the process of data traveling across networks
- Handles translation of data
    
    - E.g. email. House - router - internet - router - house
![Computer A ](Exported%20image%2020241107123827-4.png)