---
id: 9580eaxs80sdsmko50z0kh2
title: Cross Site
desc: ''
updated: 1653197951122
created: 1653197938259
---

# Cross-Site Scripting

## Security Defects Become Famous

- Heartbleed and Shellshock in 2014 software security bugs.
- Recent Wikileaks exposure of CIA research into weaponizing iOS, Android and Samsung TV security bugs.
- Security researchers are trying to cash in on the fame.
- Bugs in security software are sensational (software is supposed to protect you).
- ALL major software vendors are target, especially security software.
- Costs to reputation and revenue.
- Could lead to litigations, and law enforcement investigations.
  - Since 2000, the FTC has issued over 45 consent decrees against companies failed to institute sufficient security practices while delivering software or services.

### Why Care?

- Average total cost of data breach in 2017 (Ponemon Study) is $3.62 million.
- 58% of Internet users use the same password for multiple sites, including their web mail.
- There is a growing black market for zero-day vulnerabilities.
  - Vulnerabilities sell of thousands to millions of dollars per exploit, earning hackers serious money.

#### Breaches

- **Jan 2017 Trend Micro** - Two researchers found 223 vulnerabilities in just 6 months. Massive damage to reputation as a cybersecurity vendor.
- **Oct 2017 Equifax** - 143 million stolen SSNs. CSO, CIO, CEO lost their jobs.
- **Dec 2013 Target** - 40+ million credit cards, 70-110 million name, address, phone, email addresses.
  - Total cost may reach over $1B in fines and other associated costs.
- **March 2011 RSA Security** - 40 million auth tokens for bank and government networks $66M plus loss.

## Secure Software Challenges

|       | Developers                                            | Hackers                           |
| ----- | ----------------------------------------------------- | --------------------------------- |
| Time  | Under time pressure to develop and test functionality | May have unlimited time           |
| Focus | Security is not the primary focus over functionality  | Focused on finding security holes |
| Motivation / Resources | Responsible to product's primary functionality | Bragging rights, illicit profits |
| Specialization | Specialize on functionality of the product | Specialize in security penetration |

### Mitigate Product Security Risk

#### Prevent New Bugs

- Know SANS 25 Most Dangerous Programming Errors (includes most of common security Top 10).
- "Think like a hacker". How can code be abused?
- Build software defenses into software:
  - Input Validation
  - Output Sanitization
  - Strong Encryption
  - Strong Authentication and Authorization
- Choose secure frameworks rather than simply reply on developer security skills.
- Do not think product is isolated from the Internet is not at risk.
- Do not think that if a file or a database is local does not need to be protected. The majority of breaches are launched internally.

#### Address Existing Bugs

- Redesign product front end to be good looking and functional, but also secure.
- Implement smart architectural changes that fix security flaws at the top.
- Do not spot-fix issues.
  - Implement a fix across the board and how to be prevented in the future.
- Security bugs are special because of their potential impact.
- Deliver security patches with faster release vehicles.

## Common Attacks - Cross-Site Scripting

Cross-Site Scripting (XSS)
: Allows attackers to inject client-side scripts into the web page.

### Dangers of XSS

- Harvest credentials
- Take over user sessions
- CSRF
- Steal cookies, local store data
- Elevate privileges
- Redirect users to malicious sites

XSS is widespread in 3rd party products such as WordPress and Drupal.

### In the News

- eBay XSS bug left users vulnerable to (almost) undetectable phishing attacks.
- The Apache Foundation hacked by exploiting XSS in JIRA.

### Effective Defenses

#### HTML Encoding

- Output Encoding works well for server side generate pages and is quite effective in neutralizing most XSS payloads.
  - HTML Encoding alone will not prevent charset attacks.

#### JavaScript Escaping

- XSS can be introduced with JavaScript code.
- Escaping single quotes will prevent injection.

#### Safe DOM Elements

- XSS in modern Rich Client UIs is often made possible by unsafe handling of the DOM.
- Using the `innerHtml` attribute allows the user input to be rendered as HTML and XSS with JavaScript events as possible.
- The safe alternative is to use `textContent` (or `innerText` in some versions of IE).

#### Use Eval and Dynamic Code Generation with Care

- JavaScript `eval()` function which accepts a JavaScript expression as a string argument and executes it. Use of this function is discouraged.
- Same care is needed when the code generates pieces of JavaScript dynamically. Also discouraged.

#### Input Validation

**Whitelisting** is recommended.

- Reduces the attack surface to a known quantity.
- If possible, most input should be whitelisted to alphanumeric to prevent XSS (and many other attacks).
- Special characters should only be allowed on an exception basis.
- Some cases may be relaxed to allow single quotes or other characters.

**Blacklisting** - NOT RECOMMENDED.

- Creative attacker may bypass blacklist by trying a previously unknown method.

**Client Side Input Validation** - NOT RECOMMENDED.

- Can only be used to assist with product usability.
- Attackers can easily bypass it by sending the request directly to the server.

#### Use Proven Validation and Encoding Functionality

- Protect both input and output - "Defense in Depth" principle.
- As you validate the input and encode the output, use proven and reputable libraries.
- It is best to implement a framework that has one central set of functionality that validates and encodes data.