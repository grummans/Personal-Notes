### Demo Working flow

````
                   Start
                     |
                     v
              MASTER keep VIP
                     |
                     v
            Send Advertisement
                     |
          +----------+----------+
          |                     |
          v                     v
    Health Check OK      Health Check FAIL
          |                     |
          |             Down Priority
          |                     |
          +----------+----------+
                     |
          Backup compare Priority
                     |
          Priority MASTER higher?
             |               |
            Yes              No
             |               |
      Continue MASTER   Backup becomes MASTER
                              |
                              v
                    Assign VIP for Backup
                              |
                              v
                   Send Gratuitous ARP
                              |
                              v
                 Client continue access VIP
```
