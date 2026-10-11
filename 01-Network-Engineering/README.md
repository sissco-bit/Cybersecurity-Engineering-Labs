1. Module completion
Paste the shareable link the platform gives you when you finish, then the completion screenshot.

Shareable link
https://academy.hackthebox.com/achievement/1738064/34
Completion screenshot
[ paste screenshot here ]
2
3. Introduction
This module provided a comprehensive foundation in network 
architecture, protocols, 
and basic mathematical calculation frameworks for subnets. 
Understanding these 
core networking concepts is absolutely vital for a security analyst 
because every 
adversarial action, malicious payload, and defensive telemetry 
signal depends entirely 
on network pathways. Prior to beginning this module, I expected 
to gain clarity 
on how data is segmented and routed, as well as how to 
systematically calculate 
subnet barriers to limit network visibility and isolate potential 
host exposures
4. The work
3.1   3.1  Subnetting
3
What this section covered:
This  section explored the methodology of dividing a contiguous block of IPv4 addresses 
into smaller, isolated logical network spaces. It covered the mechanics of separating 
the network part from the host part using custom subnet masks, determining network 
boundaries, and calculating host ranges manually using powers of two and modulo 
operati
Question 1
Submit the decimal representation of the subnet mask from the following CIDR: 10.200.20.0/27
Answer
255.255.255.224
How you got there
1. The CIDR notation specifies that the first 27 bits are turned "on" (1s) to represent the 
network portion.
2. Writing this out in binary across 4 octets yields: 
11111111.11111111.11111111.11100000.
3. Converting each binary octet into decimal notation gives:
* 1st, 2nd, and 3rd Octet = 255
* 4th Octet = 128 + 64 + 32 = 224
4. Combining the segments yields the complete decimal subnet mask: 255.255.255.224.
Evidence
4
The screenshot shows the Hack The Box Academy interface for Section 10 with a green checkmark next to Question 1.
Question 2
Submit the broadcast address of the following CIDR: 10.200.20.0/27
Answer
10.200.20.31
How you got there
5
1. A /27 subnet mask uses 27 bits for the network, leaving 5 bits remaining for the host portion (32 - 27 = 5).
2. The total block size size is calculated as 2^5 = 32 addresses.
3. Since the network address starts at 10.200.20.0, the total address span for this block runs from .0 to .31.
4. To find the broadcast address, we flip all 5 host bits to 1s, which gives the very last address in the pool: 
10.200.20.31.
Evidence
The screenshot captures the completed field input for Question 2 with a verified submission status indicator.
It proves that the boundary analysis correctly isolates the terminal broadcast address for the block.
Question 3
Split the network 10.200.20.0/27 into 4 subnets and submit the network address of the 3rd subnet as the answer.
Answer
6
10.200.20.16
How you got there
1. To split an existing network space into 4 smaller subnets, we apply the formula: 2^n >= 4. This means we must 
borrow an additional 2 bits (2^2 = 4).
2. The new classless subnet mask increases from the baseline /27 by 2 bits, becoming /29.
3. With a /29 mask, the remaining host bits drop to 3 (32 - 29 = 3), resulting in a precise increment block size of 2^3 = 
8 addresses per subnet.
4. Starting from the original base address (.0), we step up sequentially by 8 to map our subnets:
* Subnet 1 Network Address: 10.200.20.0
* Subnet 2 Network Address: 10.200.20.8
* Subnet 3 Network Address: 10.200.20.16
* Subnet 4 Network Address: 10.200.20.24
Question 4
7
Split the network 10.200.20.0/27 into 4 subnets and submit the broadcast address of the 2nd subnet as the answer.
Answer
10.200.20.15
How you got there
1. Using our calculations from Question 3, each of the four newly created /29 subnets has a block step size of 8 
addresses.
2. Subnet 2 begins exactly at the Network ID address 10.200.20.8.
3. Subnet 3 begins directly after it at the Network ID address 10.200.20.16.
4. Since the broadcast address of a subnet is always exactly one increment position below the next network's ID 
address, we simply subtract 1 from Subnet 3's starting point: 16 - 1 = 15. This yields a final broadcast parameter of 
10.200.20.15.
8
4. Challenges and how you resolved them
The primary challenge faced during this module was tracking custom 
binary bit 
borrowing boundaries without making calculation errors in the final 
octet. 
Initially, I mixed up host capacities by forgetting to subtract the 
Network ID 
and Broadcast addresses. I resolved this by drafting out the block 
sizes manually 
on paper and cross-verifying the boundaries using structural 
mathematical checks 
to make sure no IP spaces overlapped.
5. Conclusion
Completing this module has significantly advanced my engineering 
perspective 
from blindly running scanning utilities to understanding how packet 
data travels 
9
across network interfaces. I can now confidently analyze a classless 
prefix, map 
active listening ports to their underlying services, and calculate 
functional 
subnetworks. This structural clarity will immediately help me 
interpret raw traffic 
captures, configure firewall boundaries, and trace data movements 
as a security 
