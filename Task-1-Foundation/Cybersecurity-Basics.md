# Cybersecurity Basics

## 1. The CIA Triad

- **Confidentiality:** Information is accessible only to authorized people or systems. Controls include access permissions, encryption and least privilege.
- **Integrity:** Information remains accurate and is changed only by authorized actions. Controls include hashes for integrity checking, digital signatures, access controls and audit logs.
- **Availability:** Systems and information are accessible when needed. Controls include backups, redundancy, patching, capacity planning and denial-of-service protection.

### Example
A private file protected by permissions supports confidentiality; a verified checksum can help detect unexpected changes; tested backups help restore availability.

## 2. Common threats

| Threat | Description | Example of prevention or reduction |
|---|---|---|
| Phishing | Deceptive messages encourage users to disclose information or take unsafe actions. | Verify sender and URL, use MFA, report suspicious messages and provide awareness training. |
| Malware | Software intended to perform harmful or unauthorized actions. | Patch systems, restrict execution, use endpoint protection and limit privileges. |
| DDoS | Distributed traffic or requests overwhelm a service and reduce availability. | Use upstream DDoS protection, rate limits, filtering and resilient architecture. |
| SQL injection | Improperly handled input changes the meaning of a database query. | Use parameterized queries, safe APIs and least-privilege database accounts. |
| Brute force | Repeated attempts are made to guess credentials. | Rate limiting, MFA, strong unique passwords, monitoring and account lockout policies where appropriate. |
| Ransomware | Malware commonly encrypts files and demands payment; some variants also steal data. | Maintain tested offline/immutable backups, patch systems, segment networks and restrict privileges. |

## 3. Attack vectors

- **Social engineering:** Manipulating people into disclosing information or performing actions. Verify unusual requests through a separate trusted channel.
- **Wireless attacks:** Attacks against wireless access, configuration or communications. Use modern Wi-Fi security, strong credentials, firmware updates and guest-network isolation.
- **Insider threats:** Risk from people with legitimate access, whether malicious or accidental. Apply least privilege, logging, separation of duties and timely access reviews.

## 4. Basic security practices

1. Keep operating systems and applications patched.
2. Use unique passwords and MFA.
3. Apply least privilege.
4. Back up important data and test recovery.
5. Monitor logs and investigate unusual activity.
6. Test only systems you own or have permission to assess.

## 5. Learning check

- [ ] Explain confidentiality, integrity and availability in your own words.
- [ ] Give one example and one mitigation for each listed threat.
- [ ] Explain the difference between an attack vector and a vulnerability.
- [ ] Describe why authorization and scope matter in security testing.

## Evidence
Add a short summary of what you learned and any class notes here. Do not claim practical testing for topics that were only studied.
