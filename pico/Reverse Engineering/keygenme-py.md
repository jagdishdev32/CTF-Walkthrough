# keygenme-py

## Overview

Points: 30
Category: Reverse Engineering

## Description

[keygenme-trial.py](https://mercury.picoctf.net/static/fb75b48f9214cf992a2199b5785564e7/keygenme-trial.py)

## Hints

1. (None)


## Approach

adding all variables in python console and decrypting it mannuallly

```python

import hashlib
from cryptography.fernet import Fernet
import base64

arcane_loop_trial = True
jump_into_full = False
full_version_code = ""

username_trial = "FREEMAN"
bUsername_trial = b"FREEMAN"

key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"
key_part_dynamic1_trial = "xxxxxxxx"
key_part_static2_trial = "}"
key_full_template_trial = key_part_static1_trial + key_part_dynamic1_trial + key_part_static2_trial
```
changed Check function to print key

```python
# enter picoCTF{1n_7h3_|<3y_of_xxxxxxxx} in licence

def add_to_string(strVar, pos, value):
    strVar = strVar[:pos] + str(value) + strVar[pos+1:]
    return strVar

def check_key(key, username_trial):

    global key_full_template_trial

    if len(key) != len(key_full_template_trial):
        return False
    else:
        # Check static base key part --v
        i = 0
        for c in key_part_static1_trial:
            if key[i] != c:
                return False

            i += 1

        print("Checking Working till now")
        # TODO : test performance on toolbox container
        # Check dynamic part --v

        # Getting Value in Variable
        key_full = "picoCTF{1n_7h3_|<3y_of_xxxxxxxx}"
        hash_hex = hashlib.sha256(username_trial).hexdigest()
        
        key_full = add_to_string(key_full, i, hashlib.sha256(username_trial).hexdigest()[4]); i += 1
        key_full = add_to_string(key_full, i, hashlib.sha256(username_trial).hexdigest()[5]); i += 1
        key_full = add_to_string(key_full, i, hashlib.sha256(username_trial).hexdigest()[3]); i += 1
        key_full = add_to_string(key_full, i, hashlib.sha256(username_trial).hexdigest()[6]); i += 1
        key_full = add_to_string(key_full, i, hashlib.sha256(username_trial).hexdigest()[2]); i += 1
        key_full = add_to_string(key_full, i, hashlib.sha256(username_trial).hexdigest()[7]); i += 1
        key_full = add_to_string(key_full, i, hashlib.sha256(username_trial).hexdigest()[1]); i += 1
        key_full = add_to_string(key_full, i, hashlib.sha256(username_trial).hexdigest()[8]); i += 1

        print("key_full = ", key_full)
        return False

        return True

# And it will return full which is 
# key_full = "picoCTF{1n_7h3_|<3y_of_0d208392}"

```


## Flag

picoCTF{1n_7h3_|<3y_of_0d208392}