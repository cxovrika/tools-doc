## TCP Connect scans (-sT)
Performs full three way handshake

## SYN scans (-sS)
SYN scans are sometimes referred to as `Half-open` scans, or `Stealth` scans.

Where TCP scans perform a full three-way handshake with the target, SYN scans sends back a RST TCP packet after receiving a SYN/ACK from the server (this prevents the server from repeatedly trying to make the request).

## UPD scans (-sU)
When a packet is sent to an open UDP port, there should be no response. When this happens, Nmap refers to the port as being open|filtered. In other words, it suspects that the port is open, but it could be firewalled. If it gets a UDP response (which is very unusual), then the port is marked as open. More commonly there is no response, in which case the request is sent a second time as a double-check. If there is still no response then the port is marked open|filtered and Nmap moves on.

When a packet is sent to a closed UDP port, the target should respond with an ICMP (ping) packet containing a message that the port is unreachable. This clearly identifies closed ports, which Nmap marks as such and moves on.

## NULL, FIN and Xmas
* **NULL** - As the name suggests, NULL scans (-sN) are when the TCP request is sent with no flags set at all. As per the RFC, the target host should respond with a RST if the port is closed.

* **FIN** - FIN scans (-sF) work in an almost identical fashion; however, instead of sending a completely empty packet, a request is sent with the FIN flag (usually used to gracefully close an active connection). Once again, Nmap expects a RST if the port is closed.

* **Xmas** - Xmas scans (-sX) send a malformed TCP packet and expects a RST response for closed ports. It's referred to as an xmas scan as the flags that it sets (PSH, URG and FIN) give it the appearance of a blinking christmas tree when viewed as a packet capture in Wireshark.

There are a variety of other switches which Nmap considers useful for firewall evasion. They can be found [here](https://nmap.org/book/man-bypass-firewalls-ids.html).



## ICMP Network Scanning
To perform a ping sweep, we use the `-sn` switch in conjunction with IP ranges which can be specified with either a hypen (-) or CIDR notation. i.e. we could scan the 192.168.0.x network using:
```
nmap -sn 192.168.0.1-254
or
nmap -sn 192.168.0.0/24
```

## NSE Scripts
The Nmap Scripting Engine (NSE) is an incredibly powerful addition to Nmap, extending its functionality quite considerably. NSE Scripts are written in the Lua programming language, and can be used to do a variety of things: from scanning for vulnerabilities, to automating exploits for them. The NSE is particularly useful for reconnaisance, however, it is well worth bearing in mind how extensive the script library is.

There are many categories available. Some useful categories include:

* safe - Won't affect the target
* intrusive - Not safe: likely to affect the target
* vuln - Scan for vulnerabilities
* exploit - Attempt to exploit a vulnerability
* auth - Attempt to bypass authentication for running services (e.g. Log into an FTP server anonymously)
* brute - Attempt to bruteforce credentials for running services
* discovery - Attempt to query running services for further information about the network (e.g. query an SNMP server).


A more exhaustive list can be found [here](https://nmap.org/book/nse-usage.html).





