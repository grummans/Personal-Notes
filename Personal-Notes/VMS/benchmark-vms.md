### Benchmark Server

- Start with 200 camera flows, check performance of server, then increasing the flows to 250, 300, 400,... until the failover.

- In Vivas VMS system, the failover point is about 350 camera.

- NIC is bottleneck point. The more cameras, the more netword bandwidth cosuming -> NIC 1Gbps is bottleneck.

### Solutions

- Update NIC (2.5Gbps/5Gbps/10Gbps/...)

- Expanse Network interface Card + Bonding Technical, a NIC for input stream, a NIC for output.

- Optimize stream: Down bitrate, down main/sub-stream.
