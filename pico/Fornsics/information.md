# information

## Overview

Points: 10
Category: Forensics

## Description

Files can always be changed in a secret way. Can you find the flag? [cat.jpg](./cat.jpg)

## Hints

1. Look at the details of the file
2. Make sure to submit the flag as picoCTF{XXXXX}

## Approach

Downloaded the file. tryied to check metadata of file with imageMagick but found nothing 
then checked file with file type, found nothing 

used nano to check the file but nothing found nothing usefull but what i dont know was thier was something useful

then to search hint about this problem i found [this](https://github.com/vivian-dai/PicoCTF2021-Writeup/blob/main/Forensics/information/information.md) which tells that strign with license could be base64 string

At the end it was base64 and found flag

```xml
JFIF
0Photoshop 3.0
8BIM
PicoCTF
http://ns.adobe.com/xap/1.0/
<?xpacket begin='
' id='W5M0MpCehiHzreSzNTczkc9d'?>
<x:xmpmeta xmlns:x='adobe:ns:meta/' x:xmptk='Image::ExifTool 10.80'>
<rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#'>
 <rdf:Description rdf:about=''
  xmlns:cc='http://creativecommons.org/ns#'>
  <cc:license rdf:resource='cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9'/>
 </rdf:Description>
 <rdf:Description rdf:about=''
  xmlns:dc='http://purl.org/dc/elements/1.1/'>
  <dc:rights>
   <rdf:Alt>
    <rdf:li xml:lang='x-default'>PicoCTF</rdf:li>
   </rdf:Alt>
  </dc:rights>
 </rdf:Description>
</rdf:RDF>
</x:xmpmeta>
```

```bash
# Command used to decrypt base64

base64 -d cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
```

## Flag

picoCTF{the_m3tadata_1s_modified}
