

## Classful -> (old system)
*  means that we use classes to determine subnet mask.
* IP like `211.x.x.x` -> class C 
* So mask should be:
	`255.255.255.0 /24`
* In this system the first `byte` determines the class type.

![[Pasted image 20260322213509.png]]



## Classless (CIDR) -> (today system)

* CIDR:  Classless Inter-Domain Routing, is an efficient IP address allocation method introduced in 1993 that replaces the old classful networking system (Classes A, B, C). By using Variable Length Subnet Masking (VLSM) and prefix notation (e.g., /24), it allows flexible, smaller, and custom-sized subnets, which prevents wasted IP addresses and improves routing efficiency on the internet.
* That means:
	* Any IP can use **any subnet mask**.
	* Classes are basically **ignored**

* So is this valid:
	```bash
		IP: 211.191.32.75  --> even 211 is in class C
		Mask: 255.255.0.0 (/16)
	```
	