**Windows Domains**
Is a group of users and computers under the admin of the business.

Centralise the admin of common components of a windows pc network in a single place, known as *Active Directory*.
	The server that runs AD services is the DC server (Domain Controller)
![[Pasted image 20251022134016.png]]

*Advantages of configured Windows domain*
	- Centralised identity management: All users across the network can be configured from Active Directory with minimum effort.
	- Managing security policies: You can configure security policies directly from Active Directory and apply them to users and computers across the network as needed.

**Active Directory**
Core of windows domain *Active Directory Domain Service*.
	Acts as a catalogue for all *'objects'* that exist on the network.
	*Objects* include:
		Users, Groups, Machines, Printers, Shares + others.
	*Users*:
		People/employees that need access to the network.
		Can also define users for services. E.G. IIS or MSSQL. Every service needs requires a user. 
			Service users only have privileges needed for the specific service.
	*Machines*
		- Are an object. Every machine that joins the domain, a machine object is created.
		- Machines are considered "Security principles" and are assigned an account just like a user.
		- The account has limited rights to the domain. Not supposed to be accessed by anyone other than the machine itself.
			As with any account, if you have the password, you can use it to log in.
			Machine account passwords are rotated out automatically and are comprised of 120 characters
		- Identify machine accounts via a specific naming convention. Is the computers name followed by a $ sign. E.G DC01's account would be DC01$
	*Security Groups*
		Define user access by groups.
		Considered 'security principles' so then can have privileges over resources on a network.
		Groups can have users as well as machine members.
		Several groups are created by default to grant specific privileges to users.
			Most important groups include:
			![[Pasted image 20251022141725.png]]
		*AD Users and Computers*
		Objets in AD are organised into OU's (Organisational Units).
			OU's are containers that classify users and machines.
			Used to define sets of users with similar policing requirements.
				- EG sales people have different rights to IT.
			A User can only be a part of a single OU at a time.
		Auto created Default containers include:
			- **Builtin:** Contains default groups available to any Windows host.
			- **Computers:** Any machine joining the network will be put here by default. You can move them if needed.
			- **Domain Controllers:** Default OU that contains the DCs in your network.
			- **Users:** Default users and groups that apply to a domain-wide context.
			- **Managed Service Accounts:** Holds accounts used by services in your Windows domain.
		*Security Group VS OU's*
		OU's
			used for applying policies to users and computers. Including specific configurations pertaining to job roles. 
			Users can only be a part of ONE OU at a time.
		Security group
			- Used to grant permissions, not resources. EG access to shared resource/network printer. 
			- Users can be a part of many groups.

**Managing Users in AD**
Deleting OU's is protected. you need to enable 'advanced features' in the 'view' menu.
Deleting an OU will delete all users groups or OU's under it.
After deletion, it's possible some departments in the users in AD won't match the same as in the org chart. Create and delete to match them.
	*Delegation*
	You can give specific users control over some OU's, known as delegation.
		This means tasks can be performed without needing a domain admin.
	Common use case is IT Support.

**Managing Computers in AD**
By default, all machines that join a domain will be put into the container called "Computers." (Not the DC's however)
	*Organising machines in AD (advice)*
		Devices are normally separated into 3 categories.
			**Workstations**:
			Most common in AD, users log on, most likely a workstation. These devices should never have any privilages.
			**Servers**:
			Second most common device in AD. Used to provide services to users or other servers
			**Domain Controllers**:
			Allow to manage the AD Domain. Have the most sensitive data as they contain hashed passwords for all user accounts in the environment.

**Group Policies**
The point of creating OU's is so we can apply policies to them.
Windows manages policies through Group Policy Objects (GPO's).
	GPO's are a collection of settings that can be applied to OU's.
	Can be aimed at computers and/or users.
Configure via *Group Policy Management* tool in windows
Group policy objects that are assigned to an OU, will affect all sub folders also.
*When selecting a policy object*:
	First tab is 'Scope'
		shows where the GPO is linked to in AD
		Can apply 'Security filtering' to the GPO so that the policy only affects certain users/computers in the OU. Default in Authenticated Users (everyone)
	Settings tab
		The contents of the GPO and what configs it applies.
			Each GPO has certain policies that can only be applied to either users OR computers.
	*Changing password policy*
		Minimum password length. After right clicking a GPO and selcting 'edit'
			Computer Configurations -> Policies -> Windows Setting -> Security Settings -> Account Policies -> Password Policy
Lots of policies to explore. Info can be found by double clicking them and read 'explain'
![[Pasted image 20251023153106.png]]

**GPO distribution**
GPO's are distributed to the network via a network share called *SYSVOL* which is stored on the DC.
All users in a domain should have access to this share over the network to sync GPO's periodically.
The SYSVOL share points by default to the *C:\Windows\SYSVOL\sysvol* directory on each of the DC's in the network.
Changes to GP's can take 2 hours to sync.
*gpupdate /force* command in powershell to implement the changes immediately.

*Creating GPO's*
	- In Group Policy Management, right click the 'Group policy Objects' folder and select 'New'.
	- Name the policy as to what you're looking to achieve.
	- Right click on the newly names policy and hit 'edit'.
	- Here, there is a huge selection of options that can be configured. Apply what is applicable to what you've named the policy.
	- Back in the Group Policy Management Window, under the Group policy Objects folder, drag and drop the policy to the desired OU's/folders/users you would like to apply the policy to.

**Authentication Methods**
All credentials are stored On the DC's. When a user tries to log in, the service talks to the DC to verify they are correct.
There are 2 protocols that can be user on the windows domain to do this:
	*Kerberos* - Used by any recent version of Windows. Default for any recent domain.
	*NetNTLM* - Legacy kept for compatibility purposes.
*Kerberos Authentication*
	Users that logon using Kerberos get assigned tickets.
		Tickets are proof of previous authentication.
	Users that have been given tickets demonstrate to a network they have previously been authenticated by the network before and are enabled to use it.
	Process:
		User sends username and a timestamp encrypted using a key derived from their password to the *Key Distribution Center* (KDC).
			KDC is a service installed on the DC and is in charge of creating kerberos tickets.
		KDC creates and sends back a *Ticket Granting Ticket* (TGT), which allows access to specific services.
		Along with TGT, a *session key* is given to the user, which they will need to generate requests.
			Users cannot access TGT.
			TGT includes a copy of the session key. 
			The KDC doesn't store session key as can recover from TGT if needed. 
![[Pasted image 20251027135309.png]]
When a user wants to connect to a service on the network like a share, website or database, they will use their TGT to ask the KDC for a **Ticket Granting Service (TGS)**. 
TGS are tickets that allow connection only to the specific service they were created for. To request a TGS, the user will send their username and a timestamp encrypted using the Session Key, along with the TGT and a **Service Principal Name (SPN),** which indicates the service and server name we intend to access.

As a result, the KDC will send us a TGS along with a **Service Session Key**, which we will need to authenticate to the service we want to access. The TGS is encrypted using a key derived from the **Service Owner Hash**. The Service Owner is the user or machine account that the service runs under. The TGS contains a copy of the Service Session Key on its encrypted contents so that the Service Owner can access it by decrypting the TGS.
![[Pasted image 20251027135547.png]]

The TGS can then be sent to the desired service to authenticate and establish a connection. The service will use its configured account's password hash to decrypt the TGS and validate the Service Session Key.
![[Pasted image 20251027135648.png]]

*NetNTLM Authentication*
	Uses a challenge-response mechanism.
	![[Pasted image 20251027135822.png]]
1. The client sends an authentication request to the server they want to access.
2. The server generates a random number and sends it as a challenge to the client.
3. The client combines their NTLM password hash with the challenge (and other known data) to generate a response to the challenge and sends it back to the server for verification.
4. The server forwards the challenge and the response to the Domain Controller for verification.
5. The domain controller uses the challenge to recalculate the response and compares it to the original response sent by the client. If they both match, the client is authenticated; otherwise, access is denied. The authentication result is sent back to the server.
6. The server forwards the authentication result to the client.
Users password (or hash) is never transmitted through the network

**Trees, Forests and Trusts**
	*Trees*
		Active directory supports integrating multiple domains. AD can then be partitioned but share the same namespace (e.g thm.local). The domains can be joined together into a *tree*.
		You can build a root domain of thm.local and two subdomains called uk.thm.local and us.thm.local, as examples, each with it's own AD, computers and users.
		![[Pasted image 20251027140719.png]]
		Security groups have to be created when using tree's and forests. ENTERPRISE ADMINS group will grant admin across all domains. 
		Each domain still has it's own admin managed by it's own team.
	*Forests*
	When a company merges, there will be different domain trees for each company. Managed by their own IT. 
	The union of tress with different namespaces is called a *forest*.
	![[Pasted image 20251027141148.png]]
	*Trust Relationships*
	Access may be required from one tree to another.
	To do this arranged trees and forests are joined by TRUST RELATIONSHIPS.
		Trust relationship allows authorisation from one domain to access resources from another domain.
	Can be established one-way or two way 
		One way:
		Domain A trusts domain B. Means B can authorise on A.
		Two way:
		Allow both to mutually authorise. 
		By default, joining domains under a tree or forest will form a two-way trust relationship.