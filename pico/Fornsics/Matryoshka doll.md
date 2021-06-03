# Matryoshka doll

## Overview

Points: 30
Category: Forensics

## Description

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg)

## Hints

1. Wait, you can hide files inside files? But how do you find them?
2. Make sure to submit the flag as picoCTF{XXXXX}


## Approach

Downloaded photo

As per the name suggest Files inside Files

Open photo in online forensic lab and local gimp for layer checking

Found Strings base_images/2_c.jpgUT and after searching about it got to know

```bash
exiftool {image}	# For forensic Image

# Output includes :- Warning	: [minor] Trailer data after PNG IEND chunk
# Which means their is image inside image

unzip {image.png/.jpg}	# To unzip image
```

## Flag

picoCTF{96fac089316e094d41ea046900197662}