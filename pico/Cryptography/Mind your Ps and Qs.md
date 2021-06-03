# Mind your Ps and Qs

## Overview

Points: 20
Category: Cryptography

## Description

In RSA, a small e value can be problematic, but what about N? Can you decrypt this? [values](https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values)

## Hints

1. Bits are expensive, I used only a little bit over 100 to save money


## Approach

Searched about RSA n c e decrpt and found out  [RsaCTFTool](https://github.com/Ganapati/RsaCtfTool) to decrypt code

```bash
python RsaCtfTool.py -n 1422450808944701344261903748621562998784243662042303391362692043823716783771691667 -e 65537 --uncipher 843044897663847841476319711639772861390329326681532977209935413827620909782846667
```

## Flag

picoCTF{sma11_N_n0_g0od_00264570}