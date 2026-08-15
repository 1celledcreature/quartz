**Objects**
	Represents an item with *properties* (characteristics) and *methods* (actions).
		e.g. a '*car*' object could have properties that describe it. e.g. *colour*. It could also have methods e.g. *Drive*
	Objects encapsulate data and functionality, making information easier to manage and manipulate.
	Objects can contain (examples): Names, Usernames, sizes as data (properties) or carry functions (methods) (e.g. copy a file)

**Basic Syntax: Verb-Noun**
	Cmdlets (commandlets) follow a verb-noun naming convention. 
		Verb describes the action
		Noun specifies which object the action is applied on.
	Examples:
		*Get-Content*: Retrieves (gets) the content of a file and displays it in the console.
		*Set-Location*: Changes (sets) the current working directory.

**Pipes |** 
	can pass objects and not just text. 
	The objects carry the data as well as instruction.
	example:
		*Get-ChildItem | Sort-Object Length*
	a pipeline of cmdlets to sort and filter the output with the goal of displaying the largest file
		*Get-ChildItem | Sort-Object Length -Descending | Select-Object -First 1*

**Scripting**
	Execute commands contained in a text file to automate tasks.
	
For **blue team** professionals such as incident responders, malware analysts, and threat hunters, PowerShell scripts can automate many different tasks, including log analysis, detecting anomalies, and extracting indicators of compromise (IOCs). These scripts can also be used to reverse-engineer malicious code (malware) or automate the scanning of systems for signs of intrusion.
	
For the **red team**, including penetration testers and ethical hackers, PowerShell scripts can automate tasks like system enumeration, executing remote commands, and crafting obfuscated scripts to bypass defences. Its deep integration with all types of systems makes it a powerful tool for simulating attacks and testing systems’ resilience against real-world threats.
    
Staying in the context of cyber security, **system administrators** benefit from PowerShell scripting for automating integrity checks, managing system configurations, and securing networks, especially in remote or large-scale environments. PowerShell scripts can be designed to enforce security policies, monitor systems health, and respond automatically to security incidents, thus enhancing the overall security posture.
    
Whether used defensively or offensively, PowerShell scripting is an essential capability in the cyber security toolkit.