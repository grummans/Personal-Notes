### Routing

- The process of directing data packets from a source to a destination.

- Choose the best path across one/more networks.

- Performed by `router`.

- Using `routing table` and `routing protocol` to decide.

### Routing table

- A set of rules that a packet is forwarded to which network through which gateway.

- Each rule holds a destination range, a gateway, a netmask.

E.g:

```
❯ ip route
default via 10.3.2.1 dev wlp0s20f3 proto dhcp src 10.3.3.202 metric 600
10.3.2.0/23 dev wlp0s20f3 proto kernel scope link src 10.3.3.202 metric 600
172.17.0.0/16 dev docker0 proto kernel scope link src 172.17.0.1
192.168.122.0/24 dev virbr0 proto kernel scope link src 192.168.122.1 linkdown
```

-> `Destination` via `Next Hop` dev `Interface`
