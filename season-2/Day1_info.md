# GTSTv2 — Season 2
# Day 01: Reconnaissance (Information Gathering)

---

# Table of Contents

1. Introduction to Penetration Testing
2. Pre-Engagement Steps
   - Scoping Questionnaire
   - Pre-Engagement Meeting
   - Kick-Off Meeting
3. Reconnaissance / Information Gathering / Footprinting
4. Why Do We Need Reconnaissance?
5. Types of Footprinting
   - Active Footprinting
   - Passive Footprinting
6. What Information Can We Gather?
7. OSINT — Open Source Intelligence
8. OSINT Framework
9. Search Engines
10. Shodan
11. Maltego
12. Website Reconnaissance
13. Computer and Phone Reconnaissance
14. Network Reconnaissance
15. Personal Information Reconnaissance
16. Blackbird
17. Physical Address and IP Geolocation
18. Behaviour and Interest Reconnaissance
19. Applications and Software Reconnaissance
20. Static and Dynamic Analysis
21. Reverse Image Search
22. Google Dorking (Google Hacking)
23. Basic Google Search Operators
24. Advanced Google Search Operators
25. Mixing Google Operators
26. Google Hacking Database (GHDB)
27. GooFuzz
28. Shodan Dorking
29. GitHub Dorking
30. Important Tools and Websites
31. Important Commands
32. Practical Exercises
33. Key Takeaways

---

# 1. Introduction to Penetration Testing

We have previously discussed what penetration testing is and its different types.

Now, we are going to explore the steps performed before and during penetration testing tasks when working as an organization that provides penetration testing services.

When performing penetration testing for companies, there are additional steps beyond the commonly taught five phases of ethical hacking.

## Professional Penetration Testing Process

The course introduces the following stages:

1. **Pre-Engagement**
2. **Information Gathering**
3. **Scanning**
4. **Gaining Access**
5. **Maintaining Access**
6. **Proof of Concept**
7. **Post-Engagement**

These stages provide a structured approach to professional security assessments.

### Red Team and Blue Team

This course mainly follows a Red Team approach, but we will also explore some Blue Team concepts.

- **Red Team:** Simulates adversarial activities to identify security weaknesses.
- **Blue Team:** Defends systems, detects suspicious activities, investigates incidents, and improves security.

Understanding Red Team techniques is very important for Blue Team professionals because defenders need to understand how attacks work to defend against them effectively.

---

# 2. Pre-Engagement Steps

Pre-engagement is the first step in a professional penetration testing engagement.

It is the main legal and preparation stage of the process.

This step takes place before starting any penetration testing activities.

Its purpose is to establish permission and a clear understanding of the systems that will be tested.

Pre-engagement consists of three main activities:

1. Scoping Questionnaire
2. Pre-Engagement Meeting
3. Kick-Off Meeting

## 2.1 Scoping Questionnaire

The scoping questionnaire helps gather detailed information about the target environment.

It identifies:

- Assets that will be tested (scope).
- Type of testing required.
- Testing restrictions.
- Project timelines.
- Client requirements.
- Security services needed.

The questionnaire should clearly explain the available cybersecurity services and allow the client to select one or more services.

### Examples

**Example 1: Network Scope**

A client may authorize testing of:

`172.16.2.32/18`

But testing other network subnets is not permitted.

**Example 2: Website Scope**

A client may authorize testing of their internet-facing website but not their internal intranet.

**Example 3: Testing Type**

A customer may request a Black-Box Penetration Test.

### Types of Penetration Testing Knowledge

- **Black-Box Testing:** The tester has little or no prior knowledge of the target system.
- **White-Box Testing:** The tester has detailed knowledge of the target system.
- **Gray-Box Testing:** The tester has partial knowledge or limited access.

## 2.2 Pre-Engagement Meeting

During this meeting, the details gathered from the scoping questionnaire are discussed and any uncertainties are clarified.

### Participants

- Key stakeholders from the client organization.
- Security team members.
- Project managers.
- Technical leads.
- Legal representatives.

### Outcomes

- Finalization of the testing scope.
- Discussion of potential risks.
- Resolution of uncertainties.
- Legal and compliance considerations.
- Agreement on project requirements.

### Important Agreements

**A. Non-Disclosure Agreement (NDA)**

An NDA is a confidentiality agreement between the client and contractor.

It protects written and verbal information shared during a project.

The parties agree not to disclose confidential project information without proper authorization.

**B. Rules of Engagement (RoE)**

Rules of Engagement define how the penetration testing engagement will happen.

They establish:

- What systems are included in the scope.
- What testing activities are permitted.
- What activities are prohibited.
- Contact addresses and responsible people.
- Communication procedures.
- Testing schedules.
- Emergency procedures.

The client and penetration tester formally agree to these rules before testing begins.

## 2.3 Kick-Off Meeting

"Kick-Off" means to officially start something.

The purpose of this meeting is to officially start the engagement after all preparations are complete.

Topics discussed include:

- Engagement schedule.
- Communication protocols.
- Escalation processes.
- Responsibilities of each team member.
- Final testing approach.
- Retesting or no-retesting arrangements.

The kick-off meeting ensures that everyone understands their responsibilities and that testing can proceed as planned.

**Important:** Never begin penetration testing without proper authorization and a clearly defined scope.

---

# 3. Reconnaissance / Information Gathering / Footprinting

Reconnaissance is also known as:

- Information Gathering
- Footprinting
- Recon

Information gathering means collecting data about a network, host, system, organization, person, or application.

### What is Footprinting?

Footprinting can be understood as collecting information and creating a record of the target's digital footprint.

It is an important part of ethical hacking.

The course emphasizes that reconnaissance is a very important part of the actual hacking process because understanding the target helps determine the next steps.

Examples of information gathered:

- IP addresses.
- Domain names.
- DNS information.
- Operating systems.
- Website technologies.
- Network architecture.
- Publicly exposed services.
- Organizational information.
- Public online accounts.

---

# 4. Why Do We Need Reconnaissance?

Imagine you are planning to rob a bank. What information would you want to know?

- How many police officers are there?
- Where are the doors and exits?
- Are there CCTV cameras?
- Who manages the bank?
- What security systems are being used?

The example demonstrates the importance of understanding a target before taking action.

In cybersecurity:

> To get access to a system, you first have to understand the system.

Reconnaissance helps us:

1. Understand the target system.
2. Identify possible attack surfaces.
3. Determine which testing methodology to use.
4. Select appropriate security testing tools.
5. Identify possible vulnerabilities.
6. Understand the target's technologies and infrastructure.

Knowing the system helps security professionals decide which areas require further investigation.

---

# 5. Types of Footprinting

Based on how information is gathered, reconnaissance is divided into two main types:

1. Active Footprinting
2. Passive Footprinting

## 5.1 Active Footprinting

Active footprinting involves gathering information by directly interacting with the target.

The course describes it as directly contacting the person or target to collect information.

### Examples

- Visiting an organization and asking questions.
- Interacting with someone through social media.
- Sending DNS queries to authorized infrastructure.
- Testing connectivity to an authorized host.
- Connecting to an authorized website to inspect its responses.

### Important Warning

Performing unauthorized active footprinting can be illegal.

Always obtain permission before interacting with or testing systems.

## 5.2 Passive Footprinting

Passive footprinting involves gathering information from publicly available sources, third parties, or other sources without directly probing the target infrastructure.

### Examples

- Checking a bank's publicly posted working hours.
- Searching public websites.
- Reading public social media information.
- Checking publicly available domain records.
- Finding public information through search engines.
- Reviewing public usernames and profiles.

### Active vs Passive Footprinting

| Feature | Active Footprinting | Passive Footprinting |
|---|---|---|
| Interaction | Direct interaction | Public sources and third parties |
| Detection | More likely to be detected | Usually less visible to the target |
| Examples | DNS queries, connectivity tests | Search engines, public records |
| Permission | Required for authorized testing | Privacy and legal restrictions still apply |

---

# 6. What Information Can We Gather?

The course identifies several categories of information.

## A. Hosts

Examples:

- Websites.
- Computers.
- Smartphones.
- Servers.

## B. Networks

Examples:

- Home networks.
- Company networks.
- Organizational networks.

## C. People and Organizations

Examples:

- Public professional information.
- Organization details.
- Public contact information.
- Publicly available social media information.

## D. Applications

Examples:

- Websites.
- Android applications.
- Desktop applications.
- Software frameworks.
- Application functionality.

---

# 7. OSINT — Open Source Intelligence

**OSINT = Open Source Intelligence**

OSINT is the process of gathering and analyzing information from publicly available resources.

It is primarily associated with passive information gathering.

Using OSINT, we can collect information about:

- Systems.
- Users.
- Hosts.
- Organizations.
- Networks.
- Applications.
- Public online activities.

### OSINT Sources

Common sources include:

- Websites.
- Social media.
- Online forums.
- Public records.
- Search engines.
- Public documents.
- Public code repositories.

### Why Is OSINT Important?

- Helps understand the target's digital footprint.
- Identifies publicly exposed information.
- Helps discover relationships between online entities.
- Supports security assessments.
- Helps organizations understand their public exposure.

### OSINT Process

1. Identify the research objective.
2. Select relevant public sources.
3. Collect information.
4. Analyze the information.
5. Verify findings.
6. Document the results.

Remember that publicly available information may be outdated or inaccurate. Always verify important findings.

---

# 8. OSINT Framework

The OSINT Framework is a useful collection of tools and resources for intelligence gathering.

It provides a structured way to explore publicly available information across different categories.

It can be used for:

- Security research.
- Intelligence gathering.
- Strategic planning.
- Digital investigations.
- General research.

**Website:**

https://osintframework.com/

The framework organizes different OSINT tools and resources, making it easier to discover tools for particular investigations.

---

# 9. Search Engines

Search engines are websites and services used to search for documents, media, and other information available on the internet.

They are essential tools for performing OSINT.

### Examples

- Google
- Bing
- Yahoo

Search engines can help discover:

- Websites.
- Public documents.
- Images.
- Public profiles.
- Technical information.
- Public reports.
- Indexed files.

Later in this lesson, we will explore advanced search techniques called Google Dorking.

---

# 10. Shodan

Shodan is a specialized search engine designed to find and index internet-connected devices.

It is often called the search engine for the Internet of Things (IoT).

Unlike traditional search engines such as Google and Bing, which primarily index web pages, Shodan focuses on internet-connected devices and services.

### Examples of Devices Shodan Can Discover

- Servers.
- Routers.
- Webcams.
- Industrial Control Systems (ICS).
- IoT devices.
- Other publicly exposed services.

### Why Is Shodan Useful?

Shodan can help security professionals understand what devices and services are publicly exposed to the internet.

Organizations can use it to investigate their own public-facing infrastructure.

**Website:**

https://www.shodan.io/

### Publicly Exposed Webcams

The course demonstrates how Shodan can be used to discover publicly exposed webcams.

**Security note:** Discovering a publicly exposed device does not give permission to access or control it. Never attempt to view private feeds or interact with devices without authorization.

---

# 11. Maltego

Maltego is a powerful data-mining and visualization tool used for link analysis.

It helps map relationships between different entities.

### Examples of Entities

- People.
- Domains.
- IP addresses.
- Organizations.
- Email addresses.
- Online accounts.

### Main Features

- Graphical visualization of relationships.
- Data analysis.
- Relationship mapping.
- Investigation of complex networks.
- Organization of collected intelligence.

### Why Is Maltego Useful?

When investigating a large environment, information may be spread across many different sources.

Maltego helps visualize relationships and makes complex information easier to understand.

**Website:**

https://www.maltego.com/

---

# 12. Website Reconnaissance

Website reconnaissance involves collecting technical and publicly available information about a website.

The course identifies the following information:

- IP addresses.
- Development frameworks.
- Technologies used.
- Technology versions.
- Website name.
- DNS information.
- Virtual hosts (VHOST).
- Subdomains.

VHOST and subdomain enumeration will be covered in more detail in the Web Hacking class.

## 12.1 Finding a Website's IP Address

There are several methods to discover the IP address associated with a domain.

### A. Active Reconnaissance

#### Method 1: ping

```bash
ping example.com
```

The command attempts to send ICMP packets to the target hostname.

It may display the resolved IP address.

#### Method 2: nslookup

```bash
nslookup example.com
```

This command queries DNS to obtain information about the domain.

#### Method 3: host

```bash
host example.com
```

This command performs DNS lookups for the specified domain.

### B. Passive Reconnaissance

An online DNS lookup service can be used.

Website:

https://www.nslookup.io/

It can help retrieve publicly available DNS information.

### Important Note

The course demonstration emphasizes entering the domain name without adding `https://`.

For example:

```text
example.com
```

Instead of:

```text
https://example.com
```

The DNS commands generally expect a hostname rather than a complete URL.

Also, a domain may resolve to different IP addresses because of CDNs, load balancers, or DNS configurations.

## 12.2 Finding Development Frameworks

We can identify the technologies and frameworks used by a website.

The course introduces browser extensions and terminal tools.

### A. Wappalyzer

Wappalyzer is a browser extension and technology profiling service.

It can help identify technologies such as:

- JavaScript frameworks.
- Content Management Systems.
- Web servers.
- Analytics tools.
- Programming technologies.

### B. BuiltWith

BuiltWith provides information about technologies used by websites.

Website:

https://builtwith.com/

### C. WhatWeb

WhatWeb is a command-line tool used for website technology fingerprinting.

Example:

```bash
whatweb https://example.com
```

It may identify:

- Web server technologies.
- Frameworks.
- CMS platforms.
- Libraries.
- Other technology indicators.

Only perform active fingerprinting against authorized targets.

## 12.3 Getting the Website Name

A website's name can often be identified by examining:

- The website title.
- Text displayed inside the webpage.
- The domain name.
- Public website information.

For example, the HTML page title can be inspected through the browser.

## 12.4 Getting Domain Details

The course introduces WHOIS and DIG for domain information gathering.

### WHOIS

WHOIS is a protocol and associated lookup service used to retrieve available domain registration information.

Install WHOIS on Debian-based Linux:

```bash
sudo apt update
sudo apt install whois
```

Example:

```bash
whois example.com
```

### DIG

`dig` is a command-line DNS lookup utility.

Examples:

```bash
dig example.com
dig example.com A
dig example.com AAAA
dig example.com MX
dig example.com NS
dig example.com TXT
```

Common DNS record types:

| Record | Meaning |
|---|---|
| A | IPv4 address |
| AAAA | IPv6 address |
| MX | Mail exchange |
| NS | Name server |
| TXT | Text information |

---

# 13. Computer and Phone Reconnaissance

Reconnaissance of computers and phones involves gathering information about hosts and devices.

### Information We Can Gather

1. IP addresses.
2. Operating system information.
3. Hostname.
4. MAC address.
5. Open services.
6. Open ports.

### Important Concepts

**IP Address:** An address used to identify a device or network interface in an IP network.

**Operating System:** The software that manages the computer's hardware and software resources.

**Hostname:** The name assigned to a device on a network.

**MAC Address:** A hardware-layer address associated with a network interface.

**Open Port:** A network port on which a service is accepting connections.

Detailed host discovery, open-port identification, and service enumeration will be covered in the Scanning and Enumeration class.

---

# 14. Network Reconnaissance

Network reconnaissance involves collecting information about a network and its structure.

### Information We Can Gather

- IP addresses.
- Network architecture.
- Network classes and types.
- Subnets.
- VLANs.
- Hosts on the network.
- Network security and configuration information.

### Important Concepts

**IP Address:** Identifies a network interface in an IP network.

**Network Architecture:** Describes how network devices and components are organized and connected.

**Subnet:** A logical division of an IP network.

**VLAN:** Virtual Local Area Network, used to logically separate devices within a network infrastructure.

**Hosts:** Devices connected to a network.

Detailed network reconnaissance will be explored in the Network Penetration Testing class.

---

# 15. Personal Information Reconnaissance

Personal information reconnaissance involves identifying publicly available information about individuals.

The course discusses the following categories:

- Full name.
- Publicly shared address information.
- Social media accounts.
- Public contact information.
- Interests.
- Job.
- Friends and public connections.
- Public status information.
- Skills.

There are different techniques and tools used for collecting publicly available information.

## 15.1 Getting Names Using Phone Numbers

The course introduces Truecaller.

**Truecaller:**

https://www.truecaller.com/

Truecaller is a service that provides caller identification and related phone-number information, depending on its available data.

The course mentions that phone numbers may appear in:

- Public social media profiles.
- Telegram profiles.
- Public promotions.
- Websites.

Some services may also provide associated information, such as names or other publicly available contact details.

**Privacy note:** Phone-number lookup can reveal personal information. Use these services only for legitimate purposes, and do not expose or misuse another person's private information.

## 15.2 Finding Social Media Addresses

If you have a person's publicly known name, search engines can help locate their public profiles.

Examples:

- Google.
- Bing.
- Yahoo.

You can search for public professional accounts and official profiles.

A matching name alone does not prove that a profile belongs to a particular person. Verify identities using reliable, independent information.

---

# 16. Sherlock

Sherlock is an open-source OSINT tool available on GitHub.

It searches for a username across different websites and identifies possible matching accounts.

### Example from the Course

The course demonstrates searching for the username:

```text
nathanhailu
```

Example command:

```bash
python3 sherlock.py nathanhailu
```

The example output includes possible matches on:

- Academia.edu
- Arduino
- Chess
- Clubhouse
- Codecademy

The demonstration reports five possible results.

### Understanding Sherlock Results

Sherlock checks whether a username may exist on different platforms.

Its output can contain:

- Website name.
- Profile URL.
- Search result status.
- Number of possible matches.

### Important

A matching username does not automatically mean that all accounts belong to the same person.

False positives can occur. Always verify results manually.

**GitHub:**

https://github.com/sherlock-project/sherlock

---

# 17. Blackbird

Blackbird is another OSINT tool introduced in the course.

It facilitates searching for user accounts by username or email across different online platforms.

### Main Features

- Username searching.
- Email-based searching.
- Searching across multiple platforms.
- Identifying possible online accounts.
- Supporting digital investigations.

Blackbird can help researchers understand the public digital footprint associated with a username or email address.

**Security and privacy note:** Only investigate accounts and identifiers for legitimate, authorized purposes.

---

# 18. Physical Address and IP Geolocation

The course introduces the relationship between publicly available location information and IP geolocation.

## 18.1 Finding Publicly Shared Locations

People sometimes share location information through:

- Public social media profiles.
- Public posts.
- Photographs.
- Public event information.
- Publicly shared business or professional information.

Such information may provide clues about a publicly shared location.

## 18.2 IP Geolocation

IP geolocation is the process of estimating a geographic location associated with an IP address.

The course introduces the following website:

https://www.iplocation.net/

### Important Concepts

An IP geolocation service may provide an estimated:

- Country.
- Region.
- City.
- Internet Service Provider.
- Network organization.

### Important Limitations

IP geolocation is not exact physical location tracking.

It may be inaccurate because of:

- VPNs.
- Proxy servers.
- Mobile networks.
- ISP routing.
- Shared public IP addresses.
- Incorrect or outdated databases.

Private IP addresses, such as `192.168.x.x`, `10.x.x.x`, and `172.16.x.x` through `172.31.x.x`, are not normally geolocatable to a person's physical location through public IP databases.

**Privacy and safety:** Do not send tracking links, collect someone's IP address, or attempt to determine their physical location without proper consent and authorization.

---

# 19. Behaviour and Interest Reconnaissance

The course introduces Behaviour and Interest Reconnaissance as another area of OSINT.

People often share information about their interests and activities on social media.

Publicly available information may include:

- Interests.
- Hobbies.
- Professional activities.
- Publicly shared opinions.
- Public social connections.
- Events attended.
- Publicly shared photographs.

### Examples of Public Sources

**Instagram**

Public posts and profiles may reveal interests, hobbies, and activities.

**Telegram**

Public profiles and channels may contain information shared by users.

### Why Is This Useful in Security?

Understanding public information can help organizations assess privacy exposure and identify social-engineering risks.

The course also introduces social engineering as a later topic.

**Important:** Behavioural profiling can be sensitive. Avoid making unsupported assumptions about a person's religion, ideology, family, or private life based on online activity.

---

# 20. Applications and Software Reconnaissance

Applications and software are another category of reconnaissance.

The course divides application analysis into two main types:

1. Static Analysis.
2. Dynamic Analysis.

## 20.1 Static Analysis

Static analysis means analyzing an application without executing it.

It involves examining the application's code and structure.

### Information We Can Gather

- Programming language used.
- Frameworks used.
- File structure.
- Application assets.
- Configuration files.
- Code organization.

### Examples

**Android Applications**

Possible technologies include:

- Java.
- Kotlin.
- Flutter.
- JavaScript-based technologies.

**Desktop Applications**

Possible technologies include:

- JavaScript.
- C#.
- C++.

Static analysis can help identify how an application is built without running it.

## 20.2 Dynamic Analysis

Dynamic analysis means analyzing an application while it is executing.

It focuses on the application's runtime behaviour.

### Information We Can Gather

- Application logic.
- Application functionality.
- Requests sent to servers.
- Responses received from servers.
- Runtime behaviour.
- Interactions between application components.

### Static vs. Dynamic Analysis

| Feature | Static Analysis | Dynamic Analysis |
|---|---|---|
| Execution | No execution required | Application is executed |
| Main focus | Code and structure | Runtime behaviour |
| Programming language | Can often be identified | May be inferred from runtime behaviour |
| Frameworks | Can be identified through code and assets | Can sometimes be inferred |
| Network requests | Examined from code where possible | Observed during execution |

### Course Example

The lesson demonstrates analyzing an Android application.

**Question:** What kind of analysis is this?

**Answer:** STATIC ANALYSIS.

Reason: The application is being examined without executing it.

---

# 21. Reverse Image Search

Reverse Image Search is a technique that allows us to search using an image instead of text.

Normally, we enter keywords into a search engine.

With reverse image search, we provide an image, and the search engine searches for visually similar images or related information.

### Example

Imagine someone posts a photograph with a recognizable background.

The person does not mention where the photograph was taken.

A reverse image search may help locate:

- Similar photographs.
- Other copies of the image.
- Websites containing the image.
- Possible locations or related landmarks.

Reverse image search is not always 100% accurate.

### Tools

**1. TinEye**

https://tineye.com/

**2. Labnol Reverse Image Search**

https://www.labnol.org/reverse/

**3. Google Images**

https://images.google.com/

### Applications of Reverse Image Search

- Finding duplicate images.
- Discovering the original source of an image.
- Identifying publicly available copies.
- Researching landmarks and locations.
- Checking whether an image appears elsewhere online.

### Important Note

Reverse image search results are clues, not definitive proof of identity or location.

---

# 22. Google Dorking (Google Hacking)

Google Dorking is also called Google Hacking.

It involves using advanced Google search operators to make search results more specific.

### Important Clarification

Google Hacking does NOT mean hacking into Google's servers.

Instead, it means using Google search operators to locate particular information indexed by Google.

### Uses of Google Dorking

- Finding specific documents.
- Searching for particular file types.
- Locating public technical information.
- Finding indexed pages.
- Identifying accidentally exposed information.
- Supporting authorized security assessments.

Google Dorking can be a powerful OSINT technique.

However, finding an exposed resource does not mean that you have permission to access or download sensitive information.

---

# 23. Basic Google Search Operators

The course introduces several basic operators.

## 23.1 Plus Sign (+)

The course notes introduce `+` as an operator associated with including terms in a search.

Modern Google Search generally treats punctuation such as `+` differently from older search behavior, so it should not be relied upon as a strict inclusion operator.

Example:

```text
ethical hacking +network
```

## 23.2 Minus Sign (-)

The minus sign excludes a particular term from search results.

Example:

```text
ethical hacking -beginner
```

This searches for ethical hacking information while excluding results associated with the excluded term.

## 23.3 Exact Search (" ")

Quotation marks search for an exact phrase.

Example:

```text
"Nathan Hailu"
```

This helps find pages containing that specific phrase rather than pages containing the words independently.

## 23.4 Wildcard (*)

The asterisk can act as a wildcard or placeholder for unknown words in certain Google searches.

Example:

```text
"ethical hacking is *"
```

Google attempts to find matching phrases where the wildcard appears.

## 23.5 Boolean OR (|)

The vertical bar `|` represents an OR-style search.

Example:

```text
cybersecurity | "ethical hacking"
```

This can help search for pages matching either term.

The word `OR` can also be used.

Example:

```text
cybersecurity OR "ethical hacking"
```

---

# 24. Advanced Google Search Operators

Advanced search operators are special search syntaxes that help narrow search results.

The course introduces four main operators.

## 24.1 intitle

The `intitle` operator searches for a word or phrase in the page title.

### Example 1

```text
intitle:index.of
```

This searches for pages with `index.of` in their titles.

### Example 2

```text
intitle:"Hackers Bible"
```

This searches for pages whose titles contain the phrase "Hackers Bible".

## 24.2 inurl

The `inurl` operator searches for a specific term inside a URL.

Example:

```text
inurl:view/index.shtml
```

It searches for URLs containing the specified path.

## 24.3 filetype

The `filetype` operator searches for particular file formats.

Example:

```text
"Hacking" filetype:pdf
```

This searches for PDF documents containing the word "Hacking".

Another example:

```text
filetype:txt
```

This searches for indexed text files.

Other possible file types include:

- pdf
- doc
- docx
- xls
- xlsx
- ppt
- pptx
- txt

## 24.4 intext

The `intext` operator searches for a specific word or phrase within the text of a webpage.

Example:

```text
intext:"Hackers in Ethiopia"
```

This searches for pages containing that phrase in their visible text.

---

# 25. Mixing Google Operators

One of the powerful features of Google Dorking is combining multiple search operators.

Combining operators helps narrow down results.

### Example 1: Search for PDF Documents

```text
"ethical hacking" filetype:pdf
```

### Example 2: Search for a Specific Phrase in Page Titles

```text
intitle:"cybersecurity training"
```

### Example 3: Search Within a Specific Website

The `site:` operator restricts results to a particular domain.

Example using a personal or authorized test domain:

```text
site:example.com cybersecurity
```

### Example 4: Search for a File Type on a Specific Website

```text
site:example.com filetype:pdf
```

### Example 5: Exclude a Search Term

```text
site:example.com cybersecurity -jobs
```

### Example 6: Combine Exact Phrase and File Type

```text
site:example.com "security policy" filetype:pdf
```

### Important Operators Summary

| Operator | Purpose |
|---|---|
| `-` | Excludes a search term |
| `" "` | Searches for an exact phrase |
| `*` | Wildcard or placeholder |
| `OR` | Searches for either term |
| `intitle:` | Searches within page titles |
| `inurl:` | Searches within URLs |
| `filetype:` | Searches for specific file types |
| `intext:` | Searches within page text |
| `site:` | Restricts results to a website or domain |

### Why Are These Operators Useful?

Security professionals use search operators to:

- Improve research efficiency.
- Find relevant documents.
- Discover publicly indexed information.
- Investigate their own organization's public exposure.
- Support authorized security assessments.

---

# 26. Google Hacking Database (GHDB)

GHDB stands for **Google Hacking Database**.

It is a collection of Google search queries, commonly called Google Dorks, used to identify different types of information exposed through search engines.

It is maintained as part of the Exploit Database project.

### Website

https://www.exploit-db.com/google-hacking-database

### Why Is GHDB Useful?

It provides examples of search patterns that can help security professionals understand:

- Publicly indexed files.
- Exposed directories.
- Information disclosure.
- Misconfigured web resources.
- Potentially sensitive publicly indexed information.

### Warning About Excessive Searches

The course notes explain that repeatedly performing many searches from the same IP address may cause Google to temporarily block or challenge additional requests.

This is because Google uses automated systems to identify unusual search activity.

### Security Reminder

Use GHDB for authorized security research and for checking your own organization's exposure.

Do not access, download, disclose, or misuse confidential information discovered through search results.

---

# 27. GooFuzz

GooFuzz is an OSINT-oriented tool introduced in the course.

It uses advanced Google searches to help discover publicly indexed resources.

### Functions Mentioned in the Course

- Directory enumeration.
- File enumeration.
- Subdomain enumeration.
- Parameter enumeration.

The course describes it as using Google search techniques to identify resources without directly probing the target server in the same way as conventional scanning.

However, search-engine queries may still be logged, and the tool's actual behavior depends on its implementation and configuration.

### GitHub Repository

https://github.com/m3n0sd0n4ld/GooFuzz

### Why Is It Useful?

It demonstrates how Google Dorking can be automated to organize and discover indexed resources.

Use it only for authorized investigations and permitted targets.

---

# 28. Shodan Dorking

Shodan Dorking is an advanced method of using Shodan search filters to locate particular internet-connected devices and services.

It uses search terms, operators, and filters.

The course notes that creating a Shodan account is required for its practical demonstration.

Website:

https://www.shodan.io/

## 28.1 Basic Shodan Searches

A normal search may include terms such as:

```text
http
```

```text
webcam
```

These terms help search for internet-connected services and devices indexed by Shodan.

## 28.2 Shodan Search Filters

### A. Title Filter

The `title` filter searches for a particular title.

Example:

```text
title:"YOUR TITLE"
```

Course example:

```text
title:"Geez"
```

### B. HTTP HTML Filter

The `http.html` filter searches for text found in the HTML content returned by a web service.

Example:

```text
http.html:Apache
```

This searches for services whose indexed HTTP HTML content contains the word Apache.

### C. Hostname Filter

The `hostname` filter searches for services associated with a hostname.

Course example:

```text
hostname:geeztech.com,geezsecurity.com
```

This demonstrates searching for either of the specified hostnames.

### D. Port Filter

The `port` filter searches for services associated with a particular port.

Example:

```text
port:1000
```

This searches for results associated with port 1000.

### E. SSH on Non-Standard Ports

The course demonstrates:

```text
ssh -port:22
```

This is intended to search for SSH services while excluding the standard SSH port.

### F. Country Filter

The `country` filter restricts results by country code.

Example:

```text
country:"ET"
```

`ET` is the country code for Ethiopia.

### G. City Filter

The `city` filter restricts results to a particular city.

Example:

```text
city:"Addis Ababa"
```

### H. Product Filter

The `product` filter searches for a particular product.

Example:

```text
product:Apache
```

### I. Operating System Filter

The `os` filter searches for a particular operating system.

Example:

```text
os:Windows
```

## 28.3 Combining Shodan Filters

The course explains that multiple filters can be combined.

For example, when auditing your own authorized infrastructure, you may combine a country filter with a product or port filter.

### Important Shodan Filters Summary

| Filter | Purpose | Example |
|---|---|---|
| `title:` | Search by page title | `title:"Geez"` |
| `http.html:` | Search HTML content | `http.html:Apache` |
| `hostname:` | Search by hostname | `hostname:example.com` |
| `port:` | Search by port | `port:443` |
| `country:` | Search by country | `country:"ET"` |
| `city:` | Search by city | `city:"Addis Ababa"` |
| `product:` | Search by product | `product:Apache` |
| `os:` | Search by operating system | `os:Windows` |

**Important:** Shodan syntax and available filters may change. Consult its official documentation for current syntax.

Shodan results show publicly indexed information, not permission to access the discovered systems.

---

# 29. GitHub Dorking

GitHub is a platform where developers collaborate, create, and maintain software projects.

It provides:

- Source code repositories.
- Version control.
- Collaboration.
- Open-source projects.
- Issue tracking.
- Documentation.

The course highlights that repositories may accidentally contain sensitive information.

Examples include:

- API keys.
- Database credentials.
- FTP credentials.
- Passwords.
- Configuration secrets.

This creates a potential security risk.

## 29.1 GitHub Reconnaissance

The course recommends beginning by searching for a target organization's public repositories.

The objective is to understand its repository architecture and publicly available development information.

Information to examine includes:

- Number of repositories.
- Commit history.
- Programming languages.
- Project structures.
- Public contributions.
- Technology choices.

## 29.2 GitHub Dorking

GitHub Dorking involves using GitHub's search capabilities to find specific code, files, or information.

The course introduces sensitive keywords such as:

```text
api_key
```

```text
key
```

```text
password
```

```text
secret
```

```text
DB_PASSWORD
```

```text
admin
```

These terms can help identify accidental secret exposure in repositories you own or are authorized to audit.

### Example: Searching Your Own Organization

Use GitHub's search interface to investigate repositories belonging to your own organization.

You can narrow searches using repository and organization filters.

For example:

```text
org:YOUR_ORGANIZATION
```

A search can then be restricted to that organization's repositories.

### Why Is GitHub Dorking Important?

Developers sometimes accidentally commit:

- API keys.
- Database passwords.
- Authentication tokens.
- Private configuration values.
- Other credentials.

If exposed, these secrets may allow unauthorized access to services.

### Important Defensive Actions

If you discover a leaked credential in your own repository:

1. Revoke or rotate the credential immediately.
2. Investigate whether it was accessed.
3. Review relevant logs.
4. Remove the exposed secret from the repository history where appropriate.
5. Store secrets in environment variables or a secret-management service.
6. Add secret scanning to the development workflow.

Simply deleting a secret from the latest commit does not guarantee that it has disappeared from Git history or other copies.

**Never use leaked credentials to access an account, database, or service.**

---

# 30. Important Tools and Websites

The following table summarizes the tools introduced in Day 1.

| Tool | Purpose | Website |
|---|---|---|
| OSINT Framework | Collection of OSINT tools | https://osintframework.com/ |
| Google | Search engine | https://www.google.com/ |
| Bing | Search engine | https://www.bing.com/ |
| Shodan | Internet-connected device search engine | https://www.shodan.io/ |
| Maltego | Link analysis and visualization | https://www.maltego.com/ |
| nslookup.io | Online DNS lookup | https://www.nslookup.io/ |
| Wappalyzer | Website technology identification | https://www.wappalyzer.com/ |
| BuiltWith | Website technology information | https://builtwith.com/ |
| WhatWeb | Website technology fingerprinting | https://github.com/urbanadventurer/WhatWeb |
| WHOIS | Domain registration lookup | https://who.is/ |
| Truecaller | Caller identification service | https://www.truecaller.com/ |
| Sherlock | Username OSINT | https://github.com/sherlock-project/sherlock |
| Blackbird | Username and email OSINT | https://github.com/p1ngul1n0/blackbird |
| IP Location | IP geolocation lookup | https://www.iplocation.net/ |
| TinEye | Reverse image search | https://tineye.com/ |
| Google Images | Reverse image search | https://images.google.com/ |
| Labnol | Reverse image search resource | https://www.labnol.org/reverse/ |
| GHDB | Google Hacking Database | https://www.exploit-db.com/google-hacking-database |
| GooFuzz | Google-based OSINT automation | https://github.com/m3n0sd0n4ld/GooFuzz |
| GitHub | Code hosting and repository search | https://github.com/ |

---

# 31. Important Commands

## DNS and Domain Reconnaissance

### 1. Ping

```bash
ping example.com
```

Purpose: Test connectivity using ICMP.

### 2. Nslookup

```bash
nslookup example.com
```

Purpose: Retrieve DNS information.

### 3. Host

```bash
host example.com
```

Purpose: Perform DNS lookups.

### 4. WHOIS Installation

```bash
sudo apt update
sudo apt install whois
```

### 5. WHOIS Lookup

```bash
whois example.com
```

Purpose: Retrieve available domain-registration information.

### 6. DIG

```bash
dig example.com
```

Purpose: Query DNS records.

### 7. DIG IPv4

```bash
dig example.com A
```

### 8. DIG IPv6

```bash
dig example.com AAAA
```

### 9. DIG Mail Records

```bash
dig example.com MX
```

### 10. DIG Name Servers

```bash
dig example.com NS
```

## Website Technology Identification

### 11. WhatWeb

```bash
whatweb https://example.com
```

Purpose: Identify possible technologies used by a website.

## Username OSINT

### 12. Sherlock

```bash
python3 sherlock.py example_username
```

Purpose: Search for possible public accounts associated with a username.

---

# 33. Key Takeaways

After completing Day 1, you should understand the following concepts.

## Penetration Testing

- Professional penetration testing involves pre-engagement and post-engagement activities.
- Pre-engagement establishes the legal and operational requirements.
- Scoping defines what is and is not allowed.
- NDA protects confidential information.
- Rules of Engagement establish testing procedures.

## Reconnaissance

- Reconnaissance is information gathering.
- Footprinting is another term used for gathering information about a target.
- Active footprinting involves direct interaction.
- Passive footprinting primarily relies on public sources.
- Reconnaissance helps identify possible attack surfaces.

## OSINT

- OSINT stands for Open Source Intelligence.
- It uses publicly available information.
- OSINT Framework helps discover information-gathering resources.
- Search engines are important OSINT tools.
- Shodan searches for internet-connected devices.
- Maltego visualizes relationships between entities.
- Sherlock and Blackbird help search for possible public accounts.

## Website Reconnaissance

- `ping`, `nslookup`, and `host` can help with hostname and DNS investigation.
- WHOIS provides available domain-registration information.
- DIG queries DNS records.
- Wappalyzer and BuiltWith help identify website technologies.
- WhatWeb performs website technology fingerprinting.

## Personal and Application Reconnaissance

- Public information can help build an understanding of an organization's digital footprint.
- Reverse image search helps discover similar images and their possible sources.
- Static analysis examines applications without execution.
- Dynamic analysis examines applications while running.

## Google Dorking

- Google Dorking uses advanced search operators.
- `intitle:` searches page titles.
- `inurl:` searches URLs.
- `filetype:` searches specific file types.
- `intext:` searches page text.
- `site:` restricts searches to a particular domain.
- GHDB contains examples of Google search queries.

## Shodan and GitHub

- Shodan Dorking uses filters to discover publicly indexed devices and services.
- GitHub Dorking helps investigate public code repositories.
- Exposed credentials are serious security risks.
- Discovered credentials should be reported and revoked, not used.

---

# Quick Summary

- **Penetration Testing:** Authorized testing to find security weaknesses.
- **Reconnaissance:** Collecting information about a target.
- **Passive Recon:** Gathering information without directly interacting with the target.
- **Active Recon:** Directly interacting with the target.
- **OSINT:** Collecting intelligence from publicly available sources.
- **Footprinting:** Identifying a target's digital presence.
- **Pre-engagement:** Agreeing on scope, NDA, and Rules of Engagement.
- **Website Recon:** Finding IP, DNS, WHOIS, hosting, and technologies.
- **Google Dorking:** Using advanced Google search operators.
- **Shodan:** Searching for internet-connected devices.
- **GitHub Dorking:** Finding potentially exposed information in public repositories.
- **Static Analysis:** Examining files without running them.
- **Dynamic Analysis:** Examining applications while running.
- **Red Team:** Offensive security.
- **Blue Team:** Defensive security.

## Important Tools

Google, Shodan, Maltego, Sherlock, Truecaller, Wappalyzer, BuiltWith, WhatWeb, and OSINT Framework.

## Remember

Always get proper authorization before conducting security testing.

# Final Reminder

> Know the target. Understand the environment. Gather information. Analyze the results. Verify your findings.

Reconnaissance is one of the most important foundations of ethical hacking.

A good penetration tester does not simply start attacking a system. They first understand the target, define the scope, gather information, and plan the assessment.

---

@innovatorsemir