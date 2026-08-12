### Vivas 10/08/2026

Problem:

- Network in VMS Server is bottleneck at 1Gbps (limit of NIC).

-> Add another NIC then bonding them into one unique NIC.

- VMS Server is using _systemd-network_ to manage network.

Aim:

```text
enp2s0 -------------------\
                           \
                            bond0 ---- 10.3.3.131/23
                           /
enx6c1ff7bb3c64 ----------/

bond0:
  mode = 802.3ad
  LACP = enabled
```
