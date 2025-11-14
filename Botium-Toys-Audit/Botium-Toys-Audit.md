# 🛡️ Botium Toys Security Audit Exercise

---

## 📌 Introduction

This document is part of an exercise from the **Google Cybersecurity Certificate** program.  
The goal is to practice conducting a security audit, completing a controls and compliance checklist, and providing recommendations to improve the security posture of a fictional company: **Botium Toys**.

---

## 📝 Audit Report

Botium Toys: Scope, goals, and risk assessment report

Scope and goals of the audit

Scope: The scope of this audit is defined as the entire security program at Botium Toys.
This includes their assets like employee equipment and devices, their internal network,
and their systems. You will need to review the assets Botium Toys has and the controls
and compliance practices they have in place.

Goals: Assess existing assets and complete the controls and compliance checklist to
determine which controls and compliance best practices that need to be implemented
to improve Botium Toys’ security posture.

Current assets

Assets managed by the IT Department include:
  ● On-premises equipment for in-office business needs
  ● Employee equipment: end-user devices (desktops/laptops, smartphones),
  remote workstations, headsets, cables, keyboards, mice, docking stations,
  surveillance cameras, etc.
  ● Storefront products available for retail sale on site and online; stored in the
  company’s adjoining warehouse
  ● Management of systems, software, and services: accounting,
  telecommunication, database, security, ecommerce, and inventory management
  ● Internet access
  ● Internal network
  ● Data retention and storage
  ● Legacy system maintenance: end-of-life systems that require human monitoring

Risk assessment

Risk description
Currently, there is inadequate management of assets. Additionally, Botium Toys does
not have all of the proper controls in place and may not be fully compliant with U.S. and
international regulations and standards.
Control best practices
The first of the five functions of the NIST CSF is Identify. Botium Toys will need to
dedicate resources to identify assets so they can appropriately manage them.
Additionally, they will need to classify existing assets and determine the impact of the
loss of existing assets, including systems, on business continuity.

Risk score
On a scale of 1 to 10, the risk score is 8, which is fairly high. This is due to a lack of
controls and adherence to compliance best practices.

Additional comments
The potential impact from the loss of an asset is rated as medium, because the IT
department does not know which assets would be at risk. The risk to assets or fines
from governing bodies is high because Botium Toys does not have all of the necessary
controls in place and is not fully adhering to best practices related to compliance
regulations that keep critical data private/secure. Review the following bullet points for
specific details:

  ● Currently, all Botium Toys employees have access to internally stored data and
  may be able to access cardholder data and customers’ PII/SPII.
  ● Encryption is not currently used to ensure confidentiality of customers’ credit
  card information that is accepted, processed, transmitted, and stored locally in
  the company’s internal database.
  ● Access controls pertaining to least privilege and separation of duties have not
  been implemented.
  ● The IT department has ensured availability and integrated controls to ensure
  data integrity.
  ● The IT department has a firewall that blocks traffic based on an appropriately
  defined set of security rules.
  ● Antivirus software is installed and monitored regularly by the IT department.
  
  ● The IT department has not installed an intrusion detection system (IDS).
  ● There are no disaster recovery plans currently in place, and the company does
  not have backups of critical data.
  ● The IT department has established a plan to notify E.U. customers within 72
  hours if there is a security breach. Additionally, privacy policies, procedures, and
  processes have been developed and are enforced among IT department
  members/other employees, to properly document and maintain data.
  ● Although a password policy exists, its requirements are nominal and not in line
  with current minimum password complexity requirements (e.g., at least eight
  characters, a combination of letters and at least one number; special
  characters).
  ● There is no centralized password management system that enforces the
  password policy’s minimum requirements, which sometimes affects productivity
  when employees/vendors submit a ticket to the IT department to recover or
  reset a password.
  ● While legacy systems are monitored and maintained, there is no regular
  schedule in place for these tasks and intervention methods are unclear.
  ● The store’s physical location, which includes Botium Toys’ main offices, store
  front, and warehouse of products, has sufficient locks, up-to-date closed-circuit
  television (CCTV) surveillance, as well as functioning fire detection and
  prevention systems.

---

## ✅ Controls Assessment Checklist

| Control                                   | Status   | Notes                                                                 |
|-------------------------------------------|----------|-----------------------------------------------------------------------|
| **Least Privilege**                       | ❌ No    | Not implemented                                                       |
| **Disaster Recovery Plans**               | ❌ No    | No backups or recovery plans                                          |
| **Password Policies**                     | ⚠️ Partial | Exists but weak, not aligned with standards                           |
| **Separation of Duties**                  | ❌ No    | Not implemented                                                       |
| **Firewall**                              | ✅ Yes   | Configured with rules                                                 |
| **Intrusion Detection System (IDS)**      | ❌ No    | Missing                                                               |
| **Backups**                               | ❌ No    | Not implemented                                                       |
| **Antivirus Software**                    | ✅ Yes   | Installed and monitored                                               |
| **Legacy Systems Monitoring**             | ⚠️ Partial | Maintained but no regular schedule                                    |
| **Encryption**                            | ❌ No    | Not used for credit card data                                         |
| **Password Management System**            | ❌ No    | Missing centralized system                                            |
| **Locks (offices, warehouse)**            | ✅ Yes   | Physical security in place                                            |
| **CCTV Surveillance**                     | ✅ Yes   | Updated and functional                                                |
| **Fire Detection/Prevention**             | ✅ Yes   | Alarms and sprinklers installed                                       |

---

## 📋 Compliance Checklist

### PCI DSS
| Best Practice                                                   | Status   |
|-----------------------------------------------------------------|----------|
| Only authorized users access card data                          | ❌ No    |
| Card data stored/processed securely                             | ❌ No    |
| Encryption procedures implemented                               | ❌ No    |
| Secure password management policies                             | ❌ No    |

### GDPR
| Best Practice                                                   | Status   |
|-----------------------------------------------------------------|----------|
| EU customer data private/secure                                 | ❌ No    |
| Breach notification within 72h                                  | ✅ Yes   |
| Data properly classified/inventoried                            | ❌ No    |
| Privacy policies enforced                                       | ✅ Yes   |

### SOC 1 / SOC 2
| Best Practice                                                   | Status   |
|-----------------------------------------------------------------|----------|
| User access policies established                                | ❌ No    |
| Sensitive data confidential/private                             | ❌ No    |
| Data integrity ensured                                          | ✅ Yes   |
| Data available only to authorized users                         | ❌ No    |

---

## 📌 Recommendations

1. Implement **least privilege access** and **separation of duties**.  
2. Develop **disaster recovery plans** and establish **regular backups**.  
3. Adopt **encryption** for sensitive data and credit card transactions.  
4. Strengthen **password policies** and enforce them via a centralized management system.  
5. Classify and inventory data to comply with **GDPR** and **SOC** requirements.  
6. Install an **Intrusion Detection System (IDS)**.  
7. Establish a **regular maintenance schedule for legacy systems**.  
8. Provide **security awareness training** for employees to reinforce compliance and best practices.

---


## 🎓 Lessons Learned

Through this exercise, I learned how to:
- Evaluate an organization’s assets and identify missing security controls.  
- Apply frameworks such as **NIST CSF, PCI DSS, GDPR, and SOC** to assess compliance.  
- Understand the importance of **defense in depth**: combining administrative, technical, and physical controls.  
- Recognize how gaps in controls (e.g., lack of encryption, weak password policies) directly increase risk.  
- Translate audit findings into **clear, actionable recommendations** for stakeholders.  

This exercise helped me connect theoretical knowledge with practical application, preparing me to perform real-world security assessments.

---
