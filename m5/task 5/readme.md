   1. Assigned ststic IP-address for Net2 and Net3 networks on Server_1  <br />
 ![1](1.png) <br />
 2. Configured DHCP-servise on Server_1, that will configure Int1 addresses,
Client_1 and Client_2. <br />
 ![2](2.png) <br />
 3. Checked the connections between VMs and Server_1 using ping and traceroute. <br />
  Traceroute needs only one hop, because Clients and Server_1 are connected directly. <br />
Ping Client 1 > Client 2  <br />
  ![3.1](3.1.png) <br />

Ping Client 2 > Client 1  <br />
  ![3.2](3.2.png) <br />

Ping Server_1 > Client 1  <br />
  ![3.3](3.3.png) <br />

Ping Server_1 > Client 2  <br />
  ![3.4](3.4.png) <br />
4. This task I divided into following steps: <br />
1) Assigned IP addresses for Client_1 lo: <br />
  ![4.1](4.1.png) <br />
2) Assigned gateways for Client_2 in routing table: <br />
  ![4.2](4.2.png) <br />
3) Added a note about о 172.17.33.1 to the routing table on Server_1: <br />
  ![4.3](4.3.png) <br /> 
4) Checked routing using traceroute utility: <br />
  ![4.4](4.4.png) <br /> 
  
5. Converted ip addresse into bin and calculated common mask and net address. <br /> 
  172.17.33.1 - 10101100.00010001.0010|0001.00000001 <br /> 
  172.17.43.1 - 10101100.00010001.0010|1011.00000001 <br /> 
Common net and mask: 172.17.32.0/20 <br /> 
Added a route to the route table on Server_1  <br /> 
 ![5](5.png) <br />

 6. Client 1 - Server_1 <br />
 ![5.1](5.1.png) <br /> 
 Client 2 - Server_1  <br />
 ![6.2.png](6.2.png) <br /> 
  Client 1 - Client_2
 ![6.3.png](6.2.png) <br /> 
 Client 2 - Client_1 <br />
 ![6.4.png](6.2.png) <br /> 

 7. Firewall is configured: <br />
 ![fw](firewall.png) <br /> 

 8. Ping is working properly: <br />
  ![8](8.png) <br />





