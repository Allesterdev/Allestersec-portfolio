## Scenario

You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A former employee has decided to lure users to a fake website with malware. 

The former employee/ hacker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website’s source code. They embedded a javascript function in the source code that prompted visitors to download and run a file upon visiting the website. After embedding the malware, the hacker changed the password to the administrative account. When customers download the file, they are redirected to a fake version of the website that contains the malware. 

Several hours after the attack, multiple customers emailed yummyrecipesforme’s helpdesk. They complained that the company’s website had prompted them to download a file to access free recipes. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly. 

In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.

To address the incident, you create a sandbox environment to observe the suspicious website behavior. You run the network protocol analyzer tcpdump, then type in the URL for the website, yummyrecipesforme.com. As soon as the website loads, you are prompted to download an executable file to update your browser. You accept the download and allow the file to run. You then observe that your browser redirects you to a different URL, greatrecipesforme.com, which contains the malware.  

The logs show the following process:

 1. The browser initiates a DNS request: It requests the IP address of the yummyrecipesforme.com URL from the DNS server.

 2. The DNS replies with the correct IP address. 

 3. The browser initiates an HTTP request: It requests the yummyrecipesforme.com webpage using the IP address sent by the DNS server.

 4. The browser initiates the download of the malware.

 5. The browser initiates a DNS request for greatrecipesforme.com.

 6. The DNS server responds with the IP address for greatrecipesforme.com.

 7. The browser initiates an HTTP request to the IP address for greatrecipesforme.com.

A senior analyst confirms that the website was compromised. The analyst checks the source code for the website. They notice that javascript code had been added to prompt website visitors to download an executable file. Analysis of the downloaded file found a script that redirects the visitors’ browsers from yummyrecipesforme.com to greatrecipesforme.com. 

The cybersecurity team reports that the web server was impacted by a brute force attack. The disgruntled hacker was able to guess the password easily because the admin password was still set to the default password. Additionally, there were no controls in place to prevent a brute force attack. 

Your job is to document the incident in detail, including identifying the network protocols used to establish the connection between the user and the website.  You should also recommend a security action to take to prevent brute force attacks in the future.

---

## Security incident report

### Section 1: Identify the network protocol involved in the incident

The following network protocols were involved:

   DNS (Domain Name System): Used to resolve domain names to IP addresses during redirection.

   HTTP (Hypertext Transfer Protocol): Used to deliver the compromised web page and initiate the malware download.

   TCP/IP: Underlying transport protocol used for all communications between browser and server.

### Section 2: Document the incident

Several hours after the compromise, customers reported that the website encouraged them to download a file in exchange for free recipes. Upon execution, their browsers were redirected to a different domain, and their computers began to slow down.

The attacker changed the admin password to prevent recovery and maintain control. The malicious script embedded in the site redirected users from yummyrecipesforme.com to greatrecipesforme.com, a fake site hosting malware.

Captured network traffic revealed the following sequence:

 1. DNS request for yummyrecipesforme.com → DNS response with correct IP

 2. HTTP request to the site → download prompt for executable file

 3. DNS request for recetasriquitasforme.com → DNS response pointing to greatrecipesforme.com

 4. HTTP request to greatrecipesforme.com → malware delivered

This confirms that the attacker used DNS manipulation and JavaScript injection to redirect users and deliver malicious payloads.

### Section 3: Recommend one remediation for brute force attacks

To prevent future brute-force attacks, the following security measures are recommended:

   Enforce strong password policies: Disable default credentials and require complex passwords for all administrative accounts.

   Implement account lockout mechanisms: Temporarily block access after multiple failed login attempts.

   Use multi-factor authentication (MFA): Add an extra layer of security to administrative logins.

   Monitor login activity: Set alerts for unusual login patterns or repeated failed attempts.

   Conduct regular security audits: Review access controls and update software to patch known vulnerabilities.

   It is strongly recommended to change all administrative passwords immediately when an employee with privileged access is terminated or leaves the organization. Failure to do so may result in unauthorized access, data compromise, or reputational damage.


 
 
