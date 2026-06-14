---
tags: [fundamentals, protocol]
---
up:: [[01 Networking Fundamentals]]
# Ports and Protocols

## 🇬🇧 English
A **port** is a numbered endpoint (0–65535) identifying a service on a host. Know these by heart:
- 20/21 FTP, 22 [[SSH]], 23 Telnet, 25 SMTP
- 53 [[DNS]], 67/68 [[DHCP]], 80 HTTP, 443 HTTPS
- 110 POP3, 143 IMAP, 389 LDAP, 445 SMB
- 3389 [[RDP]], 3306 MySQL, 5900 [[VNC]]

Closed/filtered ports are checked with [[Nmap]] and [[Netstat]].

## 🇮🇹 Italiano
Una **porta** è un endpoint numerato (0–65535) che identifica un servizio su un host. Da sapere a memoria: 22 [[SSH]], 53 [[DNS]], 80 HTTP, 443 HTTPS, 3389 [[RDP]]. Le porte si controllano con [[Nmap]] e [[Netstat]].

## Related / Correlati
- [[HTTP and HTTPS]]
- [[Firewalls]]
