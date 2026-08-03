## Component

Diagram

```text
                  Keepalived
                       |
      ----------------------------------
      |                |               |
   VRRP Engine     Health Check     Notify
      |                |               |
Election Master   check_script     notify.sh
```

### VRRP Engine

- A protocol was design for router.
- Keepalived applied this protocol for Linux.

### States of each node.

- A node has 3 states:
  -- MASTER
  -- BACKUP
  -- FAULT

### VRRP Advertisement

- MASTER continuously send multicast packets.
