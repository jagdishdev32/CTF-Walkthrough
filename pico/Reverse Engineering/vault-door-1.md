# vault-door-1

## Overview

Points: 100
Category: Reverse Engineering

## Description

This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c081ae/VaultDoor1.java)

## Hints

1. Look up the charAt() method online.


## Approach

created python file to get result

```python
lst = ['' for _ in range(50)]

lst[0] = 'd'
lst[29] = '9'
lst[4] = 'r'
lst[2] = '5'
lst[23] = 'r'
lst[3] = 'c'
lst[17] = '4'
lst[1] = '3'
lst[7] = 'b'
lst[10] = '_'
lst[5] = '4'
lst[9] = '3'
lst[11] = 't'
lst[15] = 'c'
lst[8] = 'l'
lst[12] = 'H'
lst[20] = 'c'
lst[14] = '_'
lst[6] = 'm'
lst[24] = '5'
lst[18] = 'r'
lst[13] = '3'
lst[19] = '4'
lst[21] = 'T'
lst[16] = 'H'
lst[27] = '5'
lst[30] = '2'
lst[25] = '_'
lst[22] = '3'
lst[28] = '0'
lst[26] = '7'
lst[31] = 'e'

flag = "".join(lst)

print("picoCTF{" + "".join(flag) + "}")
```

## Flag

picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}