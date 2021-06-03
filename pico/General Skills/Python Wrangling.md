# Python Wrangling

## Overview

Points: 10
Category: General Skills

## Description

Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/ende.py) using [this password](https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/pw.txt) to get [the flag](https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/flag.txt.en)?

## Hints

1. Get the Python script accessible in your shell by entering the following command in the Terminal prompt: $ wget https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/ende.py
2. $ man python

## Approach

Downloaded all the file. analyis python script and found out that it uses -e to encrypt file and -d to decrypt. So command used:-

```bash
# Changing Permissions
chmod u+x ende.py

python ende.py -d flag.txt.en
# Please enter the password:6008014f6008014f6008014f6008014f
```

## Flag

picoCTF{4p0110_1n_7h3_h0us3_6008014f}