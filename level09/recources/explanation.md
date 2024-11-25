The **token** file is the result of transforming the original token processed by the binary level09.

The binary **level09** performs the following steps for each character in the string:

For eatch character ->
character's position in the string  + its hexadecimal value

To reverse the transformation, we can extract the hexadecimal values from the token.

```bash
hexdump token
-> 
0000000 3466 6d6b 366d 7c70 823d 707f 6e82 8283
0000010 4244 4483 7b75 8c7f 0a89               
000001a
```

and reverse the process using a python script.

Solver:
```python
s = "\x66\x34\x6b\x6d\x6d\x36\x70\x7c\x3d\x82\x7f\x70\x82\x6e\x83\x82\x44\x42\x83\x44\x75\x7b\x7f\x8c\x89"
r = ""
for (i, l) in enumerate(s):
    #print("i " ,ord(l) - i)
    r = r + chr(ord(l) - i)

print(r)
```

Result -> `f3iji1ju5yuevaus41q1afiuq`

```bash
su flag09 / f3iji1ju5yuevaus41q1afiuq
```





