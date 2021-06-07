# Leviathan

Leviathan’s levels are called leviathan0, leviathan1, … etc. and can be accessed on leviathan.labs.overthewire.org through SSH on port 2223.

To login to the first level use:

Username: leviathan0
Password: leviathan0

Data for the levels can be found in the homedirectories. You can look at /etc/leviathan_pass for the various level passwords.

## Leviathan Level 0 → Level 1

There is no information for this level, intentionally.

### Approach

login `ssh leviathan0@leviathan.labs.overthewire.org -p 2223`

Checked for files in home directory and check `.backup folder`

`bookmarks.html` file in backup folder and searched for password

```bash
<DT><A HREF="http://leviathan.labs.overthewire.org/Ipasswordus.html | This will be fixed later, the password fo     r leviathan1 is rioGegei8m" ADD_DATE="1155384634" LAST_CHARSET="ISO-8859-1" ID="rdf:#$2wIU71">password to levia     than1</A>
```

### Password for Level 0 - 1 

rioGegei8m

-----------

## Leviathan Level 1 → Level 2

There is no information for this level, intentionally.

### Approach

login `ssh leviathan1@leviathan.labs.overthewire.org -p 2223` password `rioGegei8m`

tryied `strings` file for password nothing useful found
then tryied `strace` and `ltrace` and ltrace return password value

```bash
leviathan1@leviathan:~$ ltrace ./check 
__libc_start_main(0x804853b, 1, 0xffffd764, 0x8048610 <unfinished ...>
printf("password: ")                                                   = 10
getchar(1, 0, 0x65766f6c, 0x646f6700password: 0x65766f6c
)                                  = 48
getchar(1, 0, 0x65766f6c, 0x646f6700)                                  = 120
getchar(1, 0, 0x65766f6c, 0x646f6700)                                  = 54
strcmp("0x6", "sex")                                                   = -1
puts("Wrong password, Good Bye ..."Wrong password, Good Bye ...
)                                   = 29
+++ exited (status 0) +++
leviathan1@leviathan:~$ ./check 
password: sex
$ ls
```

```bash
cat /etc/leviathan_pass/leviathan2
ougahZi8Ta
```

### Password for Level 2 - 2 

ougahZi8Ta

-----------

## Leviathan Level 2 → Level 3

There is no information for this level, intentionally.

### Approach

login `ssh leviathan2@leviathan.labs.overthewire.org -p 2223` password `ougahZi8Ta`

checked file with strings , strace , ltrace

It is reading file using /bin/cat and for `/etc/leviathan_pass/leviathan3` showing error which can be exploited by creating symbolic link of `/etc/leviathan_pass/leviathan3` name b and create file "a b" and file "a"

which will run file "a b" as "a" as a file and "b" as symbolic link

### Password for Level 3 - 4

Ahdiemoo1j

-------------

## Leviathan Level 3 → Level 4

There is no information for this level, intentionally.

### Approach 

login `ssh leviathan3@leviathan.labs.overthewire.org -p 2223` password `Ahdiemoo1j`

just `strace` and `ltrace` file and found comparing string with ltrace

```bash
leviathan3@leviathan:~$ ltrace ./level3 
__libc_start_main(0x8048618, 1, 0xffffd784, 0x80486d0 <unfinished ...>
strcmp("h0no33", "kakaka")                                             = -1
printf("Enter the password> ")                                         = 20
fgets(Enter the password> kakaka
"kakaka\n", 256, 0xf7fc55a0)                                     = 0xffffd590
strcmp("kakaka\n", "snlprintf\n")                                      = -1
puts("bzzzzzzzzap. WRONG"bzzzzzzzzap. WRONG
)                                             = 19
+++ exited (status 0) +++
leviathan3@leviathan:~$ ltrace ./level3 
__libc_start_main(0x8048618, 1, 0xffffd784, 0x80486d0 <unfinished ...>
strcmp("h0no33", "kakaka")                                             = -1
printf("Enter the password> ")                                         = 20
fgets(Enter the password> snlprintf
"snlprintf\n", 256, 0xf7fc55a0)                                  = 0xffffd590
strcmp("snlprintf\n", "snlprintf\n")                                   = 0
puts("[You've got shell]!"[You've got shell]!
```

### Password for Level 4 - 5

vuH0coox6m

------------

## Leviathan Level 4 → Level 5

There is no information for this level, intentionally.

### Approach

login with `ssh leviathan4@leviathan.labs.overthewire.org -p 2223` , password `vuH0coox6m`

strings `~/.trash/bin` and found it is getting leviathan5 password file

by executing `bin` file, it returns binary

```binary
01010100 01101001 01110100 01101000 00110100 01100011 01101111 01101011 01100101 01101001 00001010
```

[Using this converted binary into strings](https://codebeautify.org/binary-string-converter)

###  Password for Level 5 - 6

Tith4cokei

------------

## Leviathan Level 5 → Level 6

There is no information for this level, intentionally.

### Approach

login with `ssh leviathan5@leviathan.labs.overthewire.org -p 2223` and password `Tith4cokei`

Executable file is reading file.log

so we can create symbolic link of password file as file.log

### Password for Level 6 - 7

UgaoFee4li

-----------

## Leviathan Level 6 → Level 7

There is no information for this level, intentionally.

### Approach

login with `ssh leviathan5@leviathan.labs.overthewire.org -p 2223` and password `UgaoFee4li`

just bruteforce file

```bash
for i in $(seq 0000 9999); do ./leviathan6 $i; done	# File will stop at correct number that why getting all number
```

### Password for Level 7 - 8

ahy7MaeBo9

-------------

**Completed**