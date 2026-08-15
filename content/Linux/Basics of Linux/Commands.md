**pwd** **(Print working Directory)** - Shows location in file system
 
**ls** **(List)** - List contents (files) of current directory
	 **-a** - shows hidden files/folders. (they start with ".") 
	 **-lh** - shows permissions for files and folders in directory
		 - Read, write and execute
 
**cd** **(Change Directory)** - changes where you are in the file system
- E.g. cd Desktop

**file** - shows the file extension
- need file name eg **file doc1**

**mv** - merge or modify files
- needs 2 filenames. eg **mv file file2** will merge both files with the latter becoming the primary. 
- Move file to directory **mv file1 folder1**

**cd** .. - move backwards through the file system
 
**whoami** - Shows username logged in
 
**clear** - clear all terminal text. (Or **ctrl + L**)
 
**cat** **(Concatenate)** - Use to read files.
	Use with **LS** to open the file/device in terminal (breaks files down to their binary form)
 
**cp** **(Copy)** - Copy file
- Needs name of copy. eg copying "file" - **cp file file2** would create 2nd file called file2
- While in file, use cp *file to copy* *new file name* to make a copy (in same directory
 
**sudo** - Admin creds for singular command
 
**rm** **(Remove)** - Delete file
- E.g. rm testfile.png
- To delete a directory, needs **-R**

**grep** - Search for any word or pattern inside a file.

**Adduser *example* -** Add user to device
 
**Which -** find out where command binaries live.
- E.g **which** **ls** will show directory command is located (usr/bin or /bin)

**--help** - Shows all the options a command accepts and what they do

**man** - manual. eg. 'man ls' would show all the different uses and describe what they do

**su** - Switch user eg *su user1* - will drop into previous users home directory.
	**-l** - will drop you in logged in users home directory

**wget** - can be used to download files from the terminal using a http(s) address. Uploades to current working dir.
	eg. **wget** https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt
	See also - downloading from web server note

**scp** - Copy files securely through SSH which provides authentication and encryption. 
		Copy files & directories from your current system to a remote system
		Copy files & directories from a remote system to your current system
	e.g scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt*

**ps** - See all running process' on a machine.
**ps aux** - See all process' running for all users

**top** and **htop** - real time stats about the process' running
	**top** - black and white version, updates every 10 secs
	**htop** - colour, updates regularly 

**kill** - kill a process. *kill 1337*
	need PID (process ID) 
	*SIGTERM* - Kill the process, but allow it to do some cleanup tasks beforehand
	*SIGKILL* - Kill the process - doesn't do any cleanup after the fact
	*SIGSTOP* - Stop/suspend a process (pause)

**systemctl** - interacts with the systemd process/daemon.
	use in the format: *systemctl* option service
		Four 'options':
			Start
			Stop
			Enable
			Disable

**fg** - brings a background process to the foreground of the terminal so it can be interacted with
	E.g a script running in the background brought forward in order to be interacted with in the terminal.

**crontab** - used for automation (see 'process')
	**-e** - select editor to edit crontab
	**-l** - list users current cron jobs

**apt** - Package management (install ect)
	**apt remove** - uninstall (e.g apt remove sublime-text)

**ss** **(socket statistics)** - like netstat but faster and more efficient

**zsh** - Show the shell name currently on the OS

**chsh -s** - Permanently change default shell

**history** - display all previous commands entered

**nano** - creates text editor file

**chmod** - change permissions of a file/script
	*+x* - make the script executable (use *./* to execute when in file dir)

**| less** - shows info one screen at a time
	*b* - go back up the screen
	*Space* - go down pages
	*q* - end the scroll

**ftp** - connect to remote server using ftp protocol. (add IP address after command)

**ssh** - start secure remote connection to another client
	*-x* - runs the graphical interface in the connection


|                   |                                                                                                                                                  |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Symbol / Operator | Description                                                                                                                                      |
| &                 | This operator allows you to run commands in the background of your terminal.                                                                     |
| &&                | This operator allows you to combine multiple commands together in one line of your terminal.                                                     |
| >                 | This operator is a redirector - meaning that we can take the output from a command (such as using cat to output a file) and direct it elsewhere. |
| >>                | This operator does the same function of the `>` operator but appends the output rather than replacing (meaning nothing is overwritten).          |

|         |                         |                              |
| ------- | ----------------------- | ---------------------------- |
| Command | Full Name               | Purpose                      |
| touch   | touch                   | Create file                  |
| mkdir   | make directory (folder) | Create a folder              |
| cp      | copy                    | Copy a file or folder        |
| mv      | move                    | Move a file or folder        |
| rm      | remove                  | Remove a file or folder      |
| file    | file                    | Determine the type of a file |