# Wireshark doo dooo do doo...

## Overview

Points: 50
Category: Forensics

## Description

Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/0505a462ac9beb7412596855df280f6b/shark1.pcapng).

## Hints

1. (None)


## Approach

Downloaded packet file and checking it in wireshark

---------

### wrong aproach

Downloading and scapy for packet analysis

```bash
pip install scapy	# Installing scapy
```

```python
#!/usr/bin/python

from scapy.all import *

packet_file = 'shark1.pcapng'

packets = rdpcap(packet_file)

print(packets[100].show())

```

----------

### Correct approach

Open file with wireshark select packet and **follow packet Tcp stream** and Increase Stream and there you will found stream data

cvpbPGS{c33xno00_1_f33_h_qrnqorrs}

which is encrypted in rot13

```bash
echo cvpbPGS{c33xno00_1_f33_h_qrnqorrs} | rot13
```

## Flag

picoCTF{p33kab00_1_s33_u_deadbeef}