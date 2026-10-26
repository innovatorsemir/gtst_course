# GTSTv2 — Season 2
## Day 01: Reconnaissance (Information Gathering)

## Table of Contents

1. [Introduction to Penetration Testing](#1-introduction-to-penetration-testing)
2. [Pre-Engagement](#2-pre-engagement)
3. [Reconnaissance and Footprinting](#3-reconnaissance-and-footprinting)
4. [Why Is Reconnaissance Important?](#4-why-is-reconnaissance-important)
5. [Types of Footprinting](#5-types-of-footprinting)
6. [Information Collected During Reconnaissance](#6-information-collected-during-reconnaissance)
7. [OSINT — Open Source Intelligence](#7-osint--open-source-intelligence)
8. [OSINT Tools and Resources](#8-osint-tools-and-resources)
9. [Website Reconnaissance](#9-website-reconnaissance)
10. [Computer and Phone Reconnaissance](#10-computer-and-phone-reconnaissance)
11. [Network Reconnaissance](#11-network-reconnaissance)
12. [Personal Information Reconnaissance](#12-personal-information-reconnaissance)
13. [Finding Information Using Phone Numbers](#13-finding-information-using-phone-numbers)
14. [Finding Social Media Accounts](#14-finding-social-media-accounts)
15. [Sherlock](#15-sherlock)
16. [Important Commands](#16-important-commands)
17. [Key Takeaways](#17-key-takeaways)

---

## 1. Introduction to Penetration Testing

Penetration testing is an authorized security assessment in which security professionals evaluate systems, applications, and networks to identify and validate security weaknesses.

Ethical hacking is commonly explained using five phases:

1. Reconnaissance
2. Scanning and Enumeration
3. Gaining Access
4. Maintaining Access
5. Covering Tracks

Professional penetration testing engagements also involve additional steps before, during, and after the technical assessment.

A typical professional engagement may include:

1. Pre-Engagement
2. Information Gathering
3. Scanning
4. Gaining Access
5. Maintaining Access, when explicitly authorized and necessary
6. Proof of Concept
7. Post-Engagement

**Note:** Different methodologies organize these phases differently. Professional testing emphasizes authorization, documentation, risk management, and reporting.

This course primarily approaches cybersecurity from a Red Team perspective while also considering Blue Team practices.

- **Red Team:** Simulates adversarial activities to test security controls.
- **Blue Team:** Detects, investigates, prevents, and responds to security threats.

Understanding Red Team techniques is valuable for Blue Team professionals because it helps them anticipate attacks and improve defensive capabilities.

## 2. Pre-Engagement

Pre-engagement is the first major step in a professional penetration testing project. It establishes the legal permission, scope, objectives, limitations, and responsibilities of the engagement.

It generally consists of three activities:

1. Scoping Questionnaire
2. Pre-Engagement Meeting
3. Kick-Off Meeting

### 2.1 Scoping Questionnaire

A scoping questionnaire gathers detailed information about the client's environment and security assessment requirements.

It helps establish:

- Which assets are included in the assessment.
- Which systems are excluded.
- The type of testing required.
- Testing objectives and priorities.
- Restrictions and prohibited activities.
- Project timelines.
- Required access and testing conditions.

Common testing approaches include:

- **Black-box testing:** The tester begins with little or no internal knowledge of the target.
- **White-box testing:** The tester receives extensive internal information, documentation, or access.
- **Gray-box testing:** The tester receives partial information or limited access.

#### Example

A client may authorize testing of `172.16.2.32/18` while explicitly excluding other network ranges.

Another client may authorize testing of an internet-facing website but prohibit testing of the internal intranet.

The written scope must clearly define the permitted targets and activities. IP ranges should be checked carefully because an address may be part of a larger network block.

### 2.2 Pre-Engagement Meeting

The pre-engagement meeting reviews the scoping questionnaire and resolves uncertainties before testing begins.

Participants may include:

- Client representatives
- Project managers
- Technical leads
- Security professionals
- Legal or compliance representatives

The meeting establishes the final scope, discusses risks, and addresses legal and compliance requirements.

#### Important Agreements

**Non-Disclosure Agreement (NDA)**

An NDA is a confidentiality agreement that governs how sensitive information shared during the project may be used or disclosed.

**Rules of Engagement (RoE)**

The Rules of Engagement define how the penetration test will be conducted.

They may specify:

- Authorized targets and testing windows
- Permitted and prohibited techniques
- Communication channels
- Emergency contacts
- Escalation procedures
- Data handling and confidentiality
- Service disruption restrictions
- Evidence collection requirements
- Retesting arrangements
- Conditions for stopping the test

Both parties should approve the relevant agreements before testing begins.

### 2.3 Kick-Off Meeting

A kick-off meeting officially starts the engagement after the necessary preparations and approvals are complete.

Its purposes include:

- Confirming the schedule.
- Establishing communication protocols.
- Identifying responsible team members.
- Confirming emergency and escalation procedures.
- Reviewing the testing approach.
- Clarifying reporting and retesting expectations.

The outcome is a shared understanding of everyone's roles and responsibilities.

**Key point:** Technical testing should not begin until authorization, scope, and Rules of Engagement are clear.

## 3. Reconnaissance and Footprinting

Reconnaissance, also called information gathering or footprinting, is the process of collecting and analyzing information about a target organization, system, host, application, or network.

The information collected helps security professionals understand the target environment and plan an appropriate assessment.

Footprinting is an important part of ethical hacking because the quality of the information gathered influences the effectiveness of later testing.

Examples of reconnaissance information include:

- IP addresses
- Domain names
- DNS records
- Website technologies
- Operating systems
- Network architecture
- Publicly exposed services
- Public organizational information
- Publicly available employee or contact information

Reconnaissance does not automatically mean exploiting a vulnerability. Its main purpose is to understand the target and identify areas that may require further investigation.

## 4. Why Is Reconnaissance Important?

Imagine planning a security assessment of a bank. Before testing, an authorized security professional needs to understand the environment, including:

- The systems that are in scope
- Publicly accessible services
- Network boundaries
- Security controls
- Potential entry points
- Business-critical systems
- Possible risks and restrictions

The same principle applies to cybersecurity.

> To assess the security of a system effectively, you first need to understand the system.

Reconnaissance helps security professionals:

1. Understand the target environment.
2. Identify potential attack surfaces.
3. Select appropriate assessment methods.
4. Discover information that may reveal security weaknesses.
5. Reduce unnecessary testing.
6. Prioritize areas for further investigation.
7. Help defenders understand their organization's public exposure.

Reconnaissance findings do not prove that a system is vulnerable. Additional validation may be required during an authorized assessment.

## 5. Types of Footprinting

There are two main categories of reconnaissance.

### 5.1 Active Footprinting

Active footprinting involves interacting directly with the target or its infrastructure to collect information.

Examples include:

- Sending DNS queries to a target's DNS infrastructure.
- Using `ping` to test connectivity.
- Querying a service on an authorized host.
- Connecting to a website to inspect its response.
- Performing approved service discovery.

Active reconnaissance may generate logs and alerts and can reveal the source of the activity.

**Important:** Active reconnaissance must remain within the authorized scope. Unauthorized interaction, scanning, or attempts to access systems may violate laws, policies, or service terms.

### 5.2 Passive Footprinting

Passive footprinting collects information from publicly available sources or third parties without directly probing the target infrastructure.

Examples include:

- Reading a company's public website.
- Reviewing published reports.
- Searching public documentation.
- Examining publicly available DNS information.
- Reviewing public social media profiles.
- Using search engines to locate indexed pages.
- Consulting public domain-registration records where available.

Passive reconnaissance usually creates less direct interaction with the target infrastructure, although third-party services may still log activity.

### Active vs. Passive Footprinting

| Feature | Active | Passive |
|---|---|---|
| Interaction with target | Direct interaction or probing | Primarily public sources |
| Detection likelihood | Often higher | Often lower at the target |
| Examples | Authorized connectivity tests, service queries | Search engines, public reports, public profiles |
| Main consideration | Authorization and operational impact | Privacy, accuracy, and source reliability |

## 6. Information Collected During Reconnaissance

Reconnaissance can focus on several categories.

### A. Hosts and Devices

Examples:

- Servers
- Desktop computers
- Laptops
- Smartphones
- Internet-connected devices
- Publicly exposed services

Possible information includes IP addresses, hostnames, operating systems, and service details.

### B. Websites and Applications

Examples:

- Website domains
- Application URLs
- DNS records
- IP addresses
- Web server software
- Frameworks and libraries
- Technology versions
- Publicly accessible subdomains

### C. Networks

Examples:

- IP address ranges
- Network architecture
- Subnets
- VLANs
- Network devices
- Publicly exposed hosts
- Network segmentation information

Detailed internal network information should only be collected when permitted by the engagement scope.

### D. People and Organizations

Potentially relevant public information includes:

- Organization names
- Public business contact details
- Official social media accounts
- Public job listings
- Published technical documentation
- Publicly disclosed employee roles
- Public organizational relationships

Personal information must be handled responsibly. Collect only information relevant to the authorized assessment and respect privacy and applicable laws.

## 7. OSINT — Open Source Intelligence

**OSINT** stands for Open Source Intelligence.

It is the process of collecting, evaluating, and analyzing information obtained from publicly available sources to answer a specific question or support a decision.

OSINT is not limited to cybersecurity. It is also used in journalism, research, business intelligence, and other fields.

### Common OSINT Sources

- Search engines
- Official websites
- Public social media posts
- Public forums
- News articles
- Public records
- Publicly accessible technical documentation
- Domain and DNS information services
- Public code repositories
- Job advertisements

### OSINT Workflow

1. Define the research objective.
2. Identify relevant public sources.
3. Collect information.
4. Verify information using independent sources.
5. Analyze relationships and patterns.
6. Document findings and source references.
7. Report conclusions and uncertainties.

### Benefits of OSINT

- Can be performed without directly probing target infrastructure.
- Helps identify publicly exposed information.
- Supports security assessments and threat intelligence.
- Can be inexpensive compared with some technical testing methods.
- Helps organizations understand their public digital footprint.

### Limitations

- Information may be outdated.
- Search results may be incomplete.
- Different people may use the same username.
- Public information may be inaccurate or misleading.
- Findings require verification and context.

## 8. OSINT Tools and Resources

### 8.1 OSINT Framework

The OSINT Framework organizes links to publicly available intelligence-gathering resources.

It helps researchers discover tools and sources for different types of investigations.

Website: https://osintframework.com/

### 8.2 Search Engines

Search engines index and retrieve web content. They are commonly used for initial OSINT research.

Examples:

- Google
- Bing
- Yahoo

They can help locate:

- Official websites
- Public documents
- Technical articles
- Public organizational information
- Indexed pages and reports

Search results should be verified against reliable sources.

### 8.3 Shodan

Shodan is a search engine that indexes information about internet-connected devices and services.

It can help researchers discover publicly exposed systems, including:

- Servers
- Routers
- Webcams
- Industrial systems
- Other internet-connected devices

Shodan is different from a conventional search engine because it focuses on information about internet-connected systems rather than primarily indexing web pages.

Website: https://www.shodan.io/

**Defensive use:** Organizations can use Shodan to investigate their own public-facing assets and identify unintended exposure.

### 8.4 Maltego

Maltego is an information-gathering and link-analysis tool that helps visualize relationships between entities.

Depending on available data sources, entities may include:

- People
- Organizations
- Domains
- IP addresses
- Email addresses
- Online accounts

Its graphical representations help analysts investigate relationships and organize complex information.

Website: https://www.maltego.com/

## 9. Website Reconnaissance

Website reconnaissance involves gathering information about a website and its publicly visible technical infrastructure.

### Information to Collect

- Domain name
- IP addresses
- DNS records
- Web technologies
- Development frameworks
- Web server information
- Publicly visible subdomains
- Public domain-registration information

The collected information can help an authorized tester understand the application's technology stack and identify areas for further assessment.

### 9.1 Finding a Website's IP Address

#### Method 1: `ping`

Syntax:

```bash
ping example.com
```

This attempts to send ICMP echo requests to the hostname.

Depending on the network and configuration, the output may display a resolved IP address.

**Limitation:** A host may block ICMP traffic, and a website may use a CDN or load balancer. Therefore, the returned address may not identify the origin server.

#### Method 2: `nslookup`

Syntax:

```bash
nslookup example.com
```

This queries DNS to retrieve information about the hostname.

#### Method 3: `host`

Syntax:

```bash
host example.com
```

This performs DNS lookups for the specified hostname.

#### Method 4: Online DNS Lookup

Website: https://www.nslookup.io/

Online DNS lookup services can help inspect DNS records without installing command-line tools.

### 9.2 Identifying Website Technologies

Web technology fingerprinting helps identify technologies used by a website.

Tools mentioned in the course:

- **Wappalyzer:** Browser extension and technology profiling service.
- **BuiltWith:** Website technology lookup service.
- **WhatWeb:** Command-line web technology fingerprinting tool.

#### WhatWeb Example

```bash
whatweb https://example.com
```

WhatWeb can identify indicators of technologies such as web servers, content management systems, frameworks, and libraries.

The results are indicators, not guaranteed proof of the exact software or version in use.

Only run active fingerprinting against websites you are authorized to assess.

### 9.3 Domain Information

Domain reconnaissance may include registration details and DNS records.

#### WHOIS

WHOIS can provide available domain-registration information, depending on the registry, privacy settings, and applicable policies.

On Debian-based systems, install the tool using:

```bash
sudo apt update
sudo apt install whois
```

Example:

```bash
whois example.com
```

Not all registration details are publicly available.

#### DIG

`dig` is a command-line tool used to query DNS records.

Examples:

```bash
dig example.com
dig example.com A
dig example.com AAAA
dig example.com MX
dig example.com NS
dig example.com TXT
```

Record types:

- `A`: IPv4 address
- `AAAA`: IPv6 address
- `MX`: Mail exchange records
- `NS`: Authoritative name server records
- `TXT`: Text records, which may contain verification or email-security information

DNS records can help explain how a domain is configured, but they do not reveal every detail of the target's infrastructure.

## 10. Computer and Phone Reconnaissance

Reconnaissance involving computers, phones, and other hosts may seek information such as:

- IP address
- Hostname
- Operating system
- MAC address
- Running services
- Open ports
- Device type

Some information is visible only on a local network or through authorized technical testing.

For example, a MAC address is generally associated with a local network interface and is not normally discoverable across the public internet through ordinary IP routing.

Detailed service and port discovery belongs to the scanning and enumeration stage of a penetration test.

## 11. Network Reconnaissance

Network reconnaissance collects information about network structure and connectivity.

Possible findings include:

- IP address ranges
- Network architecture
- Network classes and address types
- Subnets
- VLANs
- Network-connected hosts
- Network devices
- Publicly exposed services
- Potential segmentation weaknesses

This information helps an authorized security team understand the network's attack surface.

Internal network details may require explicit permission and suitable access.

More detailed network discovery is covered in network penetration testing, scanning, and enumeration.

## 12. Personal Information Reconnaissance

Personal and organizational OSINT examines publicly available information that may be relevant to a legitimate investigation.

Examples include:

- Public name and professional role
- Official contact details
- Public professional profiles
- Publicly shared skills
- Published work history
- Official organization affiliations
- Publicly visible social media accounts

Researchers must distinguish between public professional information and sensitive personal information.

**Privacy and ethics:** Do not use reconnaissance to stalk, harass, impersonate, threaten, or expose individuals. Avoid collecting sensitive personal details unless there is a clear, lawful, authorized need.

## 13. Finding Information Using Phone Numbers

Truecaller is a service that may provide caller identification or other information associated with a phone number, depending on its data and availability.

Website: https://www.truecaller.com/

Information shown by such services may be incomplete or incorrect. A name associated with a number should not automatically be treated as verified identity.

Use phone-number lookup tools only for legitimate purposes and respect applicable privacy laws.

## 14. Finding Social Media Accounts

Search engines can help find public professional or organizational profiles.

For example, searching a person's publicly known professional name may reveal:

- LinkedIn profiles
- Public GitHub accounts
- Public professional websites
- Publicly indexed social media accounts

A matching name or username does not prove that two accounts belong to the same person. Verify matches using multiple independent indicators.

## 15. Sherlock

Sherlock is an open-source tool designed to search for usernames across many websites and identify possible matching accounts.

It is useful for studying a person's public digital footprint or checking one's own username exposure.

Repository: https://github.com/sherlock-project/sherlock

### Example

The original course notes demonstrate a search for a sample username:

```bash
python3 sherlock.py example_username
```

The exact invocation may vary depending on the installed version and installation method.

A result may indicate that a username exists on a website, but it does not establish the identity of the account owner.

### Interpreting Results

A Sherlock result may include:

- Website name
- URL of a potential matching profile
- Search status
- Total number of results

Possible errors include false positives, unavailable websites, rate limits, and changed website behavior.

Always verify findings manually when appropriate.

## 16. Important Commands

| Command | Purpose |
|---|---|
| `ping example.com` | Tests ICMP connectivity and may display a resolved address |
| `nslookup example.com` | Queries DNS |
| `host example.com` | Performs DNS lookups |
| `whois example.com` | Retrieves available domain-registration information |
| `dig example.com` | Queries DNS records |
| `dig example.com MX` | Looks up mail exchange records |
| `dig example.com NS` | Looks up name server records |
| `whatweb https://example.com` | Fingerprints website technologies |
| `python3 sherlock.py example_username` | Searches for possible public accounts associated with a username |

Replace example domains and usernames with suitable values from your own lab or an authorized assessment.

## 17. Key Takeaways

- Reconnaissance is the process of collecting and analyzing information about a target.
- Footprinting is another term used for information gathering.
- Active reconnaissance interacts directly with the target or its infrastructure.
- Passive reconnaissance primarily uses publicly available sources.
- OSINT stands for Open Source Intelligence.
- Pre-engagement establishes authorization, scope, objectives, and testing rules.
- A scoping questionnaire identifies assets, restrictions, and testing requirements.
- An NDA addresses confidentiality, while Rules of Engagement define how testing will proceed.
- Search engines, Shodan, Maltego, WHOIS, DNS utilities, WhatWeb, and Sherlock support different information-gathering tasks.
- Reconnaissance findings must be verified before drawing conclusions.
- Public availability does not automatically mean that information may be used for any purpose.
- Active testing must follow explicit authorization and the agreed scope.

### Final Reminder

**Know the target, understand the scope, verify the evidence, and stay authorized.**

Reconnaissance is most effective when it is systematic, ethical, and well documented.

---

@innovatorsemir