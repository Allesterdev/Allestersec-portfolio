# Scenario

You’re part of the growing security team at a company for sneaker enthusiasts and collectors. The business is preparing to launch a mobile app that makes it easy for their customers to buy and sell shoes. 

You are performing a threat model of the application using the PASTA framework. You will go through each of the seven stages of the framework to identify security requirements for the new sneaker company app.

---

## Define business and security objectives

Business Objectives:

 - Provide a mobile platform that facilitates the buying and selling of collectible sneakers for enthusiasts.

 - Ensure the application is user-friendly while maintaining high availability during high-demand product releases ("drops").

Security & Compliance Requirements:

 - PCI-DSS Compliance: The app will process transactions, requiring strict adherence to PCI-DSS standards for credit card data protection.

 - GDPR Compliance: Implement data protection policies to handle European user data in accordance with GDPR regulations.

 - Bot Mitigation: Implement controls to prevent automated bots from hoarding inventory during launches.

## Define the technical scope

Selected Technologies: SQL, API, AES, SHA-256

Justification: "We prioritize SQL to manage the sneaker inventory and user data, which requires mitigating risks like SQL Injection. APIs are essential for the mobile application's connectivity to the backend. Finally, AES and SHA-256 are mandatory for encrypting payment information (PCI-DSS) and hashing login credentials to ensure user privacy."

## Decompose application

graph LR
    User[User] -- "Product search" --> Process(Process: Searching for sneakers for sale)
    Process -- "Query Inventory" --> DB[(Database)]
    DB -- "Listings of current inventory" --> Process
    Process -- "Display Results" --> User
