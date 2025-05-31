#  Cybersecurity Incident Report – DNS Server Unreachable

**Author:** Jonathan Arape  
**Date:** [5/31/2025]  
**Tool Used:** tcpdump  
**Topic:** Network Analysis – DNS Failure Investigation  
**Tags:** UDP, ICMP, DNS, Incident Response

---

## 🧾 Summary of the Problem

Scenario

Review the scenario below. Then complete the step-by-step instructions.

You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. Several customers of clients reported that they were not able to access the client company website www.yummyrecipesforme.com, and saw the error “destination port unreachable” after waiting for the page to load. 

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. To start, you attempt to visit the website and you also receive the error “destination port unreachable.” To troubleshoot the issue, you load your network analyzer tool, tcpdump, and attempt to load the webpage again. To load the webpage, your browser sends a query to a DNS server via the UDP protocol to retrieve the IP address for the website's domain name; this is part of the DNS protocol. Your browser then uses this IP address as the destination IP for sending an HTTPS request to the web server to display the webpage  The analyzer shows that when you send UDP packets to the DNS server, you receive ICMP packets containing the error message: “udp port 53 unreachable.” 



Upon analyzing a captured `tcpdump` log, it was observed that multiple outgoing **UDP packets** were sent from the client machine `192.51.100.15` to a DNS server `203.0.113.2` on port **53** (standard for DNS queries). However, instead of valid DNS responses, the client received multiple **ICMP "Destination Port Unreachable"** messages, indicating that port 53 was not responsive.

---

## Protocols Involved

- **UDP**: Used for sending DNS queries.
- **ICMP**: Returned by the DNS server indicating port 53 was unreachable.

---

##  Detailed Observations

- The issue occurred when attempting to resolve the domain:  
  `www.yummyrecipesforme.com`
  
- All DNS requests failed, returning ICMP errors.
  
- The DNS server at `203.0.113.2` responded with multiple **ICMP "port unreachable"** messages.
  
- The errors were persistent and affected multiple users and attempts.

---

##  Data Analysis and Explanation

### Initial Report
Users reported being unable to access `www.yummyrecipesforme.com`. Browsers showed:  
> “destination port unreachable”

### Investigation
As a cybersecurity analyst, I replicated the issue and used `tcpdump` to trace packets. The analysis confirmed that **DNS resolution was consistently failing** due to ICMP responses from the DNS server.

### Timeline of Events
- DNS queries sent to `203.0.113.2` using UDP port 53.
- Server returned ICMP errors instead of DNS replies.
- No DNS resolution → Website inaccessible.

---

## Current Status

- The DNS server is **not responding** on port 53.
- Users **cannot resolve the domain**, making the website unreachable.

---

##  Discovered Indicators

- ICMP messages confirm **unreachable port 53**.
- Multiple failed DNS attempts.
- Potential signs of a **DDoS attack** targeting the DNS server.

---

##  Next Steps

1. **Report** the potential attack to the DNS hosting provider.
2. **Escalate** the issue to the incident response team.
3. **Implement protections**:
   - Firewall rules
   - DNS-level rate limiting
   - Switch to Cloudflare DNS or Google DNS
4. **Monitor** ICMP and UDP traffic for ongoing issues.
5. **Configure a failover** DNS provider to restore availability.

---

##  Presumed Root Cause

The incident is likely due to a **Distributed Denial-of-Service (DDoS) attack** aimed at UDP port 53 of the DNS server. The attack causes unavailability of DNS services, resulting in failed resolution of the domain name and loss of access to the client’s website.

---

>  *This incident report was created as part of my cybersecurity training. It demonstrates my ability to analyze network logs, identify protocol behavior, and propose effective responses to security events.*

