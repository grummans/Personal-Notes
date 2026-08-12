### RAID 0

```
Disk1

Disk2
```

```
AAAA BBBB CCCC DDDD
```

->

```
Disk 1

AAAA
CCCC

Disk 2

BBBB
DDDD
```

-> Read 2 disk simutaneously.

Pros:

- Fastest
- Utillize 100% storage capacity.

Cons:

- 1 disk broken -> system broken -> No redundancy.

-> Use for: Cache, Temporary Data, ...
