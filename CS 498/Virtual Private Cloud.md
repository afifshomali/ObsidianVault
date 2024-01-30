---
tags:
  - CS498
  - CS498/Midterm1
---
---
## VPC - Virtual Private Cloud 
![[Pasted image 20240122211223.png]]
![[Pasted image 20240122211320.png]]
![[Pasted image 20240122211404.png]]
![[Pasted image 20240122211533.png]]
10.0.0.0/16 is the IP range, routing remains local 
Availability Zones are unlikely to fail at the same time so we used them to create subnets which separate our VPC internally, both get a smaller range of IP addresses
![[Pasted image 20240122211808.png]]
CIDR keeps first/highest $n$ bits, which is the number after the $/$ and the other bits can be any combination so then we get a range
![[Pasted image 20240122212059.png]]
![[Pasted image 20240122212207.png]]
![[Pasted image 20240122212314.png]]
Can have at most 11 instances deployed in the subnet 
## VPC Subnets
![[Pasted image 20240122212443.png]]
Let one subnet be private and the other be internet facing/public
![[Pasted image 20240122212530.png]]
![[Pasted image 20240122212637.png]]
![[Pasted image 20240122212810.png]]

## VPC Gateways
![[Pasted image 20240122213148.png]]
![[Pasted image 20240122213553.png]]
NAT works in the internet layer, it works to distribute packets within a VPC that need to be sent outside to the internet
![[Pasted image 20240122213602.png]]
Similar to NAT, but it is used to ssh to access machines in a VPC, like when working remotely off a companies network with your laptop
## Advanced VPC Gateways
![[Pasted image 20240122213754.png]]
![[Pasted image 20240122214113.png]]
Add line to Routing Table for VPC peering things 
![[Pasted image 20240122214323.png]]
Allows us to access services from same company without using the internet
![[Pasted image 20240122214606.png]]
![[Pasted image 20240122214615.png]]
Infrastructure owner intercepts the packets without using the link layer
## VPC Security & Firewalls

![[Pasted image 20240122214740.png]]
![[Pasted image 20240122214912.png]]
Reduce the number of ports open to the public 
![[Pasted image 20240122215042.png]]
![[Pasted image 20240122215524.png]]
![[Pasted image 20240122215534.png]]
![[Pasted image 20240122215658.png]]
This allows ec2 instances in the same security group to communicate with each other
