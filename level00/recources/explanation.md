Connection
```bash
ssh level00@10.0.2.2 -p 4242
```

Search for *flag00* files
```bash
find / -user flag00 2>/dev/null
```

found -> `/usr/sbin/john`

```bash
cat /usr/sbin/john
```

encoded string `cdiiddwpgswtgt`

use https://www.cachesleuth.com/multidecoder/ to decode 

**Rot 15** -> `nottoohardhere`

```bash
su flag00 / nottoohardhere
```
