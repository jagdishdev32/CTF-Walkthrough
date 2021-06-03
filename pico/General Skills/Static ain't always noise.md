# Template

## Overview

Points: 20
Category: General Skills

## Description

Can you look at the data in this binary: [script](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static)? This [BASH script](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh)  might help!

## Hints

1. (None)


## Approach

Download files. opened both files.

static file is in binary and have some strings 

Simplly used 
```bash
strings static	# It returns flag
```

## Flag

picoCTF{d15a5m_t34s3r_98d35619}