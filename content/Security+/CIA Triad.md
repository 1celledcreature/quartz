Confidentiality, Integrity & Availability
 
- Somtimes referred to as AIC triad - Security Objectives
    
    - Confidentiality - Prevent information from being leaked
    - Integrity - Things can't be modified without detection
    - Availability - ensuring networks and systems are up
    ![Security Objectives Confidentiality ](Exported%20image%2020241107123755-0.png)
   

- Confidentiality
    
    - Use encryption so only certain people can access. Even if intercepted, data would not be readable.
    - Access controls can limit who has access to what. E.g accountants can only access accounts.
    - MFA's
- Integrity
    
    - Ensure data wasn't tampered with.
    - Hashing
        
        - Create a hash of the data. If both sender and receiver's hash match, you know data hasn't been tampered with.
    - Digital signatures
        
        - Takes the hash, and encrypts it.
        - Check to ensure data wasn't tampered with and also verify the sender.
        - Important for VERY sensitive data
    - Certificates
        
        - Can help identify devices and users
    - Non-repudiation
        
        - Provides proof of integrity ensuring the information really came from who it says
- Availability
    
    - Information is always accessible to users (authorized)
    - Redundancy
        
        - Building systems to ensure data vis always available
    - Fault Tolerance
        
        - System keeps up and running even if something fails. Sothing will pick up.
    - Patching (updates)
        
        - Stabilizes the system
        - Helps patch security threats