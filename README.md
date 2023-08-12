# DHCP_Starvation_Attack
DHCP starvation attack is an attack that targets DHCP servers whereby forged DHCP requests
are crafted by an attacker with the intent of exhausting all available IP addresses
that can be allocated by the DHCP server. Under this attack, legitimate network users can be denied service.

This attack can done by sending alot or infinite DHCP Discover packets.
Or by leasing all the scope of the DHCP Server.
I choose to do that by the second option, since we have to show a lease for one of our requests in question 4.
To do that we have to understand the process of DHCP leasing.
The client send a DHCP Discover Packet, Then the server sends DHCP Offer Packet,
Then the client send DHCP Request packet, Then the server sends DHCP ACK Packet.
In my code first we have to choose an interface, Then the program sends DHCP Discover Packet,
Then sniffing or listening to DHCP Offer for 10 seconds. If there is no answer that means that the server
Have no fre lease. Then if there is an answer the program sends DHCP Request packet,
Then it fakes DHCP ACK Packet.

I add the ability to wait more than 10 seconds by deleting the timeout
from the sniffing line (explained in the comments of the code)

Also, this program doesn't continue to flood the server with DHCP Discover requests, for me, it was enough here.
There is explanation in the code comments of the main function how to do that.
