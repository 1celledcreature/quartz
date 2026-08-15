- Allows devices on separate networks to communicate securely.
    
    - Creates a dedicated path between the devices known as a tunnel.
    - Devices in the tunnel form their own private network. - Only devices on the same network can communicate (e.g office)
    
    - However, a VPN allows many offices to be connected.
![The internet Network Network Network (VPN) 1. Network #1 (Office #1) 2. Network #2 (Office #2) 3. Network #3 (Two devices connected via a VPN) ](Exported%20image%2020241107123922-0.png)  

Advantages

- Allows networks worldwide to be connected.
- Offers privacy
    
    - Encrypts data - only the devices on the network can understand the data
        
        - This protects against 'sniffing'
- Anonymity
    
    - Reporters can use this in areas where freedom of speech is controlled
    - Traffic can be still viewed by ISP
    - The anonymity of a VPN is only as good as the worst device
    
VPN Technologies
 
- PPP - Point to Point Protocol
    
    - Used in PPTP to allow authentication and provide encryption of data.
    - VPN's use a private key and public certificate (Similar to SSH)
        
        - Private key and certificate must match to connect.
    - This in non-routable (Can't leave a network by itself) - PPTP - Point to Point Tunnelling Protocol
    
    - Allows data from PPP to travel and leave the network.
    - Easy to set up
    - Supported by most devices
    - Weakly encrypted - IPSec - Internet Protocol Security
    
    - Encrypts data using existing IP (internet protocol) framework.
    - Difficult to set up in comparison to the others.
    - Strong encryption.
    - Supported on many devices.