
## Incident handler's journal

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

Entry: 2

Date: 07-20-2022

Description: The SOC received an alert regarding a suspicious file download on an HR workstation. Investigation confirmed a successful spearphishing attack. An employee received an email with the subject "Re: Infrastructure Egnieer role" from an external sender using a high-risk TLD (.su). The email contained a password-protected archive (password provided in the body) to evade email gateway scanning. The user manually downloaded and executed the attachment bfsvc.exe, which corresponds to the Flagpro malware family. The malware successfully executed and attempted to establish communication with external Command and Control (C2) infrastructure at org.misecure.com.

Tool(s) used: VirusTotal (Intelligence enrichment), SIEM (Alerting), Email Gateway Logs (Evidence retrieval).

The 5 Ws of the Incident:

 - Who caused the incident? The APT group BlackTech, known for using the Flagpro malware family.

 - What happened? A targeted spearphishing attack delivered a malicious downloader via a password-protected zip file, leading to the execution of bfsvc.exe.

 - When did the incident occur? On Wednesday, July 20, 2022, at 09:30:14 AM.

 - Where did the incident occur? On an endpoint belonging to the HR department (hr@inergy.com) within the corporate network.

 - Why did the incident occur? The incident occurred because the threat actor used defense evasion techniques (password-protected attachment) to bypass automated security controls, and the user failed to identify social engineering indicators (suspicious sender domain .su and  unsolicited attachment).

Additional notes: The primary failure point was the human element combined with the inability of the Email Gateway to inspect encrypted archives. Immediate action is required to block the C2 domain org.misecure.com and the IP 87.248.202.1 at the perimeter firewall. The infected host must be isolated and reimaged. Recommend updating email policies to flag or quarantine password-protected attachments from external sources.
