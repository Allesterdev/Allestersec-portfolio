# Scenario

You are part of the security team at Rhetorical Hospital and arrive to work one morning. On the ground of the parking lot, you find a USB stick with the hospital's logo printed on it. There’s no one else around who might have dropped it, so you decide to pick it up out of curiosity.

You bring the USB drive back to your office where the team has virtualization software installed on a workstation. Virtualization software can be used for this very purpose because it’s one of the only ways to safely investigate an unfamiliar USB stick. The  software works by running a simulated instance of the computer on the same workstation. This simulation isn’t connected to other files or networks, so the USB drive can’t affect other systems if it happens to be infected with malicious software.

![imagen](../image/usb.png)
---

## Parking lot USB exercise

### Contents
The USB contains personal folders such as family photos, pictures of the dog, vacation ideas, and a file related to the wedding. It also stores highly sensitive work data, including the employee budget, the hospital’s internal agenda, a résumé, and a letter.

### Attacker mindset

#### Personal Data Exploitation
- **Family photos, pet pictures, vacation ideas, wedding file**  
  - Used to understand personality traits, preferences, and motivations.  
  - Enables **social engineering** attacks by crafting convincing messages or scenarios.  
  - Supports **brute-force attacks** by guessing passwords based on personal details.  
  - Facilitates **identity theft** or creation of fake social media profiles to gain trust.  

#### Work-Related Data Exploitation
- **Employee budget, internal hospital agenda, résumé, letter**  
  - Provides insight into organizational structure and financial planning.  
  - Can be leveraged for **spear phishing** campaigns targeting hospital staff.  
  - Allows attackers to impersonate internal personnel using agenda or budget details.  
  - May be used for **extortion or blackmail** if sensitive financial or personal details are exposed.  

#### Combined Attack Scenarios
- **Reconnaissance and mapping:** Correlating personal and professional data to identify relationships, hierarchies, and weak points.  
- **Credential attacks:** Using personal information to guess or reset hospital system credentials.  
- **Targeted campaigns:** Crafting highly convincing phishing emails or fraudulent communications using both personal and professional context.  

### Risk analysis

To reduce the risk of USB bait attacks, organizations should implement a combination of technical, operational, and management controls:

- **Technical controls**: Disable USB ports on workstations, enforce endpoint protection policies, and use device control software to monitor and restrict USB access.
- **Operational controls**: Train employees to avoid connecting unknown devices, establish clear reporting procedures for suspicious USBs, and conduct regular awareness campaigns.
- **Management controls**: Define and enforce data handling policies, maintain an incident response plan for physical device threats, and audit compliance with USB usage restrictions.

These measures help prevent unauthorized access, reduce human error, and strengthen the organization’s resilience against physical attack vectors.

