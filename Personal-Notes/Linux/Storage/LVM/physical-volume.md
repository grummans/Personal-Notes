### Physical Volume

- Manage by `LVM`.

E.g:

```
/dev/sdb = 500Gb
/dev/sdc = 500Gb
```

->

```
pvcreate /dev/sdb
pvcreate /dev/sdc
```

->

```
/dev/sdb
   │
   ▼
PV 500GB

/dev/sdc
   │
   ▼
PV 500GB
```
