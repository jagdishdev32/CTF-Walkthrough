# Obedient Cat

## Overview

Points: 5
Category: General Skills

## Description

This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag).

## Hints

1. Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: $ wget https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
3. $ man cat

## Approach

just used `cat` to get the data 

```bash
cat flag
```

## Flag

picoCTF{the_m3tadata_1s_modified}