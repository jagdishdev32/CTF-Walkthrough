# Nice netcat...

## Overview

Points: 15
Category: General Skills

## Description

There is a nice program that you can talk to by using this command in a shell: $ nc mercury.picoctf.net 22342, but it doesn't speak English...

## Hints

1. You can practice using netcat with this picoGym problem: what's a netcat?
2. You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)	


## Approach

nc server and it returns numbers and saved them into file.txt

didn't know what they were but in hint2 `let's warm up` problem was to convert hex into ascii and 
for that i used python and `0x70` which return `112` and chr(112) is `p`

so i decided to convert all nc server number into ascii char with python

```python
#!/usr/bin/python3

import sys

with open(sys.argv[1], 'r') as f:
	data = f.readlines()
	

flag = ""
for char in data:
	char = char.rstrip(" \n")
	flag += chr(int(char))

print(flag)
```

```bash
# running python script dec_to_char.py

python dec_to_char.py decimals.txt 

# Output :- picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5e51d}
```

## Flag

picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5e51d}