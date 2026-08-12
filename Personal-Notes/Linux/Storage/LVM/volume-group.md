### Volume Group

- Simple understand **Storage Pool**

E.g:

```
PV1 = 500Gb
PV2 = 500Gb
```

->

```
vgcreate vg_data /dev/sdb /dev/sdc
```

->

```
/dev/sdb       /dev/sdc
 500GB          500GB
   │              │
   └──────┬───────┘
          ▼
     vg_data
      1000GB
```
