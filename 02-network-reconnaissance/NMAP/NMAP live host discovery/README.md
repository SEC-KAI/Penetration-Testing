This folder contains the documentation of the room I completed in TRYHACKME's NMAP live host discovery. 
The room started with the concept of subnetworks. Subnets are basically a divided part of a network.
Then the next topic covers the concept of arp, ping and tcp
next, the room tackled enumerating commands that would list which ip was affected by the ping. This does not yet check wether hosts are alive or not.
Commands mentioned were:
-sL = lists out ip that was pinged
-n = disables reverse dns lookups 

Then the fun part starts when I started discovering host layer by layer. 
Starting from the layer 2 which uses ARP to check which devices are alive inside the network.
Commands mentioned were:
-PR = performs arp to check alive host
-sn = says not to perform port scanning 
by default, you dont have to include the -PR for the scan to work since -sn chooses which method would be best depending on the situation.

Then for layer 3 I used ICMP to check alive host. In some cases, this wont work since some devices has firewalls blocking icmp traffic so you should try multiple methods in discovering live hosts. 
Commands mentioned were:
-PE = icmp echo ping
-PP = icmp timestamp ping
-PM = icmp address mask ping

lastly, we have layer 4 wherein TCP and UDP methods were used. For TCP we have SYN ping wherein the 3 way handshake isnt completed since the ack response wasnt provided by the client. Then we have ACK ping wherein the client sends an ACK reply to a port and since no connection was established initially, it would reply with an RST. A device replying with an RST usually means the host is alive but that is not always the case. For UDP ping, an uncommon port is used since if we use a common port like 52 and that port is open, then that device wont reply anything back since UDP is connectionless. If we used a port like 52343 and that port is closed, then the device will send an error message back saying that the port is closed which can indicate the host is alive.
commands mentioned were:
-PS = SYN ping
-PA = ACK ping
-pu = UDP ping

This room was very fun to play around with and I think would be very useful in the long run.
