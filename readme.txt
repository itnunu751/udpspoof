I used the python package scapy to create and send packets.
I encapsulated the packet with an ethernet layer, IP layer, and a UDP layer. As the body of the packet, I sent my IP address so that the server would know where to send a packet to per the directions. 

sendp(Ether(…)/IP(...)/UDP(...)/[my-ip-address])

The source IP address should be the spoofed address that is the only trusted IP: 10.2.4.10. 

The destination IP address is the IP address of the FlagServ that I found when I connected using openvpn: 172.16.44.1

I added ports as I was getting a port unreachable error: source port 13333 (randomly chose this) and dport 13337 per the directions. 