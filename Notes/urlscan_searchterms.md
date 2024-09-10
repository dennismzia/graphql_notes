# URLscan.io Paired Search Terms Reference

This document provides a list of useful paired search terms for URLscan.io to help refine your search and gather detailed information about URLs, domains, IPs, and more.

---

## Basic Search Terms
- **Domain**: `domain:example.com`
- **IP Address**: `ip:192.168.1.1`
- **File Type**: `filetype:php`
- **ASN (Autonomous System Number)**: `asn:AS12345`
- **HTTP Status Code**: `status:200`
- **Date Range**: `date:2023-09-01 TO 2023-09-10`
- **Country**: `country:US`
- **Malicious URLs**: `malicious:true`
- **External Resources**: `resource:google.com`
- **Screenshot Content**: `screenshot:Login`
- **Technology**: `tech:WordPress`

---

## Combining Search Terms

### 1. **Combine Domain and HTTP Status**
Find all scans of a domain that returned a specific HTTP status, like `200 OK`:
```bash
domain:example.com AND status:200

domain:example.com AND filetype:php
```