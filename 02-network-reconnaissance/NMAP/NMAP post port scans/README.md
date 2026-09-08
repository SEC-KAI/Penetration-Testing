This is the last part of the NMAP module.

1. Used -sV to scan the version of the ports. Note that when using -sV, you are initiating a 3 way handshake in order to get the version of the open port. But initially, u can use -sS to be stealthy and find out open first and then use -sV to find version like nmap -sS -sV -p- target_ip. Version level can be changed by using --version-(intensity). like --version-light,
--version-all

2. OS detection, the way nmap discovers OS version is by checking values that the target responds with and matches it with the key that would match the OS. for example TTL values like 64 can be linux while 128 windows, ICMP behaviour, TCP window sizes and more. -O is used. Traceroute can also be added using -traceroute which determines the number of hops it took from ur machine to target machine

3. NMAP scripting engine. nmap has lots of scripts and they are stored in /usr/share/nmap/scripts. the default script (-sC) contains lots of scripts like vuln, malware, and many more. if you want to use specific scripts from the /usr/share/nmap/scripts. example scriptname is dns-brute.nse, do nmap -script "dns-brute" target-ip. 

4. Its important to save the outputs of the scan in a file so you can just view them instead of performing a scan again. U can do normal -oN, grepable -oG, and xml -oX.
