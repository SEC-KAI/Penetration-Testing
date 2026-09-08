This is a simple lab that I did wherein I made a counter.sh file with a code in it that pings devices whos in scope of your code.
The way it works is that there is a counter and it increments each time. For every increment, it sends out a ping to the address
it currently has. If the device recieved a response, it will conclude that it is alive and it will display that it is 
reachable. One flaw to this is that it doesnt evade firewalls so if a firewall blocks icmp, then the program will assume its
not alive.
