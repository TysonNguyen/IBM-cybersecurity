---
id: vewpabhrh45ba5ic00kqet3
title: Application
desc: ''
updated: 1653181066889
created: 1653181053325
---

# Application Security Techniques and Risks

- [ ] Describe the pros and cons of various Software Development Life-cycles.
- [ ] Explore application security risks.
- [ ] Discuss application security techniques, dynamic analysis, static source code analysis and industry tools.

- [ ] Explore standards and regulations for application security.
---

## Application Security Fundamentals

> Application security encompasses measures taken to improve the security of an application often by finding, fixing and preventing security vulnerabilities. Different techniques are used to surface such security vulnerabilities at different stages of an applications lifecycle such as design, development, upgrade, and maintenance.

### Network Security vs Application Security

Network security is the protection of systems and information assets at the network level involving areas such as routers / switches, servers, workstations, and wireless networks.

Application security is the protection of application front ends, source code, and information assets at the software level involving systems such as website, databases, mobile apps, and client and server applications.

- Both network security and application security are components of an overall information security program that includes policy procedures, incident response, and disaster recovery.

## Software Development Lifecycle

1. Plan
2. Develop
3. Tests
4. Deploy
5. Maintain

Common software development methodologies:

Waterfall
: Top-down approach is a simple and easy to follow, but not very flexible and design flaws can be costly if discovered after the application is deployed.

Agile and Scrum
: Consists of short bursts of analysis, design, coding, and testing. Allows team to be responsive and motivates the team to be productive.

- However, due to cycle deadlines, it is easy to forget about application security testing.

Spiral
: Focuses on minimizing risk, which makes it possible to evaluate security at the end of each cycle. However, not as quick as Agile, and may increase the cost of the software development.

Iterative
: Breaks up development into smaller prototypes through repeated cycles, which allows lessons to be learned from earlier iterations.

### White Box Testing

Provides the attackers with detailed information about the system to target.

- Bypasses many reconnaissance steps normally precedes attacks, shortening the time of the attack, and increasing the likelihood that it will find security flaws.

### Black Box Testing

Does not provide attackers with any information prior to the attack.

- Simulates an external attacker trying to gain access to information about the business and technical environment before engaging in an attack.

### Gray Box Testing

Known as partial knowledge tests, are sometimes chosen to balance the advantages and disadvantages of white and black box penetration tests.


### Source Code Analysis Tools

Static Application Security Testing (SAST)
: Analyzes source code for security vulnerabilities prior to the launch of an application and is used to strengthen code.

- Produces fewer false positives, but more implementations require access to the application source code and requires expert configurations and lots of processing power.

Dynamic Application Security Testing (DAST)
: Find visible vulnerabilities by feeding the URL into an automated scanner. This method is highly scalable, easily integrated, and quick.

- Requires expert configuration.
- High possibility of false positives and negatives.


Interactive Application Security Testing (IAST)
: A solution that assesses applications from within using software instrumentation. This technique allows us to combine the strengths of both SAST and DAST methods as well as providing access to code, HTTP traffic, library information, back-end connections, and configuration information.

## Application Security Threats and Attacks

Before an organization selects any third-part software, an application security professional should assess the risk and ask questions about the security standards used to develop the software.

### Third Party Software and Supplier Risk Assessment

Third party software standards, patching, and testing.

- Identify how any risks would impact your organizations business.
  - Financial
  - Operational
  - Strategic
- Next step would be to determine the likelihood the risk would interrupt the business.
- Finally, there is a need to identify how the risk would impact the business.

#### Web Application Firewall (WAF)

A web application firewall filters, monitors, and blacks HTTP traffic to and and from a web application.

- WAF is able to filter the content of specific web applications while regular firewall serve as a safety gate between servers.
- By inspecting HTTP traffic, it can prevent attack stemming from web application security flaws such as SQL injection, cross-site scripting, viral inclusion, and security misconfigurations.

### Input Validation

- Buffer overflow
- Cross-site scripting
- SQL injection
- Canonicalization - The process of converting data that involves more than one representation into a standard approved format.

### Authentication

- Network eavesdropping
- Brute force attack
- Dictionary attacks
- Cookie replay
- Credential theft

### Authorization

- Elevation of privilege
- Disclosure of confidential data
- Data tampering
- Luring attacks

### Configuration Management

- Unauthorized access to administration interfaces
- Unauthorized access to configuration stores
- Retrieval of clear text configuration data
- Lack of individual accountability; over-privileged process and service accounts.


### Exception Management

- Information disclosure
- Denial of service


### Auditing and Logging

- User denies performing an operation
- Attacker exploits an application without trace
- Attacker covers his or her tracks

### OWASP Top 10 Web Application Security Risks

Top 10 is a standard awareness document for developers and web application security. It Represents a broad consensus about the most critical security risk to web applications.

1. **Injection** - When untrusted data is sent to an interpreter as part of a command or query to trick interpreter into executing unintended commands.
2. **Broken Authentication** - Application related to authentication and session management issues allowing the attackers to compromise passwords, keys, or session tokens to exploit other users identities temporarily or permanently.
3. **Sensitive Data Exposure** - Attackers may steal or modify protected data to conduct credit card fraud, identity theft, or other crimes.
4. **XML External Entities (XXE)** - Poorly configured XML processors evaluate external entity references within XML documents.
5. **Broken Access Control** - Restrictions on what authenticated users are allowed to are often not properly enforced.
6. **Security Misconfigurations** - Most common seen issue result of insecure default configurations, incomplete, or Ad-hoc configurations.
7. **Cross-site Scripting XSS** - Occurs whenever an application includes untrusted data in a new webpage without proper validation or updates an existing webpage with users data using a browser API that can create HTML or Javascript.
   - Allows hackers to execute scripts in the victim's browser to hijack sessions, deface websites, or redirect the user to malicious sites.
8. **Insecure De-serialization** - Leads to remote code execution. Can be used to perform attacks including replay attacks, injection attacks, and privilege escalation attacks.
9. **Using components with known vulnerabilities** - A vulnerable component can be exploited for serious data loss or server takeover.
10. **Insufficient Logging & Monitoring** - Missing or ineffective integration with incident response allows attackers to further attack systems, maintain persistence, pivot to more systems, extract or destroy data.
    - Most breach studies show time to detect a breach is over 200 days, typically detected by external parties rater than internal processes or monitoring.

## Application Security Standards and Regulations

### Threat Modeling

Threat Modeling
: A process by which potential threats, such as structural vulnerabilities or the absence of appropriate safeguards, can be identified, enumerated, and mitigation can be prioritized.

- The purpose of threat modeling is to provide defenders with a systematic analysis of what controls or defenses need to be included, given the nature of the system, the probable attacker's profile, the most likely attack vectors, and the assets most desired by an attacker.

- **STRIDE methodology** - Introduced in 1999 at Microsoft for developers to find threats in products.
- **P.A.S.T.A** - Stands for process for attack simulation and threat analysis, which is a 7-step methodology.
- **TRIKE** - Using threat models as a risk management tool to satisfy the security auditing process, threat models are based on requirements model.
  - Establish the stakeholder defined acceptable level of risk assigned to each asset class.
  - Analysis of the requirements model yields a threat model for which threats are enumerated and assigned risk values.
- **VAST** - Visual agile and simple threat modeling and necessity of scaling the threat modeling process across the infrastructure and entire SDLC into Agile software development.

### Standards

#### CERT Secure Coding

- Computer Emergency Response Team or CERT, for the software engineering Institute is a non-profit United States federally funded research and development center.
- Software coding standard for the C programming language, developed by the CERT Coordination Center.
- Used to improve the safety, reliability, and security of software systems.

#### Common Weakness Enumeration (CWE)

- Software weaknesses and vulnerabilities.
- Sustained by a community project with the goals of understanding flaws in software.
- Project is sponsored by the National Cybersecurity FFRDC (Federally Funded Research and Development Center).

#### DISA-STIG - Defense Information Systems Agency

- A security technical implementation guide as a cybersecurity methodology for standardizing security protocols within networks, servers, and computers, to enhance overall security.

#### ISO 27034/24772

- Another set of standards for application security are from the International Organization for Standardization. 
- ISO 27034 describes the minimum requirements for application security control.
- ISO 24772 is a standard around information technology programming languages, which provides guidance to avoiding vulnerabilities and programming languages through language selection and use. 

#### PCI-DSS PCI Data Security Standard

- Mandated by the card brands but administered by the Payment Card Industry Security Standards Council.
- Increase controls around cardholder data to reduce credit card fraud.

#### NIST 800-53

- A special publication provides a catalog of security and privacy controls for all US federal information systems except those related to national security.
- Published by the National Institute of Standards and Technology (non-regulator agency of the United States Department of Commerce).

#### Gramm-Leach-Bliley Act (GLBA)

- Known as Financial Services Modernization Act of 1999.
- More strict governmental boundaries between financial institutions to limit companies share and provide information with each other.

#### Health Insurance Portability and Accountability 1996 (HIPAA)

- Created to modernize the flow of healthcare information.
  - How personally identifiable information maintained by the healthcare and healthcare insurance industries could be protected from fraud and theft.
  - Address limitations on healthcare insurance cover.

#### Sarbanes-Oxley Act of 2002 (SOX)

- A United States federal law that set new or expanded requirements for all US public company boards, management, and public accounting firms.
  - Many provisions also applied to privately held companies, such as the willful destruction of evidence to impede a federal investigation.

