

* Each packet has [Source, Destination]
* When a device tries to send a packet to another:
	1) It goes from application layer to physical layer.
	2) The packets move from the local network up to the default gateway (the internet usually).
	3) Routing table is used to know if this packet matches the longest prefix (most bits), in it's routing.
	4) After the packet arrives, reverse way is happened (destination -> source).

* When router wants to send packets to specific PC (source, destination), it doesn't send to a specific PC, instead it sends to the network that this PC is in . 


![[Pasted image 20260327002114.png]]