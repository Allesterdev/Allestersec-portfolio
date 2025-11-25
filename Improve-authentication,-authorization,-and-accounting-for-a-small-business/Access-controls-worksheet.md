# Scenario

You’re the first cybersecurity professional hired by a growing business.

Recently, a deposit was made from the business to an unknown bank account. The finance manager says they didn’t make a mistake. Fortunately, they were able to stop the payment. The owner has asked you to investigate what happened to prevent any future incidents.

To do this, you’ll need to do some accounting on the incident to better understand what happened. First, you will review the access log of the incident. Next, you will take notes that can help you identify a possible threat actor. Then, you will spot issues with the access controls that were exploited by the user. Finally, you will recommend mitigations that can improve the business' access controls and reduce the likelihood that this incident reoccurs.

### Accounting exercise
Event Type: Information

Event Source: AdsmEmployeeService

Event Category: None

Event ID: 1227

Date: 10/03/2023

Time: 8:29:57 AM

User: Legal\Administrator

Computer: Up2-NoGud

IP: 152.207.255.255

Description:

Payroll event added. FAUX_BANK

---

## Access controls worksheet

| Authorization/authentication | Note(s) | Issue(s) | Recommendation(s) |
|------------------------------|---------|----------|--------------------|
| Legal\Administrator account used from external IP `152.207.255.255` on device `Up2-NoGud` | **Objective:** List 1–2 pieces of information that can help identify the threat:<br>• Incident caused by `Legal\Administrator` account<br>• Occurred on 10/03/2023 at 8:29 AM<br>• Device used: `Up2-NoGud` | **Objective:** Based on your notes, list 1–2 authorization issues:<br>• Account had excessive privileges for financial operations<br>• Administrator account active without proper restrictions | **Objective:** Make at least 1 recommendation that could help prevent this kind of incident:<br>• Enforce least privilege by limiting admin access to financial systems<br>• Implement MFA and restrict access from external IPs<br>• Audit privileged accounts regularly |

