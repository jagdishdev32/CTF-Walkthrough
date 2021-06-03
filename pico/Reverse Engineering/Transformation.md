# Transformation

## Overview

Points: 20
Category: Reverse Engineering

## Description

I wonder what this really is... [enc](https://mercury.picoctf.net/static/e47483f88b12f2ab0c46315afc12f64d/enc) ''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])

## Hints

1. You may find some decoders online


## Approach

Downloaded the file i was in chinese. Tryed to code it translator found nothing.

then I created a python script to reverse encryption method

```python
#!/usr/bin/python3

import sys

file = sys.argv[1]

with open(file, 'r') as f:
	data = f.read()

## Method 1 (Analysing)
### Encrption Method
# ''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])
# chr((ord(demo[0]) << 8) + ord(flag[i+1])) 

# Check with demo string
# flag="hello_sir_ji"
# ''.join([str(i) + " " + flag[i]+" "+ str(i+1)+ " " + flag[i + 1] + " - " for i in range(0, len(flag), 2)])
# Result = '0 h 1 e - 2 l 3 l - 4 o 5 _ - 6 s 7 i - 8 r 9 _ - 10 j 11 i - '

## String is even number

## Method 2 (Idea's) :- 
#	brutforce all the combination of ascii character with next letter stored in dictionary
#	After the result search for word values in dict get dict[flag[i]]
#	dict storing method :- `dict[encrypted letter] = [ char a, char b ]`

dict1 = {}
for i in range(128):
	for j in range(128):
		letter = [chr(i), chr(j)]
		encrypted = chr((ord(letter[0]) << 8) + ord(letter[1]))
		dict1[encrypted] = letter

decrypted = ""
for echar in data:
	#print(dict1[echar])
	decrypted += "".join(dict1[echar])

print(data)
print(decrypted)

```

```bash
# To run file
python reverse.py enc

# Output :- 灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥ㄴㅡて㝽 picoCTF{16_bits_inst34d_of_8_e141a0f7} 
```

## Flag

picoCTF{16_bits_inst34d_of_8_e141a0f7} 