# Wave a flag

## Overview

Points: 10
Category: General Skills

## Description

Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm) has extraordinarily helpful information...

## Hints

1. This program will only work in the webshell or another Linux computer.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: $ wget https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
3. Run this program by entering the following in the Terminal prompt: $ ./warm, but you'll first have to make it executable with $ chmod +x warm
4. -h and --help are the most common arguments to give to programs to get more information from them!
5. Not every program implements help features like -h and --help.


## Approach

first check file type with `file` command and find out it was excutable file. 

```bash
file warm	# To check File type 

# Output :- warm: ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=b11c22752c901adc13ba1ce86eda9d5516f22763, with debug_info, not stripped
```

So changed file permissions and excute it

```bash
chmod u+x warm	# Chaning file permission

./warm	# Running file

# Output :- Hello user! Pass me a -h to learn what I can do!

./warm -h 	# Using -h as it says

# Output :- Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_d6969390}

```


## Flag

picoCTF{b1scu1ts_4nd_gr4vy_d6969390}