1. Module completion
Shareable link
https://tryhackme.com/room/threatinteltools?
utm_campaign=social_share&utm_medium=social&utm_content=share-completed
room&utm_source=copy&sharerId=67f610481688bb843e1229a9
Completion screenshot
1
2
2. Introduction-------------------------------------------------------------------------------
This module explored the practical utilization of open-source threat 
intelligence (OSINT) tools within a modern Security Operations 
Center (SOC) framework. Investigating external threat infrastructure, 
analyzing malicious file artifacts, and dissecting email headers are 
essential skills for a security analyst tasked with triaging targeted 
infrastructure attacks. Prior to beginning this module, I expected a 
general theoretical overview of indicators of compromise (IoCs), but I 
gained direct practical experience interacting with real-world 
intelligence platforms like UrlScan.io, Abuse.ch, PhishTool, and Cisco 
Talos.
3. The work-------------------------------------------------------------------------------
3.1  Scenario 1: Email Analysis & Open-Source Triage (Task 7)
What this section covered
This section covered tactical incident triage workflows by staging a 
virtual SOC scenario. It evaluated how to analyze unverified email 
message configurations (.eml), extract embedded recipient 
properties, isolate malicious attachments, and audit their 
corresponding historical indicators using VirusTotal.
Question 1
According to Email2.eml, what is the recipient's email address?
Answer
chris.lyons@supercarcenterdetroit.com
How you got there
I launched the specialized virtual lab infrastructure and opened the 
3
pre-staged analysis environment. I loaded the target file 'Email2.eml' 
into PhishTool to extract the metadata properties from the message 
headers, immediately identifying the targeted destination email 
parameters under the recipient routing fields.
Evidence
The screenshot exhibits the completed field entry for Scenario 1 
marked as correct on the platform.
It verifies that deep header inspection successfully parsed the exact 
target user profile.
Question 2
On VirusTotal, which year recorded the first submission details of the 
mentioned file?
Answer
2017
How you got there
4
I extracted the specific cryptographic hash fingerprint from the 
attachment contained within the suspicious email structure. I 
queried this unique signature string against the unified database on 
VirusTotal, reviewing the historical entry timeline metadata to locate 
the earliest original submission log record.
Evidence
The interface logs confirm the correct answer verification flag for the 
histo
rical timeline check.
It proves that open intelligence tracking parameters can accurately 
establish the threat age profile.
3.2  Scenario 2: Advanced Malware Triage (Task 8)
What this section covered
This section built upon the incident triage workflow by evaluating a 
more complex phishing vector, demonstrating how to isolate 
weaponized spreadsheets, extract hidden macro properties, and map 
5
them to documented threat groups.
Question 1
What is the name of the attachment on Email3.eml?
Answer
Sales_Receipt 5606.xls
How you got there
I loaded the 'Email3.eml' data block into the parsing utility interface 
to evaluate the body boundaries. I isolated the multi-part data 
parameters and successfully located the exact filename string string 
under the attachment properties.
Evidence
The screenshot captures the completed answer input field for Task 8 
verified as correct.
It verifies that attachment isolation metrics successfully cataloged 
the incoming attack vector profile.
6
Question 2
What malware family is associated with the attachment on 
Email3.eml?
Answer
Dridex
How you got there
I calculated the cryptographic hash of the weaponized Excel 
spreadsheet and cross-referenced it across public threat sharing 
platforms and sandboxes. The automated signature tracking arrays 
and threat behavior analysis tags identified the payload behaviors as 
belonging to the Dridex banking trojan family.
Evidence
The platform screen panel displays a green checkmark confirming the 
correct identification of the signature family.
It proves that multi-source intelligence correlation can quickly 
7
identify active malware signatures.
4. Challenges and how you resolved them-------------------------------------------------------------------------------
The primary challenge encountered during these practical labs was 
dealing with initial file parsing friction when reading raw header 
tracking text strings before feeding them into specialized processing 
interfaces. Unstructured log data felt overwhelming at first. I 
resolved this by systematically using dedicated tools like PhishTool 
to parse structural protocol layers into organized dashboards, 
allowing me to isolate target indicators without losing context.
5. Conclusion-------------------------------------------------------------------------------
5. Conclusion-------------------------------------------------------------------------------
Completing this module has significantly advanced my defensive 
triage skills, transforming my approach from guessing threat patterns 
to executing structured, data-driven threat intelligence 
investigations. I can now confidently intercept targeted email 
delivery scripts, isolate malicious hash signatures, and leverage 
global OSINT frameworks to classify threat groups. These 
competencies directly support my core objective of engineering 
robust, proactive security perimeters capable of neutralizing 
advanced campaigns across corporate networks.
