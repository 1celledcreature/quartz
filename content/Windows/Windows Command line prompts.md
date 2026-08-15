- **-h or /?** - Use after a command to show the help page of that command.  

**Wildcard character `*`**  - refer to multiple files. For example, *'copy * .md C:\Markdown'* will copy all files with the extension *md* to the directory *C:\Markdown*

**Netstat** - See network info
	**-b** - displays the executable associated with each active connection and listening port.

**set** - See lots of system info. Including the path of where commands will be executed. (PATH=C:\path\ )

**ver** - see version of windows running.

**systeminfo** - See in depth details of the OS

**driverquery** - See installed drivers

**| more** - Use after command help or txt files to see large amounts of info one page at a time

**help** - provides info on a specific command

**cls** - Clear screen

**ipconfig** - See IP Adress
	**/all** - See all info in regards to the network and IP

**ping** - Send a packet to address to see if a response is received.
	**-c** - How many packets to send. e.g. *-c 4* to send 4 packets. 

**Tracert** - Like ping, but shows all the IP's on the journey.

**nslookup** - use to look up IP address of a domain. e.g. "nslookup google.com"

**netstat** - Shows network configurations and listening ports
	**-a** displays all established connections and listening ports
	**-b** shows the program associated with each listening port and established connection
	**-o** reveals the process ID (PID) associated with the connection
	**-n** uses a numerical form for addresses and port numbers
	**-abon** combine all of the above  

**cd** - see current directory (add location/folder name to move there)
	**..** - move up one directory

**dir** - see 'child' directories in the current directory
	**/a** - Displays hidden and system files as well.
	**/s** - Displays files in the current directory and all subdirectories.

**tree** - show visuals of child directories and sub-directories

**mkdir** - Followed by name. Create a directory (folder).
**rmdir** - Followed by name. Deletes the directory (folder).

**type** - use alongside a file name to show the contents of a txt file in the terminal window.
**more** - for longer txt files (use 'spacebar' to move through pages or 'enter' to go line by line)

**copy** - copy file. e.g. 'copy file1 file2'. file1 the original and specifying copied name.
**move** - Move files. e.g 'move file1 ..'.

**del** or **erase** - Delete files.

**tasklist** - Similar to task manager. see all running process'.
	**/h** - See all available filters
	**/FI** - filter tasks related to specific proccess
		e.g. To search for tasks related to sshd.exe, we can do that with the command *tasklist /FI "imagename eq sshd.exe*. Note that */FI* is used to set the filter image name equals *sshd.exe*
**taskkill** - End task.
	e.g. *taskkill /PID target_pid*. PID being the process ID.

**chkdsk** - checks the file system and disk volumes for errors and bad sectors.

**driverquery** - displays a list of installed device drivers.

**sfc /scannow** - scans system files for corruption and repairs them if possible.

**powershell** - start powershell

**whois** - Shows the record of a registered domain.
	Information provides includes: Name, phone number, email, address plus much more.