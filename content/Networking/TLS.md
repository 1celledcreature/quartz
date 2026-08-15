Used for secure communication across the web.
Operates at the 'transport layer' of OSI.
Eventually developed into SSL.

**Certificates**
	Every client and server needs a TLS certificate to identify itself.
	The server admin creates a Certificate Signing Request (CSR)
		This then gets submitted to the Certificate Authority which verifies and issues the digital certificate.
	The server is then identifiable by this signature
	Getting a certificate signed requires an annual fee
		https://letsencrypt.org/ will do it for free

**HTTP over TLS**
	requesting a page via HTTPS requires the following:
		TCP 3 way handshake with target server
		Establish TLS session
		Communicate using HTTP protocol (GET / HTTP/1.1)
	Example shown of HTTPS packets being caught:
		![[Pasted image 20251113135516.png]]
		 TCP session is established in the first three packets, marked with `1`. Then, several packets are exchanged to negotiate the TLS protocol, marked with `2`. `1` and `2` are where the **TLS negotiation and establishment** take place
		  HTTP application data is exchanged, marked with `3`. Looking at the Wireshark screenshot, we see that it says “Application Data” because there is no way to know if it is indeed HTTP or some other protocol sent over port 443.
	Opening the packet would contain gibberish however as an encryption key is needed:
		![[Pasted image 20251113135633.png]]

**Getting encryption keys**
	All packets are encrypted when TLS is added to HTTP.
	If you have the encryption key, this can be added to wireshark to decrypt the packets.
	The screenshot above would then look like:
		![[Pasted image 20251113140118.png]]
