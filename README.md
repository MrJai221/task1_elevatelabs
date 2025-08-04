Basic Reconnaissance : Using Nmap and Wireshark .

Some commands to scan the ip for ports which are open and close : 

The following command is for scan the network IP and show the hosts. 
nmap -sn 192.168.1.0/24

The following command to scan the open ports .
nmap -sS 192.168.1.10 -oN open_ports.txt
Note : "-oN file.txt "  is for where the output will be saved.

some more related scans : 

nmap -sS --top-ports 100 -T4 192.168.1.0/24     : which scan all the imp or top ports of the network.

nmap -sS -Pn -p- 192.168.1.10                             : It scans all ports on a specified network.


Some information about the Scanning and Flags : 

Flag	                           Meaning
-sS	                          TCP SYN scan (stealthy and fast)
-Pn	                          Skip ping, assume host is online
-p-	                          Scan all ports (1–65535)
--top-ports 100	  Scan top 100 most common ports
-T4	                          Use aggressive timing (faster scan)
-sn	                          Ping scan only (no port check)
-oN	                          Output to file in normal format




Wireshark :

Filter Traffic :

Filter	                            What it Shows
http	                                    Only HTTP traffic
ip.addr == 192.168.1.10	    Packets involving a specific IP
tcp.port == 80	            Packets over TCP port 80 (web traffic)
icmp	                            Ping packets (e.g., from ping command)
dns	                                    Only DNS queries/responses
