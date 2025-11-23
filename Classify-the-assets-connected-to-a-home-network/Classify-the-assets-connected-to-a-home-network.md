# Scenario

![imagen](../image/escritorio.png)

You’re operating a small business from your home and must create an inventory of your network devices. This will help you determine which ones contain sensitive information that require extra protection.

To do this, you will start by identifying three devices that have access to your home network. This might include devices such as:

  - Desktop or laptop computers

  - Smartphones

  - Smart home devices

  - Game consoles

  - Storage devices or servers

  - Video streaming devices

Then, you’ll list important characteristics of each device such as its owner, location, and type. Finally, you will assign each device a level of sensitivity based on how important it is to protect.

---

![Home asset inventory](../image/HAI.png)

## Context
Evaluation of connected assets in a home environment, aiming to identify risks, classify sensitivity, and apply proportional defensive measures. The focus is on protecting confidentiality, integrity, and availability (CIA) of each asset.

## Main Table
| Asset                | Network Access     | Sensitivity     | Primary Risk                          | Key Defensive Recommendation                  |
|----------------------|--------------------|------------------|----------------------------------------|------------------------------------------------|
| Network router       | Continuous         | Confidential     | Direct exposure to Internet            | Change default credentials, disable WPS, update firmware |
| Desktop              | Occasional         | Restricted       | Personal data theft, malware           | Updated antivirus, disk encryption, regular backups |
| Guest smartphone     | Occasional         | Internal-only    | Uncontrolled access to local network   | Separate guest network, no access to internal devices |
| Webcam               | Occasional         | Confidential     | Espionage, unauthorized remote access  | Disable when unused, physical cover, review permissions |
| Printer              | Occasional         | Internal-only    | Wi-Fi exposure, remote access          | Change admin password, disable unused services |
| External hard drive  | None               | Confidential     | Indirect access if Desktop is compromised | Data encryption, disconnect when not in use |

## Sensitivity Classification
- **Confidential** → Specific users only. Requires encryption, access control, and monitoring.
- **Restricted** → Need-to-know basis. Requires strong authentication and segmentation.
- **Internal-only** → On-premises users. Requires network isolation and physical control.

## General Recommendations
1. **Network segmentation**: Create a separate guest network for untrusted devices (guest smartphones, IoT).
2. **Physical access control**: Ensure sensitive devices (webcam, external drive) are physically protected and disconnected when not in use.
3. **Encryption and backups**: Apply encryption to hard drives and perform regular offline backups.
4. **Updates and patching**: Keep all devices updated, especially router, Desktop, and printer.
5. **Monitoring and alerts**: Enable activity logs on router and Desktop to detect unauthorized access.

## Strategic Observations
- The Desktop acts as an indirect access hub for multiple assets. Its protection is a priority.
- The external hard drive, while not networked, inherits risks from the Desktop.
- Webcam and printer, connected via Wi-Fi, should be treated as semi-exposed assets.
- The router, as the network entry point, must be hardened.

