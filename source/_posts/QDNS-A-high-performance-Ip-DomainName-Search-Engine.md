---
title: 'QDNS: A high performance Ip-DomainName Search Engine'
date: 2019-02-27 21:17:48
tags: Design
categories: System Design
---

### Terms about QDNS:
DNS: Domain Name System
Dig : Domain Information Groper
QDNS : An IP to domain name search engine.
DN : Domain Name
CV : cluster View of IP segments.

---

Typical type of DNS record:

A (Address record): Map a domain name to its ip.
CNAME Canonical name record): Map a domain name to its alias, for example www.baidu.com -> www.a.shifen.com.
MX (Mail exchange record): Maps a domain name to a list of message transfer agents for that domain.
NS (Name server record): return domain name of a dns server who will tell you the ip you want.
SOA (Start of [a zone of] authority record): tell you who have the original record answer you want.

