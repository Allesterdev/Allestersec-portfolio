## Scenario

You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services. 

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack. 

To address this security event, the network security team implemented: 

 -A new firewall rule to limit the rate of incoming ICMP packets

 -Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets

 -Network monitoring software to detect abnormal traffic patterns

 -An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity event and integrate your analysis into a general security strategy. We have broken the analysis into different parts in the template below. You can explore them here:

 -Identify security risks through regular audits of internal networks, systems, devices, and access privileges to identify potential gaps in security. 

 -Protect internal assets through the implementation of policies, procedures, training and tools that help mitigate cybersecurity threats. 

 -Detect potential security incidents and improve monitoring capabilities to increase the speed and efficiency of detections. 

 -Respond to contain, neutralize, and analyze security incidents; implement improvements to the security process. 

 -Recover affected systems to normal operation and restore systems data and/or assets that have been affected by an incident. 

---

## Incident report analysis

### Summary:
The company suffered a DDoS attack carried out by a malicious actor, which endangered the internal network for two hours until it was resolved. The attack was executed through a flood of incoming ICMP packets. As a result, internal network traffic was unable to access any resources.

The incident response team reacted by blocking incoming ICMP packets, shutting down non-critical network services, and restoring critical services. Subsequently, the cybersecurity team discovered that the attacker had launched a flood of ICMP pings through a misconfigured firewall, which caused the company’s network to become saturated.

### Identify:
The attack consisted of an ICMP flood, a type of Denial-of-Service (DoS) attack. It was carried out through a massive stream of ICMP packets, which overwhelmed the network and disrupted internal services.

### Protect:
The network security team implemented a new firewall rule to limit the rate of incoming ICMP packets. In addition, source IP verification was configured on the firewall to detect potential spoofed IP addresses in incoming ICMP packets.

### Detect:
Network monitoring software has been implemented to identify abnormal traffic patterns. In addition, an IDS/IPS system has been deployed to filter portions of ICMP traffic based on suspicious characteristics, thereby enhancing the organization’s ability to detect potential attacks at an early stage.

### Respond:
The incident response team blocked incoming ICMP packets to stop the traffic flood. Non-critical network services were suspended, while critical services were restored to maintain operational continuity. The attack was then analyzed and all actions were documented, with the goal of improving response procedures for similar future incidents.

### Recover:
After containing the attack, the internal network was restored to normal operation and critical services were secured. Improvement measures, such as new firewall rules and monitoring systems, were implemented to strengthen resilience and reduce the impact of potential future attacks. The incident results were also communicated to company management to ensure transparency and organizational preparedness. The actions documented in this report will serve as a reference to respond more quickly and effectively to future cybersecurity incidents.


