# Scenario

You work for an educational technology company that developed an application to help teachers automatically grade assignments. The application handles a wide range of data that it collects from academic institutions, instructors, parents, and students.

Your team was alerted to a data leak of internal business plans on social media. An investigation by the team discovered that an employee accidentally shared those confidential documents with an external business partner. An audit into the leak is underway to determine how similar incidents can be avoided.

A supervisor provided you with information regarding the leak. It appears that the principle of least privilege was not observed by employees at the company during a sales meeting. You have been asked to analyze the situation and find ways to prevent it from happening again.

First, you'll need to evaluate details about the incident. Then, you'll review the controls in place to prevent data leaks. Next, you'll identify ways to improve information privacy at the company. Finally, you'll justify why you think your recommendations will make data handling at the company more secure.

---

## Incident Summary
During a team meeting, a sales manager shared access to an internal-only folder containing documents related to a new, unreleased product, customer analytics, and promotional materials. After the meeting, access was not revoked. Later, a sales team member mistakenly shared the full folder link with a business partner during a video call. The partner assumed it was promotional content and posted the link publicly on social media.

## Control
**Least Privilege (NIST SP 800-53: AC-6)**

## Issue(s)
Factors contributing to the information leak:
- Excessive access to internal documents.
- No automatic revocation of temporary access.
- Confusion between internal and promotional materials.
- Lack of technical controls to prevent external sharing.

## Review
NIST SP 800-53: AC-6 defines the principle of least privilege: users should only have the minimum access necessary to perform their tasks. This includes enforcing roles, revoking access automatically, auditing privileges, and logging account activity.

## Recommendation(s)
To improve least privilege enforcement:
- Implement automatic revocation of temporary access.
- Clearly label internal vs. external documents.
- Restrict external sharing of internal links.
- Audit user privileges regularly.

## Justification
These improvements reduce the risk of accidental leaks by limiting unnecessary access, reinforcing team awareness, and applying technical safeguards against human error. They align with AC-6 and strengthen protection of sensitive data.

## Security Plan Snapshot

| Function | Category             | Subcategory                        | Reference(s)              |
|----------|----------------------|------------------------------------|---------------------------|
| Protect  | PR.DS: Data Security | PR.DS-5: Protections against data leaks | NIST SP 800-53: AC-6 |

## Notes
Security events occur when vulnerabilities align with threats in the operating environment, allowing exploitation. Human error, weak encryption, misconfigurations, or natural disruptions create opportunities for incidents, impacting confidentiality, integrity, and availability of critical assets.

