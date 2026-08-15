- **bin** (Essential Command Binaries)
    
    - Where all the terminal command files are stored
      
    
- **sbin**
    
    - Only admin special commands within directory (e.g add user). Will then be prompted for password creation and account details. - **Usr**
    
    - Contains **bin** and **sbin**
    - After creation, has same directory's/files as standard user
- **Local**
    
    - Store command binaries that you create.
- **Lib**
    
    - Place where the command binaries will share
- **Boot**
    
    - Contains files needed for system boot - **Var**
    
    - Where log files are kept
    - As well as application related files - **Tmp**
    
    - Temporary files
- **Lib**
    
    - Shared library files
    - Things the device needs to boot - **Home**
    
    - Where user profiles are stored
    - See all user files - **Root**
    
    - 'Admin' user files - **Dev**
    
    - Devices
    - As linux treat everything as a file, devices are also
    - Where **VDA** and **VDA1** are found
        
        - **VDA**
        - Virtual disks (hard drives)
        - May also be seen as sda/sda1 - **ETC**
    
    - Etcetera (known as **etsy**)
    - Where configuration files are found (e.g **network**)
    - Inside network directory is **interfaces**
        
        - **Interfaces -** use **cat** to see file contents which shows all network devices as a file.
        - Shows al network configurations (IP address')
        - Can use this place to configure network settings
          
        
- **Media**
    
    - When usb/hard drive is plugged in, it automatically mounts here as a file - **Mnt**
    
    - Drives that are mounted manually (via commands)

**/etc**
This root directory is one of the most important root directories on your system. The etc folder (short for etcetera) is a commonplace location to store system files that are used by your operating system.
"**passwd**" and "**shadow**" files. These two files are special for Linux as they show how your system stores the passwords for each user in encrypted formatting called sha512.

**/var - Variable Data**
The "/var" directory, with "var" being short for variable data,  is one of the main root folders found on a Linux install. This folder stores data that is frequently accessed or written by services or applications running on the system. For example, log files from running services and applications are written here (**/var/log**), or other data that is not necessarily associated with a specific user (i.e., databases and the like).

**/root**
Unlike the **/home** directory, the **/root** folder is actually the home for the "root" system user. There isn't anything more to this folder other than just understanding that this is the home directory for the "root" user. But, it is worth a mention as the logical presumption is that this user would have their data in a directory such as "**/home/root**" by default. (eg password files)

**/tmp**
This is a unique root directory found on a Linux install. Short for "temporary", the /tmp directory is volatile and is used to store data that is only needed to be accessed once or twice. Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out.
What's useful for us in pentesting is that any user can write to this folder by default. Meaning once we have access to a machine, it serves as a good place to store things like our enumeration scripts.