### Problem

- When designing a network, we have to decide how IP addressed are laid out.

-> **IP** - **subnetting** - **CIDR notation**

### IP

- **IPv4**: 32bits, from `0-255`

E.g: `192.168.1.1`

- **IPv6**: 128bits

- IPv4 has two parts:
  - **network part (Network ID)**: which network you're on.
  - **host part (Host ID)**: which device on that network.

- Some **private networks**:
  - `10.0.0.0` - `10.255.255.255`
  - `172.16.0.0` - `172.31.255.255`
  - `192.168.0.0` - `192.168.255.255`

### Subnetting

- Split one network into smaller sub-networks (subnets).

- Manage IP address efficiently.

- Keep IPs orginized and secured.

- Borrowing bits from the host part to create more network parts.

E.g: `172.16.0.0` - `172.16.255.255`

- `172.16.0.0` - `172.16.15.255`
- `172.16.16.0` - `172.16.31.255`
- ...

### CIDR notation

- **CIDR (Classless Inter-Domain Routing)**

- Short way to tell "How big is this network?"

- `IP/number` (`192.168.1.10/24`)

```
IPs = 2^(32 - CIDR)
```

E.g:
`192.168.1.0/24` has `2^(32-24) = 2^8 = 256 IPs`
