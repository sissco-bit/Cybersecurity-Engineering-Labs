1. Module completion
Shareable link
https://academy.hackthebox.com/achievement/1738064/19
Completion screenshot
1
2
2. Introduction-------------------------------------------------------------------------------
This module provided a comprehensive deep dive into network 
reconnaissance, architectural mapping, and enumeration using the 
industry-standard tool Nmap. Understanding scanning mechanics is a 
critical baseline skill for any security analyst, as every offensive 
assessment phase and defensive firewall rule relies entirely on 
accurate host visibility. Prior to beginning this module, I expected to 
learn simple script commands, but I gained an advanced tactical 
understanding of timing states, signature banner parsing, and 
complex firewall evasion strategies.
3. The work-------------------------------------------------------------------------------
3.1  Host and Port Scanning (Section 4 / 12)
What this section covered
This section explored the structural mechanics of TCP port 
3
enumeration, highlighting how to scan all 65,535 possible 
communication sockets on a target machine, interpret three-way 
handshake packet responses, and accurately pull system host 
parameters.
Question
Find all TCP ports on your target. Submit the total number of found 
TCP ports as the answer.
Answer
7
How you got there
To sweep all ports efficiently without hitting structural timing delays 
or firewall retransmission freezes, I appended aggressive rate
limiting and timing parameters to force a rapid scan queue:
$ sudo nmap -p---min-rate 5000 -T4 10.129.130.62
The console completed data parsing within seconds and exposed 
exactly 7 open listening TCP ports on the destination host.
Evidence
4
It proves that proper optimization switches successfully bypassed 
processing bottlenecks to locate all active port states 
3.2  Saving the Results (Section 5 / 12)
What this section covered
This section evaluated the documentation workflows necessary for 
professional technical reporting, demonstrating how to save raw 
scanner metrics into XML formats and systematically convert them 
into interactive client HTML files using processing engines.
Question
Perform a full TCP port scan on your target and create an HTML 
report. Submit the number of the highest port as the answer.
Answer
31337
5
How you got there
I initiated a rapid full-range scan on the active target address, 
redirecting the results directly into an structured XML schema file. 
Following this, I invoked the xsltproc utility to cleanly map the XML 
schema into a clean frontend HTML web layout report:
$ sudo nmap -p---min-rate 5000 -oX target_results.xml 10.129.x.x
$ xsltproc target_results.xml -o nmap_report.html
Opening the file structure revealed that the highest active listening 
port on the target machine was 31337.
Evidence
It proves that the conversion parsing logic successfully cataloged the 
extreme boundaries of the target's listening space 
3.3  Nmap Scripting Engine (Section 7 / 12)
What this section covered
This section evaluated the automation capabilities of the Nmap 
6
Scripting Engine (NSE) using custom Lua scripts to interact with 
backend network applications, extract deep configuration 
definitions, and audit hidden server assets.
Question
Use NSE and its scripts to find the flag that one of the services 
contain and submit it as the answer.
Answer
HTB{873nniuc71bu6usbs1i96as6dsv26}
How you got there
I verified the open web services on the target machine and targeted 
the hidden directories on the server. I utilized the command-line curl 
utility to directly fetch and analyze the web root's robots.txt access 
control policy file:
$ curl http://10.129.130.62/robots.txt
The request parsed the remote asset immediately and exposed the 
custom system target confirmation flag string at the base of the file 
content.
Evidence
The terminal display captures the curl response payload exposing the 
plaintext flag array 
7
It verifies that information exposure diagnostics successfully 
intercepted hidden administrative file records 
3.4  Firewall and IDS/IPS Evasion - Medium Lab (Section 11 / 12)
What this section covered
This section explored firewall bypass methods, testing structural 
approaches to bypass rigid boundary filter rules by transitioning 
across transport layer protocol definitions and utilizing unmonitored 
ports.
Question
After the configurations are transferred to the system, our client 
wants to know if it is possible to find out our target's DNS server 
version. Submit the DNS server version of the target as the answer.
Answer
HTB{GoTtgUnyze9Psw4vGjcuMpHRp}
8
How you got there
Because standard TCP connection request streams were dropped 
silently by the protective firewall rules, I shifted the operational 
strategy to target the UDP layout. Since DNS natively handles 
lightweight lookups on Port 53 over UDP, I initiated a targeted UDP 
service version banner enumeration request:
$ sudo nmap -sU -p 53 -sV 10.129.x.x
The scan bypassed the filtering rule layout and exposed the exact 
service flag embedded directly in the version identity results.
Evidence
The screenshot highlights the successful verification status for the 
Section 11 practical challenge lab 
9
It proves that protocol shift strategies can safely maintain scanning 
visibility through restricted network boundaries 
4. Challenges and how you resolved them-------------------------------------------------------------------------------
The primary challenge encountered during this module was handling 
extreme timing timeouts and freezes while executing full 65,535 port 
sweeps against firewalled systems that drop packets. Standard 
commands hung indefinitely. I resolved this friction by mastering 
advanced rate tuning and execution metrics, specifically configuring 
the --min-rate 5000 boundary switch and the -T4 timing matrix to 
force rapid data transmission and maintain momentum.
5. Conclusion-------------------------------------------------------------------------------
Completing this module has significantly advanced my architectural 
10
scanning capabilities, transforming my approach from blindly 
running basic commands to executing highly targeted, evasion-aware 
network enumeration. I can now confidently configure multi-format 
automated script scans, build interactive HTML client validation 
deliverables, and engineer bypass techniques to test hardened 
perimeters. These core competencies directly support my career goal 
of building resilient, enterprise-grade continuous security monitoring 
services to protect infrastructure on the continent.
