**SMTP** - Simple mail transfer protocol
	Defines how mail talks to mail server and how mail servers talk to each other.
	Analogy - local post office: 
		- Greet employee
		- tel them where you're sending
		- provide senders info
	Commands used by mail client when transferring an email to SMTP server:
		*HELO* or *EHLO* - initiates SMTP session
		*MAIL FROM* - specifies senders email address
		*RCPT TO* - Specifies recipients address
		*DATA* - indicates that the client will begin sending the content of the email message
		*.* - is sent on a line by itself to indicate the end of the email message

**POP3** - Post Office Protocol
	Designed to allow the client to communicate with a mail server and retrieve messages
	email clients send via *SMTP* and retrieves using *POP3*
	Analogy:
		SMTP - handing over an envelope to post office
		POP3 - checking the mailbox for new letters
	Commands:
		- *USER + (username)* - Identify's user
		- *PASS + (password)* - Provide the user's password
		- *STAT* - requests number of messages and total size
		- *LIST* - Lists all messages and their sizes
		- *RETR + (Message_number)* - Retrieves the specified message
		- *DELE + (Message_number)* - mark for deletion
		- *QUIT* - ends the POP3 session applying changes, such as deletions
	Connect to POP3: *telnet (ip address) 110*
	Example (caught from wireshark)
		![[Pasted image 20251112135717.png]]

**IMAP** - Internet message Access Protocol
	Synchronises mailbox's across devices
	uses more storage due to keeping the emails on a server and syncing across multiple devices
	 Commands:
		 *LOGIN + (username) (password)* - authenticates
		 *SELECT (mailbox)* - selects mailbox to work with
		 *FETCH (mail_number) (data_item_name)*
			 E.g *fetch 3 body [ ]* - to fetch message number 3, header and body
		*MOVE (sequence_set) (mailbox)* - moves specified messages to another mailbox
		*COPY (sequence_set) (data_item_name)* - copies specified messages to another mailbox
		*LOGOUT* - logs out
	Example:
		![[Pasted image 20251112140836.png]]
		