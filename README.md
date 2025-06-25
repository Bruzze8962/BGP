# BGP
# Configuration of BGP on Packet Tracer
* The goal of this lab is to configure routing between organizations using EBGP for single home to branch connectivity (AS)
*The end result will be BGP peering Router 1 and SPR1, Router 1(R1) will advertise routes to the Internet Service Provider Router
* The first step is to evaluate the current router on the routers using the " sh ip route" command in global configuration mode 
* The second step is to enter BGP configuration mode using the "BGP router" command in addition to adding the correct AS number associated with that router
* The third step is to create tcp connection with SPR1 using the "neighbor 100.0.0.1(ip of SPR1) remote-AS 650001( AS of SPR1)
* The fourth step is to statically configure neighbors due to the fact the EBGP does not peer dynamically, therefore the loopback addresses will be statically configured as neighbors along with     the 10.0.0.0 / 16 network.
* The 10.0.0.0/16 doesn't exist in the routing table, therefore you must create it using the "10.0.0.0. 255.255.0.0. null 0" the ip address is not assigned to an interface but it willl force all    traffic destined for ip addresses in that network to be resolved to interfaces with more specific ip network masks (10.0.12.0/30 ,10.0.13.0/30 ,10.0.23.0/30)
* To configure the BGP peering with SPR1 and Router 1 you must use the "neighbor 1.1.1.1 mask 255.255.255.255" command, BGP doe not use inverted masks like OSPF and RIP, do the same for the other routers with loopback addresses
* To advertise multiple networks in the 10.0.0.0./16 network you will use the "network 10.0.0.0 mask 255.255.0.0.) to advertise the 10.0.12.0, 10.0.13.0, 10.0.23.0 command
* Use the show commands "do sh ip route" or "sh ip route" to verify the existence of desired BGP routes 
* Ping SPR1 for desired connectivity 
* BGP is great for scalability, it updates if triggered but it relies heavily on policy and filtering. 

<img width="1512" alt="Image" src="https://github.com/user-attachments/assets/2d1cf3f1-0aca-44ca-899b-0c4ddd6bd90f" />

