The mapping of hostnames to IP address
is done in file **/etc/hosts**

And we can configure DNS server and search domains in **/etc/resolv.conf**

We can customize the lookup order in **/etc/nsswitch.conf**

==Record types==
**A record** = maps a domain name to an IPv4 add.
**AAAA record** = maps a domain to IPv6 add.
**CNAME record** = maps a domain name to another domain name.

**4 way communication:-**
In my system i write ping 1.1.1.1 then ->
1. 1.1.1.1 will go to DNS server.
2. Then DNS sends us IP address.
3. Then we send that IP address to web server.
4. Then it response.
Screenshot -
![[Pasted image 20260623105921.png|345]]

To add a custom dns server in Linux we need to first go in **/etc/resolv.conf** and then it is just a txt file we need to add nameserver 1.1.1.1 as it is Cloudflare public dns.

**Configure search domain**
In /etc/resolv.conf we add a search line followed by domain name.
Eg:- 
search example.com example.org

**Troubleshooting & Diagnostics Tools**
![[Pasted image 20260623120637.png]]

**Common Diagnostic Snippets**
1. Check your current active nameservers:
		**cat /etc/resolv.conf**
	
2. Clear your local DNS cache (systemd-resolved):
	     **sudo resolvectl flush-caches**

3. Force an immutable `/etc/resolv.conf` (Locks down files against automated tools overwriting your changes):
			**sudo chattr +i /etc/resolv.conf**
