# Easy Peasy

## Overview

Points: 40
Category: Cryptography

## Description

A one-time pad is unbreakable, but can you manage to recover the flag? (Wrap with picoCTF{}) `nc mercury.picoctf.net 58913` [otp.py](https://mercury.picoctf.net/static/e87ba627b72932bdb57b31bbac3c22c5/otp.py)

## Hints

1. Maybe there's a way to make this a 2x pad.


## Approach

Analysing python file and found that it is unsing one time pad cipher encryption.

In file max key 50000 then key resets, So we need to send 50000 data then analyise bits for last `64*2` words (64)

creating file with letter `a*(50000-len(flag)`

```python
eflag = "51124f4d194969633e4b52026f4c07513a6f4d05516e1e50536c4954066a1c57" 
key_len = 50000
# key_len = 10

with open("a.txt", "w") as a:
	# a.write("a"*(key_len - len(eflag)))
	a.write("a"*(key_len))

print("Done")
```

after 50000th
`19040402033d1900553d1904054a3d1902503e3d1900553d1907023d1902033d1951500b113d1904593d1959502017093d1958535e3d1905503d1900003d1959`


---------------

## Correct answer

```bash
python -c "print('a'*49968);print('a'*32)" | nc mercury.picoctf.net 58913

# Output :- `03464b4f1a1c3a313d1951573d195102383d1907533d1905033d1904043d1904`
```

# Encrypted flag
ef=0x51124f4d194969633e4b52026f4c07513a6f4d05516e1e50536c4954066a1c57

# Encrypted a
ea=0x03464b4f1a1c3a313d1951573d195102383d1907533d1905033d1904043d1904

# Plaintext a in hex = 61
pa=0x6161616161616161616161616161616161616161616161616161616161616161

ef=f^k,ea=61^k,ef^ea=pa^f

# Hex flag
hf = "{:x}".format(ef^ea^pa)

# Hex to String
print(bytes.fromhex(hf).decode('utf-8'))

# Output :- `35ecb423b3b43472c35cc2f41011c6d2`
## Flag

picoCTF{35ecb423b3b43472c35cc2f41011c6d2}