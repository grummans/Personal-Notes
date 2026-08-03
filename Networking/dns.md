### DNS (Domain Name System)

- A "Phone Book"

- Convert domain name into IP.

E.g: `example.com` -> `1.2.3.4`

### How a lookup work?

- When type an url:

1. Machine asks a **resolver** (local/ remote like `1.1.1.1`)
2. The resolver asks a **root** server, which points it to the right **TLD** server ( `.vn`, `.com`, ...)
3. The TLD server points to the domain's **authoritative** server -> it holds the real answer.
4. The authoritative server returns the IP address, and the resolver caches it so the next lookup is instant.

### DNS Records

| Record | What it does                                             |
| ------ | -------------------------------------------------------- |
| A      | Points a name to an IPv4 address                         |
| AAAA   | Points a name to an IPv6 address                         |
| CNAME  | Points a name to another name (alias)                    |
| MX     | Says which mall server handle email for the domain       |
| TXT    | Free-form text, used for verification                    |
| NS     | Says which name servers are authoritative for the domain |
