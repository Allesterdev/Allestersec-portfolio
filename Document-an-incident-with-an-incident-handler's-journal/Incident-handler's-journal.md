
# Incident handler's journal

### Entry: 1
### Date: 11-30-2025
### Description: 
On a Tuesday morning at approximately 09:00 AM, the clinic experienced a critical security incident resulting in a complete operational shutdown. Staff reported an inability to access workstations and essential files, including patient medical records. Ransom notes displayed on screens indicated that data had been encrypted by an organized threat group targeting the healthcare sector, demanding payment for decryption. The breach originated from targeted phishing emails containing malicious attachments that installed malware upon download. In response, the organization was forced to power down computer systems and contact external agencies for technical assistance and incident reporting.
### Tool(s) used: 
Information not provided.
### The 5 Ws of the Incident:
 - Who caused the incident? A malicious actor or organized threat group.

 - What happened? The clinic suffered a ransomware attack that encrypted critical files and disrupted business operations.

 - When did the incident occur? On a Tuesday at approximately 09:00 AM.

 - Where did the incident occur? At a small healthcare clinic located in the United States.

 - Why did the incident occur? The incident occurred because a staff member fell victim to a social engineering attack via a targeted phishing email containing a malicious attachment.
### Additional notes:
The root cause was a successful social engineering attack, highlighting the need for mandatory Security Awareness Training for all staff. Furthermore, an immediate audit of backup systems is required to ensure patient data can be restored without engaging with the threat actors.

---

### Entry: 2
### Date: 07-20-2022
### Description: 
The SOC received an alert regarding a suspicious file download on an HR workstation. Investigation confirmed a successful spearphishing attack. An employee received an email with the subject "Re: Infrastructure Egnieer role" from an external sender using a high-risk TLD (.su). The email contained a password-protected archive (password provided in the body) to evade email gateway scanning. The user manually downloaded and executed the attachment bfsvc.exe, which corresponds to the Flagpro malware family. The malware successfully executed and attempted to establish communication with external Command and Control (C2) infrastructure at org.misecure.com.
### Tool(s) used: 
VirusTotal (Intelligence enrichment), SIEM (Alerting), Email Gateway Logs (Evidence retrieval).
### The 5 Ws of the Incident:
 - Who caused the incident? The APT group BlackTech, known for using the Flagpro malware family.

 - What happened? A targeted spearphishing attack delivered a malicious downloader via a password-protected zip file, leading to the execution of bfsvc.exe.

 - When did the incident occur? On Wednesday, July 20, 2022, at 09:30:14 AM.

 - Where did the incident occur? On an endpoint belonging to the HR department (hr@inergy.com) within the corporate network.

 - Why did the incident occur? The incident occurred because the threat actor used defense evasion techniques (password-protected attachment) to bypass automated security controls, and the user failed to identify social engineering indicators (suspicious sender domain .su and  unsolicited attachment).

### Additional notes: 
The primary failure point was the human element combined with the inability of the Email Gateway to inspect encrypted archives. Immediate action is required to block the C2 domain org.misecure.com and the IP 87.248.202.1 at the perimeter firewall. The infected host must be isolated and reimaged. Recommend updating email policies to flag or quarantine password-protected attachments from external sources.

---

### Entry: 3
### Date: 04-12-2025
### Description:
Execution of network forensic analysis and traffic capture procedures within a controlled Linux environment. Active network interfaces were identified, followed by live packet capture using the tcpdump command-line tool. The objective was to intercept HTTP traffic (Port 80) synthetically generated via curl, store the data in a pcap file (capture.pcap), and perform Deep Packet Inspection (DPI) of headers and payloads in Hexadecimal and ASCII formats to identify communication patterns without alerting potential external actors (name resolution disabled).

### Tool(s) used:
tcpdump (Capture & Filtering), ifconfig (Interface Enumeration), curl (Traffic Generation), Linux CLI.

### The 5 Ws of the Incident:

 - Who performed the action? The Security Analyst (User analyst) during a training/audit session.

 - What happened? Successfully captured 9 packets of TCP/IP traffic filtering by port 80, avoiding DNS name resolution to maintain operational discretion (-nn). Raw data from the .pcap file was subsequently analyzed using read filters.

 - When did the incident occur? During the assigned maintenance/lab window for connectivity testing.

 - Where did the incident occur? On the primary Ethernet interface (eth0) of the analyst's Linux workstation.

 - Why did the incident occur? Proactive activity to validate network visibility capabilities and practice packet filtering syntax required for future malware or intrusion investigations.

### Additional notes: 
Confirmed the critical importance of the -nn flag in tcpdump as an Operational Security (OPSEC) measure to prevent reverse DNS lookups from alerting attackers during a live investigation. Hexadecimal analysis (-X) allowed for visualization of the packet payload, validating that the captured traffic corresponded to a standard HTTP request. The procedure is validated and ready for application in real-world incidents.

---

### Entry: 4
### Date: 03-12-2025
### Description:
Conducted operational testing and configuration of the Suricata Intrusion Detection System (IDS). The objective was to validate signature-based detection capabilities by analyzing pre-recorded network traffic (sample.pcap). A custom detection rule was authored and deployed to flag specific HTTP traffic patterns. Post-execution analysis involved examining alert generation in legacy logs (fast.log) and parsing rich telemetry data within the standard JSON output (eve.json) using command-line JSON processors.

### Tool(s) used:
Suricata (IDS Engine), jq (JSON processing), Linux CLI, sample.pcap (Traffic Replay).

### The 5 Ws of the Incident:

 - Who performed the action? The Security Analyst (User analyst) within the local testing environment.

 - What happened? Suricata was executed in offline mode (-r) to process a pcap file using a custom signature (SID: 12345). The engine successfully triggered alerts upon detecting HTTP "GET" methods egressing from the local network ($HOME_NET) to external destinations ($EXTERNAL_NET).

 - When did the incident occur? During the designated signature development and testing window.

 - Where did the incident occur? The Linux workstation, specifically processing data from /home/analyst and generating logs in /var/log/suricata.

 - Why did the incident occur? To verify the logic of custom IDS rules and to practice correlating events using unique flow_id values in JSON logs for threat hunting purposes.

### Additional notes:
The custom rule was validated: alert http $HOME_NET any -> $EXTERNAL_NET any (msg:"GET on wire"; flow:established,to_server; content:"GET"; http_method; sid:12345; rev:3;). It was observed that while fast.log provides a quick summary, it is deprecated for deep analysis. The eve.json file is the primary source for incident response, containing critical metadata (Flow IDs, timestamps, protocol details). The utility jq proved essential for filtering this verbose data to isolate specific conversation flows.
