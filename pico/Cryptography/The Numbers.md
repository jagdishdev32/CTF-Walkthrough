# The Numbers

## Overview

Points: 50
Category: Cryptography

## Description

The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Hints

1. The flag is in the format PICOCTF{}


## Approach

downloaded image and run strings on it.

open image as normal image file

```
16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }
```

```python
#!/usr/bin/python

# converting numbers into strings
LETTERS = "16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }"
LETTERS = LETTERS.split()

flags = []
for LETTER in LETTERS:
	if LETTER == "{" or LETTER == "}" :
		flags.append(LETTER)
	else:
		flags.append(chr(int(LETTER) + 64))

print("".join(flags))
```

## Flag

PICOCTF{THENUMBERSMASON}