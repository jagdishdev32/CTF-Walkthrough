# Magikarp Ground Mission

## Overview

Points: 30
Category: General Skills

## Description

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `481e7b14`

## Hints

1. Finding a cheatsheet for bash would be really helpful!


## Approach

using sftp to get download files

```bash
sftp -P {PORT} {user}@{server_address}

ls	# Listing files

get * # Downloading both files

cd /; ls 	# Chaning directory

get *.txt	# Downloading other 2 files
```

## Flag

picoCTF{xxsh_0ut_0f_\/\/4t3r_1118a9a4}