

 
The **default gateway** is the router that a host (or router) sends packets to **when it doesn’t have a more specific route for the destination network**.
* If the destination IP is **not in the same local network**, send it to the default gateway.
### 💡 Key takeaway

- **Local network?** → send directly
- **Not local?** → send to default gateway


>[!note] The next hop must be on the same local network for the device.

* `0.0.0.0/0` -> default : means match ALL IP addresses.
	* - Matches **all IP addresses**
	- Acts as a **catch-all**
Ex:
![[Pasted image 20260327010144.png]]
1. Check routing table
2. No specific route found
3. Matches:
    `0.0.0.0/0`
4. So:  
    👉 Send packet to `10.0.0.254`


> [!note] Default route is only used when **no direct or specific route exists**

## 🎯 Rule

1. Check routing table
2. Find best match (longest prefix)
   - If it's directly connected (same router) → send directly
   - Else → send to next hop
3. If no match → use default route
4. If no default → drop packet

Ex:
![[Pasted image 20260327011246.png]]
* Here router has 3 interfaces, so to send from an interface to specific one, the other interfaces will be part of the routing table of the **router**.

* Routing table for the picture above:
```
10.0.0.0/24
7.8.10.0/28
192.168.0.0/24
default -> 169.159.234.62 (it's the isp in this case)
```