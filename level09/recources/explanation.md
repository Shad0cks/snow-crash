le token est le resutat de la transformation du token original mit dans le binary level09

Le binaire level09 vas:

pour chaque char dans la string:
        -> position du char dans la string + HEX du char

Pour reverse la transformation nous pouvons recuperer les valeurs hexadecimal du token 

```bash
hexdump token
-> 
0000000 3466 6d6b 366d 7c70 823d 707f 6e82 8283
0000010 4244 4483 7b75 8c7f 0a89               
000001a
```

et renverser le processus dans un script python.

Solver:
```python
s = "\x66\x34\x6b\x6d\x6d\x36\x70\x7c\x3d\x82\x7f\x70\x82\x6e\x83\x82\x44\x42\x83\x44\x75\x7b\x7f\x8c\x89"
r = ""
for (i, l) in enumerate(s):
    #print("i " ,ord(l) - i)
    r = r + chr(ord(l) - i)

print(r)
```

Resultat -> `f3iji1ju5yuevaus41q1afiuq`

```bash
su flag09 / f3iji1ju5yuevaus41q1afiuq
```





