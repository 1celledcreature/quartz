
**What is DNS?**

- DNS (Domain Name System) is basically converting numbers from an IP address, into an easy to remember address.
	- E.g 104.26.10.229 = tryhackme.com
	![[Pasted image 20241108122007.png]]

**Domain Hierarchy**

- TLD (Top Level Domain)
	- Is the most righthand part of an address (e.g '.com')
	- There are two types of TLD
		- gTLD - Generic Top level
			- Shows a domains purpose 
				- '.com' would be commercial 
				- '.org' for an organisation
				- '.edu' for education
				- '.gov' for government
		- ccTLD - Country code top level domain
			- For geographical purposes
				- .ca for Canada
				- .co.uk for the UK ect
	-  Due to demand, there is a big influx of new gTLD ([Full List](https://data.iana.org/TLD/tlds-alpha-by-domain.txt))
- Second-level Domain
	- .com being the TLD, what comes before it is known as the second-level domain 
		- eg the 'google' in google.com
	- Limited to to 63 characters + the TLD
	- Can only use a-z, 0-9 and hyphens (cannot start or end with hyphens)
- Subdomain
	- Sits on the left of the Second-level domain using a period to separate it
		- eg admin.tryhackme.com, the 'admin' part is the subdomain
	- Has the same creation restrictions as the second-layer (63 characters ect)
	- Can use multiple subdomains to create longer names
		- eg jupiter.servers.tryhackme.com
	- Length must still be kept to 253 characters or less
	- No limit to the amount of subdomains

**Record Types

Multiple types of DNS exist, not just for websites. Common types include:

- A Record
	- These Resolve to IPv4 address' 
		- e.g 104.26.10.229
- AAAA Record
	- These resolve to IPv6 address'
		- e.g 2606:4700:20::681a:be5
- CNAME Record
	- Resolve to another domain name
		- e.g online shop has a subdomain name *store.tryhackme.com* which returns a CNAME record *shops.spotify.com*
		- Another DNS request is then made to *shops.spotify.com* to work out the IP address
- MX Record
	- Resolve to the address of the servers handling the email domain thats being queried.
		- e.g MX response for *tryhackme.com* would look like *alt1.aspmx.l.google.com
	- The records come with a priority flag
		- Tells the client which order to try the servers.
		- This is good for when the main server goes down and email needs to go to a backup server.
- TXT Server
	- Known as free text fields, where any text based data can be stored.
	- Have multiple uses
		- List servers that have the authority to send email on behalf of a domain.
			- Helps fighting against spam and spoofed email.
	- Can be used to verify ownership of a domain when signing up for 3rd party resources.

**Making a DNS request**

Steps: 
- 1. Making the request
	- The device first checks the local cache to see if the website has been visited before. If not, a request to the *Recursive DNS server is made*
- 2. Recursive DNS server
	- 'Usually' provided by the ISP (can choose your own)
	- Has local cache of domain names
		- If a result is found locally, it's sent back to the device and the request ends.
			- Commonly seen for social media sites, google ect.
	- If the request isn't found locally, the search begins starting with the internets Root DNS servers.
- 3. Root Servers
	- The DNS backbone of the internet.
	- Job is to redirect you to the correct 'Top Level Domain Server'.
		- e.g Requesting www.tryhackme.com the root server recognises '.com' (which is a Top Level Domain).
		- Then refers you to the correct TLD server that deals with .com address'
- 4. TLD Server
	- Holds the records to find the authoritative server to answer the DNS request.
		- Authoritative server is known as the 'nameserver' for the domain.
		- e.g the nameserver for tryhackme.com is:  kip.ns.cloudflare.com and uma.ns.cloudflare.com.
		- Multiple name servers are used for a domain for backup in case one goes down.
- 5. Authoritative DNS Server
	- Responsible for storing DNS records for a particular domain name
		- also where any updates to your domain name DNS records are made.
	- Depending on the record type, the DNS record is sent back to the Recursive DNS server (2)
		- This then caches for future requests and is relayed back to the original client
	- All DNS records come with a TTL value.
		- The value is a number represented in seconds that the response saves locally for when you need it again.
		- Caching saves time so the requests don't have to be made every time.

Terminal command: nslookup

nslookup --type=CNAME *webaddress*
