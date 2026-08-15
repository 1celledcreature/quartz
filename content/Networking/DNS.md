Dns operates at Layer 7 of OSI (application layer).
Using UDP port 53.

Some examples of DNS records:

*'A' record*
	Maps a hostname to one or more IPv4 address' 
		e.g. example.com could resolve to 172.17.2.172

*'AAAA' Record*
	Similar to 'A' but refers to IPv6

*CNAME Record* (Canonical name)
	maps a domain to another domain
		e.g. www.example.com can be mapped to "example.com" or even to "example.org"

*MX Record* (Main Exchange)
	Specifies the mail server responsible for the emails of the domain

