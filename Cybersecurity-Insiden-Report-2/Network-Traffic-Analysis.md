## Scenario

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. 

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor. 

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.


## Section 1: Identify the type of attack that may have caused this network interruption

The network interruption was caused by a high volume of synchronization requests using the TCP protocol from a single IP address, with the intent to overwhelm the server. The logs show that the IP address 203.0.113.0 sent a packet to initiate synchronization with the server through port 445 (commonly used for encrypted communication). After the initial connection attempt, the attacking IP continued sending additional synchronization requests, aiming to slow down and eventually disrupt the network.

The type of attack that caused the interruption is a SYN Flood Attack, which belongs to the family of Denial of Service (DoS) attacks.

## Section 2: Explain how the attack is causing the website to malfunction

The TCP three-way handshake works as follows:

 1. The source IP sends a synchronization request packet (SYN) using the TCP protocol.

 2. The destination server responds with a packet acknowledging the request (SYN/ACK).

 3. The source IP then sends a final packet (ACK) confirming that the connection is established and ready for communication.

When a large number of SYN requests are sent to the destination server all at once, the server’s processing capacity becomes overwhelmed. This slows down legitimate traffic and can eventually interrupt network communication entirely.

The logs show that a significant number of SYN packets were sent from the IP address 203.0.113.0, causing an overload on the server. They also indicate that legitimate IP addresses attempted to establish connections, but these could not be completed due to the ongoing SYN Flood attack.
