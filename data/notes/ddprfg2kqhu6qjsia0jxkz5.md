
# Penetration Testing Introduction

- [ ] Describe how penetration testing is used in cybersecurity and the role of digital forensics and Locard's exchange principle.

- [ ] Describe penetration testing, why it is used and the ethical considerations you might run into.
- [ ] Describe the difference between white hat, black hat, and grey hat attackers.
- [ ] Describe the several different types of threat actors and what characterizes each.

- [ ] Describe the methodologies used in penetration testing, including the following:
  - [ ] OSSTMM: Open Source Security Testing Methodology
  - [ ] NIST SP 800-42: National Institute of Standards and Technology Guideline on Network Security Testing
  - [ ] FFIEC: Federal Financial Institutions Examination Council, Information Technology Examination
  - [ ] ISSAF: Information Systems Security Assessment Framework

- [ ] Describe the Vulnerability Assessment Methodology

- [ ] Describe the practice of digital forensics, what technical skills and legal knowledge is required to be effective.

---

Penetration Testing
: The practice of testing a computer system, network or application to find security vulnerabilities that an attacker could exploit. Also called Pen-test, pen testing, ethical hacking.

White Hat
: Work done under contract for security reasons (Ethical hackers).

Grey Hat
: May look for vulnerabilities in an unauthorized manner and report back to the possible victim. They stand between white and black hat hackers.

Black Hat
: Do it for personal recognition, money, political agenda or a social change ("Bad guys").

Threat Actors
: An entity that is partially or wholly responsible for an incident that affects or potentially affects an organization's security. Also referred to as malicious actor.

- Script kiddies
- Hacktivists
- Organized crime
- Insiders
- Competitors
- Nation states
  - Fancy Bear (ATP28)
  - Lazarus Group
  - Scarcruft (Group 123)
  - APT29

---

## Pen-test Methodologies

- OSSTMM: Open Source Security Testing Methodology
- NIST SP 800-42: National Institute of Standards and Technology Guideline on Network Security Testing
- FFIEC: Federal Financial Institutions Examination Council, Information Technology Examination
- ISSAF: Information Systems Security Assessment Framework

![Method](https://www.smartlockr.eu/hs-fs/hubfs/Pentesting%20Process%20Infographic.png?width=1674&name=Pentesting%20Process%20Infographic.png)

![Pen-test Process](https://www.imperva.com/learn/wp-content/uploads/sites/13/2019/01/pen-testing.jpg.webp)

1. **Information Gathering** - The most important part to outline the logistics of the test, expectation, legal implications, objectives and goals to achieve.
2. **Threat Modeling** - Identify vulnerabilities in the network begins with  automated scans and manual testing techniques.
3. **Vulnerability Analysis** - Involves documenting analysis of vulnerabilities discovered as a result of previous penetration testing techniques. The plan of attack is developed by making a list of attractive vulnerabilities, suspicious services, and items worth researching for further analysis.
4. **Exploitation** - Carry out the vulnerability's exploit in an effort to be certain if the vulnerability is truly exploitable.
5. **Post Exploitation** - Once a system has been compromised, the value of the actual data is determined by what is stored and how far the attacker is wiling to make use of it for malicious purposes.
6. **Reporting** - Most critical aspect to document recommendation from testing to have an opportunity to review the findings to improve security.

---

## Vulnerability Tests

Vulnerability assessment is important to disclose risks of issues of security weakness so teams can prioritize and act for them accordingly.

- Plays a crucial role in ensuring company meets security compliance and guidelines of PCI DSS and HIPAA.

![Vulnerability](https://shieldbyteinfosec.com/images/vulnerabilityMethodology1.png)

---

## Digital Forensics

- Is a branch of forensic science.
- Includes the identification, recovery, investigation, validation, and presentation of facts regarding digital evidence found on computers or similar digital storage media devices.

### Locard's Exchange Principle

Dr. Edmond Locard is a pioneer in forensic science who became known as the Sherlock Holmes of France.

- The perpetrator of a crime will bring something into the crime scene and leave with something from it, and that both can be used as forensic evidence.

### Chain of Custody

- Refers to the chronological documentation or paper trail that records the sequence of custody, control, transfer, analysis, and disposition of physical or electronic evidence.
- It is often a process that has been required for evidence to be shown legally in court.

### Tools

Hardware:

- Faraday cage - a grounded metal screen surrounding a piece of equipment to exclude electrostatic and electromagnetic influences.
- Forensic laptops and power supplies, tool sets, digital camera, case folder, blank forms, evidence collection and packaging supplies, empty hard drives, hardware write blockers.

Software:

- Volatility
- FTK
- EnCase
- dd
- Autopsy (The Sleuth Kit)
- Bulk Extractor, and many more.
