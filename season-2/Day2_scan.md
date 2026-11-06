# Day 2 – Scanning and Enumeration

## 1. What is Scanning?

- Scanning is the **second phase of Ethical Hacking**.
- It helps examine and test a system based on information gathered during reconnaissance.
- It can also help us gather additional information.
- Scanning is the active phase of probing a target to identify vulnerabilities, services, open ports, and more.
- Scanning focuses more on systems than people.

### Reconnaissance vs Scanning

**Reconnaissance:** Focuses on broad, high-level information about the target.

It may include:
- Organizational structure and employee details.
- Publicly available IP addresses and domain names.
- Technology stack (web servers, frameworks, etc.).
- Potential entry points from open sources, such as exposed subdomains.

**Scanning:** Focuses on technical, low-level details about the target's systems.

It may include:
- Open ports and services.
- Operating system and service versions.
- Network topology.
- Specific vulnerabilities in systems and services.

## 2. Why Do We Perform Scanning?

Scanning helps us to:

- Identify host system information.
- Discover operating systems.
- Identify service versions.
- Discover open ports.
- Discover live systems.

## 3. Network Scanning

Network scanning is a method of scanning a network to gather more information about its devices and services.

Different tools are used for different purposes.

| Purpose | Tools |
|---|---|
| Network scanning | Nmap, Netdiscover |
| Subdomain discovery | Sublist3r, Subfinder, Amass |
| Website scanning | Nikto, Nuclei, Nessus |

## 4. Nmap – Network Mapper

Nmap is a network scanning and exploration tool used by network administrators and security professionals.

It is used to scan:
- Networks
- Ports
- Operating systems
- Services

Nmap is available for Windows and Linux and is included in Kali Linux.

### Check Nmap Installation

```bash
nmap --version
```

Example output:

```text
Nmap version 7.91
Platform: x86_64-pc-linux-gnu
```

Official website: https://nmap.org

## 5. Live System Discovery

Live system discovery means identifying active hosts (clients and servers) on a network.

One common method is using the `ping` command.

### Ping Sweep

Ping sweep is a method of checking whether a host is up or down.

It uses **ICMP (Internet Control Message Protocol)** packets.

The process:
1. The sender sends an ICMP Echo Request.
2. The target receives the request.
3. If the target responds with an Echo Reply, the host is reachable.

### Example: Ping an Ubuntu Server

Our demonstration Ubuntu server has this IP address:

```text
192.168.56.101
```

Check whether the server is reachable:

```bash
ping 192.168.56.101
```

Example output:

```text
64 bytes from 192.168.56.101: icmp_seq=1 ttl=64 time=1.52 ms
64 bytes from 192.168.56.101: icmp_seq=2 ttl=64 time=0.710 ms
64 bytes from 192.168.56.101: icmp_seq=3 ttl=64 time=0.615 ms
```

### Understanding Ping Results

Ping responses can provide information such as:
- Whether a host is reachable.
- Round-trip response time.
- Packet loss and connection stability.
- TTL value.

### TTL – Time To Live

TTL determines how long a packet can exist in a network before being discarded.

- Each time a packet passes through a router (hop), its TTL decreases by 1.
- When TTL reaches 0, the packet is discarded.
- The router sends an ICMP Time Exceeded message.

The original notes give these common TTL examples:

| Operating System | Example TTL |
|---|---:|
| Windows | 108 |
| Linux | 64 |

**Note:** TTL values are not reliable proof of an operating system. They can vary and may be changed by network devices.

### Ping an External IP

Example:

```bash
ping 8.8.8.8
```

This tests connectivity to Google's public DNS server.

## 6. Nmap Ping Sweep

Nmap can also perform host discovery.

### Scan a Single Host

```bash
nmap -sn 192.168.56.101
```

- `-sn` means host discovery without a port scan.

Example output:

```text
Starting Nmap 7.91
Nmap scan report for 192.168.56.101
Host is up (0.0028s latency).
Nmap done: 1 IP address (1 host up)
```

### Discover All Hosts on a Network

Nmap can scan an entire network range instead of checking only one host.

Examples:

```bash
nmap -sn 192.168.56.1-255
```

Using CIDR notation:

```bash
nmap -sn 192.168.56.0/24
```

This helps identify active hosts within the specified network.

### When ICMP Is Blocked

Some organizations and system administrators block ICMP requests.

As a result, a host may appear down even when it is running.

To skip normal host discovery and treat the target as up:

```bash
nmap -Pn 192.168.56.101
```

`-Pn` skips host discovery and proceeds with scanning the target.

**Important:** Ping sweeps are a form of active reconnaissance. Network administrators may detect and log these activities.

## 7. What Is a Port?

A port is a process-specific or application-specific communication endpoint used by transport-layer protocols such as:

- TCP (Transmission Control Protocol)
- UDP (User Datagram Protocol)

A port can be compared to a door in a house. Different doors provide access to different places or services.

Computers have **65,536 port numbers**, ranging from 0 to 65,535.

### Common Port Numbers

| Port | Service | Description |
|---:|---|---|
| 20 | FTP Data | File transfer data |
| 21 | FTP | File transfer control |
| 22 | SSH | Secure Shell |
| 23 | Telnet | Remote login |
| 25 | SMTP | Sending email |
| 53 | DNS | Domain Name System |
| 80 | HTTP | Web traffic |
| 110 | POP3 | Email retrieval |
| 139 | NetBIOS | Network communication |
| 143 | IMAP | Email retrieval |
| 443 | HTTPS | Secure web traffic |
| 445 | SMB | File and printer sharing |

Ports 0–1023 are commonly known as **well-known ports**.

## 8. Port Status

Nmap generally identifies three important port states:

### Open Ports

- The port is accepting connections.
- A service is listening on that port.

### Closed Ports

- The port is reachable, but no application is listening on it.
- The target responds that the connection cannot be established.

### Filtered Ports

- Nmap cannot determine whether the port is open or closed.
- A firewall or packet filter may be blocking the probes.

## 9. Port Discovery with Nmap

Port discovery identifies which ports are open, closed, or filtered on a target.

### Scan Default Ports

```bash
nmap 192.168.56.101
```

By default, Nmap scans the 1,000 most common TCP ports.

### Scan Specific Ports

```bash
nmap -p 80,443,22 192.168.56.101
```

This scans ports 80, 443, and 22.

### Scan All TCP Ports

```bash
nmap -p- 192.168.56.101
```

`-p-` scans all 65,535 TCP ports.

### Example Output

```text
PORT      STATE SERVICE
135/tcp   open  msrpc
139/tcp   open  netbios-ssn
445/tcp   open  microsoft-ds
2179/tcp  open  vmrdp
5357/tcp  open  wsdapi
```

An open port may expose a service that needs to be secured. Unnecessary services should be disabled or restricted.

## 10. Port Scanning: Red Team vs Blue Team

**Red Team Perspective:**
- Sends requests to target ports.
- Identifies open ports and running services.
- Uses the results to understand possible attack surfaces.

**Blue Team Perspective:**
- Monitors incoming connection attempts.
- Analyzes network packets and logs.
- Detects unusual scanning activities.
- Uses security monitoring tools to investigate suspicious traffic.

Port scanning activity can be observed in network traffic captures.

## 11. Netcat (NC)

Netcat is a networking utility that can establish connections to hosts and ports.

It can also be used to check whether a port accepts connections.

### Syntax

```bash
nc -nv IP PORT
```

Example:

```bash
nc -nv 10.129.202.41 111
```

Example output:

```text
(UNKNOWN) [10.129.202.41] 111 (sunrpc) open
```

Check another port:

```bash
nc -nv 10.129.202.41 1102
```

Example output:

```text
Connection refused
```

Options:
- `-n`: Do not use DNS resolution.
- `-v`: Enable verbose output.

## 12. Nmap Scanning Methods

Nmap supports different scanning techniques:

1. TCP Connect Scan
2. TCP SYN Scan (Stealth Scan)
3. UDP Scan
4. Xmas Scan

### 12.1 TCP Connect Scan

TCP Connect Scan is a connection-oriented scanning method.

It uses the TCP three-way handshake.

#### TCP Three-Way Handshake

The three steps are:

1. **SYN:** The client sends a connection request.
2. **SYN-ACK:** The server acknowledges and accepts the request.
3. **ACK:** The client confirms the connection.

After the handshake, a TCP connection is established.

#### TCP Scan Process

- Nmap sends a SYN packet.
- If the target responds with SYN-ACK, the port is open.
- Nmap completes the handshake with ACK.
- If the target responds with RST, the port is closed.
- If there is no clear response, the port may be filtered.

#### Syntax

```bash
nmap -sT 192.168.56.101
```

Nmap commonly uses TCP Connect Scan when it cannot perform a SYN scan, such as without the required privileges.

### 12.2 TCP SYN Scan (Stealth Scan)

SYN Scan is also called a half-open scan.

Unlike a TCP Connect Scan, it does not complete the full TCP three-way handshake.

Process:

1. Nmap sends SYN.
2. If the target sends SYN-ACK, the port is open.
3. Nmap sends RST instead of completing the connection.
4. If the target sends RST, the port is closed.

#### Syntax

```bash
sudo nmap -sS 192.168.56.101
```

It is called a half-open scan because the full TCP connection is not established.

**Note:** SYN scans are not invisible. Firewalls and intrusion detection systems can still detect them.

### 12.3 UDP Scan

UDP Scan checks for services using the User Datagram Protocol.

UDP is connectionless, meaning it does not use the TCP three-way handshake.

UDP scanning can be slower because responses are not always returned.

#### Syntax

```bash
sudo nmap -sU 192.168.56.101
```

UDP services are important to check because some applications rely on UDP rather than TCP.

### 12.4 Xmas Scan

Xmas Scan sends TCP packets with the following flags:

- FIN
- PSH
- URG

These flags are set instead of SYN.

Typical responses:

- RST response: Port is closed.
- No response: Port may be open or filtered.

#### Syntax

```bash
sudo nmap -sX 192.168.56.101
```

The results can vary depending on the operating system and firewall behavior.

## 13. Operating System Detection

Nmap can attempt to identify the operating system of a target.

It analyzes responses from the target, including characteristics of TCP/IP behavior.

### OS Detection Only

```bash
sudo nmap -O 192.168.56.101
```

### Aggressive Detection

```bash
sudo nmap -A 192.168.56.101
```

`-A` enables several advanced features, including:
- OS detection
- Service version detection
- Script scanning
- Traceroute

## 14. Banner Grabbing

Banner Grabbing is a technique used to identify information about services running on a target.

A service banner may reveal:
- Software name
- Service version
- Application details
- Sometimes operating system information

### Nmap Service Version Detection

```bash
nmap -sV 192.168.56.101
```

The `-sV` option attempts to identify running services and their versions.

Banner information can help security professionals identify outdated or vulnerable software.

## 15. Nmap Scan Speed and Timing Templates

Nmap provides six timing templates, from T0 to T5.

They control how quickly Nmap sends probes and waits for responses.

| Option | Name | Description |
|---|---|---|
| `-T0` | Paranoid | Extremely slow |
| `-T1` | Sneaky | Very slow |
| `-T2` | Polite | Slower scanning |
| `-T3` | Normal | Default timing |
| `-T4` | Aggressive | Faster scanning |
| `-T5` | Insane | Extremely fast |

### Paranoid – T0

```bash
nmap -T0 192.168.56.101
```

- Very slow.
- Sends probes sequentially.
- Uses long delays between probes.

### Sneaky – T1

```bash
nmap -T1 192.168.56.101
```

- Slow scanning.
- Uses longer delays.

### Polite – T2

```bash
nmap -T2 192.168.56.101
```

- Slower than the default.
- Reduces network load.

### Normal – T3

```bash
nmap -T3 192.168.56.101
```

- Default timing template.

### Aggressive – T4

```bash
nmap -T4 192.168.56.101
```

- Faster scanning.
- Suitable for reasonably modern and reliable networks.

### Insane – T5

```bash
nmap -T5 192.168.56.101
```

- Very fast scanning.
- May sacrifice accuracy.
- Can increase network load.
- Should only be used when the network and target can handle it.

## 16. Nmap Scripting Engine (NSE)

Nmap includes a scripting engine that allows users to run scripts against hosts and services.

- NSE scripts are written in Lua.
- Scripts are commonly stored in:

```bash
/usr/share/nmap/scripts
```

- Users can also write custom NSE scripts using Lua.

### Run Default Scripts

```bash
nmap -sC 192.168.56.101
```

### Run a Specific Script

```bash
nmap --script banner 192.168.56.101
```

### Run Scripts Matching a Pattern

```bash
nmap -p 22 --script "ssh-*" 192.168.56.101
```

### Important NSE Script Categories and Examples

**Banner Script**

Attempts to retrieve service banners.

```bash
nmap --script banner 192.168.56.101
```

**Broadcast Scripts**

Gather information from network broadcast services.

```bash
nmap --script broadcast 192.168.56.101
```

**Vulnerability Scripts**

Check for known vulnerabilities using relevant NSE scripts.

```bash
nmap --script vuln 192.168.56.101
```

NSE scripts vary in behavior and impact. Review scripts before running them against a system.

## 17. Nmap Output Formats

Nmap can save scan results in different formats.

### Normal Output

```bash
nmap -oN scan.txt 192.168.56.101
```

- `-oN`: Saves normal text output.

### XML Output

```bash
nmap -oX scan.xml 192.168.56.101
```

- `-oX`: Saves results in XML format.

### Greppable Output

```bash
nmap -oG scan.gnmap 192.168.56.101
```

- `-oG`: Saves results in a grep-friendly format.

## 18. Nmap Verbose Mode

Verbose mode displays more information about what Nmap is doing during a scan.

### Basic Verbose

```bash
nmap -v 192.168.56.101
```

### More Detailed Output

```bash
nmap -vv 192.168.56.101
```

### Maximum Verbose Level

```bash
nmap -vvv 192.168.56.101
```

The more `v` characters used, the more detailed the output becomes.

## 19. Nmap Firewall Evasion Techniques

Firewall evasion techniques involve changing how scan packets are sent in an attempt to avoid or bypass network filtering and detection.

Nmap provides several options that can be used to test firewall behavior.

### IDS – Intrusion Detection System

An IDS is a security technology designed to monitor network traffic and system activities for signs of:

- Malicious behavior
- Policy violations
- Unauthorized access
- Suspicious network activity

### Common Nmap Techniques

1. Decoy Scanning
2. Fragmented Packets
3. MAC Address Spoofing
4. Source Port Manipulation

### 19.1 Decoy Scan

Decoy scanning uses additional IP addresses to make it harder to identify the real source of a scan.

The `-D` option specifies decoy addresses.

#### Syntax

```bash
nmap -D DECOY1,DECOY2,DECOY3 TARGET
```

Nmap can also generate random decoy addresses.

```bash
nmap -D RND:5 TARGET
```

This generates five random decoys.

**Purpose:** Make it more difficult for a system administrator to identify the actual scanning source.

### 19.2 Fragment Packets

Packet fragmentation divides packets into smaller fragments.

This technique attempts to make inspection more difficult for some firewalls and intrusion detection systems.

#### Syntax

```bash
nmap -f -p 21 TARGET
```

The `-f` option enables packet fragmentation.

### 19.3 MAC Address Spoofing

MAC address spoofing changes the MAC address used in network communication.

It can be relevant when testing networks that use MAC address filtering.

#### Syntax

```bash
sudo nmap --spoof-mac Apple -Pn TARGET
```

You can also specify a MAC address:

```bash
sudo nmap --spoof-mac MAC_ADDRESS -Pn TARGET
```

### 19.4 Source Port Manipulation

A source port identifies the application or process initiating a network connection.

When a client sends a request, the server uses the connection information to send its response back.

Example:

- Source IP: Your computer
- Destination IP: The server
- Source Port: The client's temporary port
- Destination Port: The server's service port

Nmap provides the `-g` option to specify a source port.

#### Syntax

```bash
nmap -g PORT -p 21 TARGET
```

Example:

```bash
nmap -g 53 -p 21 192.168.56.101
```

This uses source port 53 while scanning destination port 21.

**Note:** Source port manipulation does not automatically bypass a firewall. Modern firewalls inspect connection state and other packet characteristics.

---

## 20. Important Nmap Commands – Quick Reference

| Command | Purpose |
|---|---|
| `nmap --version` | Check Nmap version |
| `ping IP` | Check host connectivity |
| `nmap -sn IP` | Host discovery without port scanning |
| `nmap -Pn IP` | Skip host discovery |
| `nmap IP` | Scan common TCP ports |
| `nmap -p 80,443 IP` | Scan selected ports |
| `nmap -p- IP` | Scan all TCP ports |
| `nmap -sT IP` | TCP Connect Scan |
| `sudo nmap -sS IP` | TCP SYN Scan |
| `sudo nmap -sU IP` | UDP Scan |
| `sudo nmap -sX IP` | Xmas Scan |
| `sudo nmap -O IP` | OS detection |
| `nmap -A IP` | Aggressive detection |
| `nmap -sV IP` | Service version detection |
| `nmap -sC IP` | Default NSE scripts |
| `nmap --script vuln IP` | Run vulnerability scripts |
| `nmap -T4 IP` | Aggressive timing |
| `nmap -v IP` | Verbose output |
| `nmap -oN scan.txt IP` | Save normal output |
| `nc -nv IP PORT` | Connect to a specific port |

**Important:** Replace `IP` or `TARGET` with the authorized target address or domain. Perform scanning only on systems you own or have explicit permission to test.

---

@innovatorsemir