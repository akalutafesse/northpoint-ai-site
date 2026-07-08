# DNS Backup — northpoint-ai.com

Captured: 2026-07-09 via `dig` queries against live DNS.
Registrar/DNS: Squarespace (NS delegated to Google Cloud DNS).

## All existing records

| Type  | Host                    | Value                             | TTL     |
|-------|-------------------------|-----------------------------------|---------|
| A     | @                       | 216.239.32.21                     | 14400   |
| A     | @                       | 216.239.34.21                     | 14400   |
| A     | @                       | 216.239.36.21                     | 14400   |
| A     | @                       | 216.239.38.21                     | 14400   |
| CNAME | www                     | ghs.googlehosted.com              | 3600    |
| MX    | @                       | 1 aspmx.l.google.com              | 3600    |
| MX    | @                       | 5 alt1.aspmx.l.google.com         | 3600    |
| MX    | @                       | 5 alt2.aspmx.l.google.com         | 3600    |
| MX    | @                       | 10 alt3.aspmx.l.google.com        | 3600    |
| MX    | @                       | 10 alt4.aspmx.l.google.com        | 3600    |
| TXT   | @                       | google-site-verification=6vAEg-fcnSmGEtT8VRdG39eicz_ZYFehZo968ysxqQ8 | 3600 |
| TXT   | @                       | v=spf1 include:_spf.google.com ~all | 3600  |
| NS    | @                       | ns-cloud-e1.googledomains.com     | 21600   |
| NS    | @                       | ns-cloud-e2.googledomains.com     | 21600   |
| NS    | @                       | ns-cloud-e3.googledomains.com     | 21600   |
| NS    | @                       | ns-cloud-e4.googledomains.com     | 21600   |
| SOA   | @                       | ns-cloud-e1.googledomains.com cloud-dns-hostmaster.google.com 1 21600 3600 259200 300 | — |

## Record classification

### Web-routing records (WILL CHANGE)
| Type  | Host | Current value           | Purpose                    |
|-------|------|-------------------------|----------------------------|
| A     | @    | 216.239.32.21           | Google Sites apex routing  |
| A     | @    | 216.239.34.21           | Google Sites apex routing  |
| A     | @    | 216.239.36.21           | Google Sites apex routing  |
| A     | @    | 216.239.38.21           | Google Sites apex routing  |
| CNAME | www  | ghs.googlehosted.com    | Google Sites www routing   |

### Email / verification records (DO NOT TOUCH)
| Type  | Host | Value                                                                  | Purpose              |
|-------|------|------------------------------------------------------------------------|----------------------|
| MX    | @    | 1 aspmx.l.google.com                                                   | Google Workspace email |
| MX    | @    | 5 alt1.aspmx.l.google.com                                              | Google Workspace email |
| MX    | @    | 5 alt2.aspmx.l.google.com                                              | Google Workspace email |
| MX    | @    | 10 alt3.aspmx.l.google.com                                             | Google Workspace email |
| MX    | @    | 10 alt4.aspmx.l.google.com                                             | Google Workspace email |
| TXT   | @    | google-site-verification=6vAEg-fcnSmGEtT8VRdG39eicz_ZYFehZo968ysxqQ8  | Google domain verify |
| TXT   | @    | v=spf1 include:_spf.google.com ~all                                    | SPF for email        |

### Infrastructure records (DO NOT TOUCH)
| Type  | Host | Value                              |
|-------|------|------------------------------------|
| NS    | @    | ns-cloud-e1.googledomains.com      |
| NS    | @    | ns-cloud-e2.googledomains.com      |
| NS    | @    | ns-cloud-e3.googledomains.com      |
| NS    | @    | ns-cloud-e4.googledomains.com      |
| SOA   | @    | (managed by Google Cloud DNS)      |

## Rollback instructions

To revert to Google Sites, restore the 5 web-routing records:
1. Delete the 4 GitHub Pages A records (185.199.108-111.153)
2. Delete the CNAME www → akalutafesse.github.io
3. Re-add: A @ → 216.239.32.21, 216.239.34.21, 216.239.36.21, 216.239.38.21
4. Re-add: CNAME www → ghs.googlehosted.com
5. Wait for propagation (up to 4 hours with 14400s TTL on A records)
