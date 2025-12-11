# Scenario

You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. Several customers of clients reported that they were not able to access the client company website www.yummyrecipesforme.com, and saw the error “destination port unreachable” after waiting for the page to load. 

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. To start, you attempt to visit the website and you also receive the error “destination port unreachable.” To troubleshoot the issue, you load your network analyzer tool, tcpdump, and attempt to load the webpage again. To load the webpage, your browser sends a query to a DNS server via the UDP protocol to retrieve the IP address for the website's domain name; this is part of the DNS protocol. Your browser then uses this IP address as the destination IP for sending an HTTPS request to the web server to display the webpage  The analyzer shows that when you send UDP packets to the DNS server, you receive ICMP packets containing the error message: “udp port 53 unreachable.” 

![Exercise Screenshot](../image/imagencurso.png)

In the tcpdump log, you find the following information:

 1. The first two lines of the log file show the initial outgoing request from your computer to the DNS          server requesting the IP address of yummyrecipesforme.com. This request is sent in a UDP packet.

 2. The third and fourth lines of the log show the response to your UDP packet. In this case, the ICMP           203.0.113.2 line is the start of the error message indicating that the UDP packet was undeliverable to       port 53 of the DNS server.

 3. In front of each request and response, you find timestamps that indicate when the incident happened. In      the log, this is the first sequence of numbers displayed: 13:24:32.192571. This means the time is 1:24       p.m., 32.192571 seconds.

 4. After the timestamps, you will find the source and destination IP addresses. In the first line, where        the UDP packet travels from your browser to the DNS server, this information is displayed as:                192.51.100.15 > 203.0.113.2.domain. The IP address to the left of the greater than (>) symbol is the         source address, which in this example is your computer’s IP address. The IP address to the right of the      greater than (>) symbol is the destination IP address. In this case, it is the IP address for the DNS        server: 203.0.113.2.domain. For the ICMP error response, the source address is 203.0.113.2 and the           destination is your computers IP address 192.51.100.15.

 5. After the source and destination IP addresses, there can be a number of additional details like the          protocol, port number of the source, and flags. In the first line of the error log, the query                identification number appears as: 35084. The plus sign after the query identification number indicates       there are flags associated with the UDP message. The "A?" indicates a flag associated with the DNS           request for an A record, where an A record maps a domain name to an IP address. The third line displays      the protocol of the response message to the browser: "ICMP," which is followed by an ICMP error message.

 6. The error message, "udp port 53 unreachable" is mentioned in the last line. Port 53 is a port for DNS        service. The word "unreachable" in the message indicates the UDP message requesting an IP address for        the domain "www.yummyrecipesforme.com" did not go through to the DNS server because no service was           listening on the receiving DNS port.

 7. The remaining lines in the log indicate that ICMP packets were sent two more times, but the same             delivery error was received both times. 

Now that you have captured data packets using a network analyzer tool, it is your job to identify which network protocol and service were impacted by this incident. Then, you will need to write a follow-up report. 

As an analyst, you can inspect network traffic and network data to determine what is causing network-related issues during cybersecurity incidents. Later in this course, you will demonstrate how to manage and resolve incidents. For now, you only need to analyze the situation. 

This event, in the meantime, is being handled by security engineers after you and other analysts have reported the issue to your direct supervisor. 

---

## Cybersecurity Incident Report

Part 1: Description of the Issue  

Several clients reported that they were unable to access the company’s website www.yummyrecipesforme.com. The error displayed was “destination port unreachable”. I performed a network analysis using tcpdump and received ICMP packets with the message “UDP port 53 unreachable”.

Part 2: Incident Evaluation and Diagnosis

 1. When the issue was first reported: The issue was first reported when multiple clients were unable to       access the company’s website www.yummyrecipesforme.com. The error message displayed was “destination       port unreachable.”
 
 2. Description of initial symptoms: Users experienced long loading times followed by an error message,        indicating that the browser could not reach the web server. This suggested a failure in the network        communication process.
 
 3. Current status of the issue: After performing a network analysis using tcpdump, ICMP packets were          observed with the message “UDP port 53 unreachable.” These responses were triggered by DNS queries         sent via UDP to the server at IP address 203.0.113.2. This confirms that the DNS service was not           reachable at the time of the incident.
 
 4. Information discovered during investigation: The captured traffic shows that the browser attempted to      resolve the domain name using DNS over UDP (port 53). However, the DNS server responded with ICMP          error messages, indicating that no service was listening on that port. As a result, the domain name        could not be resolved to an IP address, and the subsequent HTTPS request to the web server failed.
 
 5. Next steps to resolve the issue:
 
    -Verify whether the DNS service is running and actively listening on UDP port 53.
 
    -Check firewall or ACL rules that may be blocking incoming UDP traffic to port 53.
 
    -Review system and DNS logs for service failures or misconfigurations.
 
    -Deploy a temporary fallback DNS server to restore name resolution while the issue is being addressed.
 
 6. Probable root cause of the issue: The ICMP message “UDP port 53 unreachable” suggests that the DNS         server was either down, misconfigured, or blocked by a network security rule. Additionally, the            possibility of a targeted attack cannot be ruled out. An attacker may have disrupted the DNS service       through traffic saturation (DoS), firewall manipulation, or service tampering. Further investigation       of system and firewall logs is recommended to determine whether malicious activity contributed to the      incident.


