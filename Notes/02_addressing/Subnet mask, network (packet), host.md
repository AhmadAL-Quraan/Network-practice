
```table-of-contents
title: 
style: nestedList # TOC style (nestedList|nestedOrderedList|inlineFirstLevel)
minLevel: 0 # Include headings from the specified level
maxLevel: 0 # Include headings up to the specified level
include: 
exclude: 
includeLinks: true # Make headings clickable
hideWhenEmpty: false # Hide TOC if no headings are found
debugInConsole: false # Print debug info in Obsidian console
```

## Subnet mask

* It tells us how many bits are used NOW for network and host.
* It doesn't tell us the what is the original network is (it's must be stated).
* **Devices in same network should have the same subnet mask**
* Each byte here called `octet`
* It's a way to determine the network bytes from the host bytes.
* `255.255.0.0`: Means the first 2 bytes determines the network, the last two determines the host.
* Another representation of it: `192.1.1.1 / 24` -> here 24 means 24 bits for network and 8 bits for host ->` 255.255.255.0`, so the first 3 bytes determines the network.
* **All 1s first, then all 0s (no mixing)** and it's from left to right.

```
255.251.245.0 (wrong subnet mask)
255.245.0.0 (wrong subnet mask) --> all bits should be 1's then 0's (no mixing)

```
 
 > Only valid values per octet: 255, 254, 252, 248, 240, 224, 192, 128, 0

* when we say `0 - 31` IP addresses we means that the total number of addresses are 32 because `31 - 0 + 1 = 32` i.e we use counting.

>[!note] In networking we deal with bits from left to right 

### What if the last byte in subnet mask wasn't 255 ?




* If I have this subnet mask `255.255.255.224` --> 224: `1 1 1 0 0 0 0 0` 
	* **Info 1**: This means that the number of bits determines the network is: 8 + 8 + 8 + 3 = 27
	* **Info 2**: The number of hosts in this case will be `2 ^ 5 (bits remaining) -2 = 30 hosts`
	* **Info 3**: In this case we have **divided the large network into subnets (sub-networks)**, so to know how many subnets we have: `2 ^ Number of bits taken from the host`, in this case we have 3 bits from the host i.e `1 1 1`, so total 8 subnets.
	* **Info 4:** To know the IP range for each subnet = `256 - subnet mask value (224 in above example)`. So it's `32` addresses for each subnet.
	> [!note]Block size = `256 - subnet mask value`
	* **Info 5**: each subnet has it's like it has it's own network so same rules for whole network i.e `255.255.255.0`
	```bash
	subnet 1 range 0 - 31 --> available host range 1 - 30  (remove 0 and 31)  
	
	subnet 2 range 32 - 63 --> available host range 33 - 62 (remove 32 and 63)
	
	subnet 3 range 64 - 95  --> availabe host range 65 - 94 ...
	```

> Remove means that each subnet has it's own network so if host bits are 0's then **network address** and if it's 1's then **broadcast**.


>[!note] If two devices have the same **network address**,  then they are in the same **subnet/network**

>[!note] You don't talk about **how many subnets** until you know the original network which should be given. OR you can assume.

---

## Host 

* You can choose any bytes for the host (in host bytes), except there is some exceptions:
	1) All host bits are `1`: Means **broadcast** .
	2) All host bits  are `0`:  **Entire network itself**, It is **NOT assigned to any device** .



---


## Network 

* The **Pdu** for this layer is **packet**.
* The packet has two important info:
	1) **Destination IP (y)** NEVER changes  
	2) **Next hop (x)** changes at each step

## 📦 What’s inside the packet?


![[Pasted image 20260326230039.png]]
When your computer sends a packet:
- **Destination IP = y** (final target, e.g. `91.198.14.1`)
- **Next hop = x** (e.g. your router)
👉 The packet still says:
> “I want to go to `91.198.14.1`






