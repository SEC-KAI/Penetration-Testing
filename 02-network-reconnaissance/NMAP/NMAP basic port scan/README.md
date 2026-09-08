This is a continuation of my NMAP live host discovery room.
The room starts off by teaching what ports are and how they are used in nmap. It also explains what the states mean like open, closed or filtered.

Next, it tackles about the tcp headers which are URG(urgent), ACK(acknowledgement), PSH(push), RST(reset), SYN(synchronise), and FIN flags.

1. i performed a tcp connect scan wherein i complete the entire 3 way handshake to see whether the port is open or not. We send SYN, target replies with SYN ACK, then we reply with ACK and then RST, ACK to stop connection
   
2. I performed a syn scan wherein the handshake was not completed since I didnt give an ack response back.
   
3. I performed a UDP scan wherein a host that is alive might reply with an error if a port is closed and im trying to connect to it.

4.  Lastly when scanning, you can specify what ports to scan or how many ports to scan. The timing can also be changed ranging from -T0(slowest, sneakiest) to -T5 (fastest, riskier)

This was also a very fun lab very basic and simple
