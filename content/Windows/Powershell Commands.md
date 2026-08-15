**Resetting AD password**
Set-ADAccountPassword *user* -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose

**Force reset on next login**
Set-ADUser -ChangePasswordAtLogon $true -Identity sophie -Verbose

**Get-command** - Tool for showing what commands available.
	A way to filter the commands shown by type **-commandtype "function"** 

**Get-help** - Provides detailed info about cmdlets including usage, parameters and examples.
	![[Pasted image 20251028143757.png]]
	Use **-examples** to show common uses of command

**get-alias** - shows the alias' for common cmd commands that are different in powershell.
	e.g. *dir* is an alias for **get-childitem**

**Find Module** - search for module that requires installation to powershell as not everything is immediately available. Similar to Linux installing repos.
	If unsure of the exact name, add wildcard * to the partial name. 
		e.g. *cmdlet -Property "pattern"* 

**install-module** - Install rep. e.g. install-module -name "powershellget"

**Get-childitem** - similar to *dir* in cmd or *ls* in unix.

**-path** - directly navigate to a file directory. eg *Set-Location -Path ".\Documents"*

**set-location** - Navigate to a different directory. same as *cd*.

**new-item** - can be used to create directories and files. eg *New-Item -Path ".\captain-cabin\captain-wardrobe\captain-boots.txt" -ItemType "File"*

**remove-item** - remove files and dir's
**copy-item** - copy
**Move-item** - moves the file

**get-content** - similar to *type* in cmd or *cat* in unix

**sort-object** - sorts results. use an operator.

**where-object** - search on specified conditions. If searching for txt files for example:
	*Get-ChildItem | Where-Object -Property "Extension" -eq ".txt"*

**comparison operators**
	*-eq* - 'equal to'.
	*-ne* - not equal
	*-gt* - greater than
	*-ge* - greater than or equal to
	*-lt* - less than
	*-le* - less than equal to

  **-like** - filter by a specific pattern

**select object** - select specific properties or limit objects returned.
	eg *Get-ChildItem | Select-Object Name,Length*

**select-string** - search for text patterns within files. similar to *grep*
	eg *Select-String -Path ".\captain-hat.txt" -Pattern "hat"*


***All following commands used for real-time system monitoring and analysis, proving especially useful to incident responders and threat hunters.***

**Get-computerinfo** - Get comprehensive and thorough system information

**Get-localuser** - lists all user accounts on device

**Get-netipconfiguration** - similar to ipconfig, but more detailed

**Get-NetIPAddress** - shows all IP's configured on the device, including those not active. 

**get-process** - see running process' including cpu and ram usage

**get-service** - info on services running on the system. 
	Good for spotting anomalous.

**get-netTCPconnection** - display current TCP connection locally and remote. 
	good for incident response and malware analysis

**get-filehash** - used for generating file hashes. e.g. *Get-FileHash -Path .\ship-flag.txt*
	valuable in threat hunting, incident response and malware analysis.

***END***

**invoke-command** - execute commands on remote systems.
	enables efficient remote management and, combining it with scripting, automation of tasks across multiple machines.
	can execute commands/payloads on target systems.
		*-ScriptBlock { ... }* - user to execute commands on remote computer.