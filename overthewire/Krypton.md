# Krypton

## Krypton Level 0 → Level 1

Level Info

Welcome to Krypton! The first level is easy. The following string encodes the password using Base64:

S1JZUFRPTklTR1JFQVQ=

Use this password to log in to krypton.labs.overthewire.org with username krypton1 using SSH on port 2231. You can find the files for other levels in /krypton/

### Solution

```bash
echo S1JZUFRPTklTR1JFQVQ= | base64 -d
```
```
KRYPTONISGREAT
```

## Krypton Level 1 → Level 2
Level Info

The password for level 2 is in the file ‘krypton2’. It is ‘encrypted’ using a simple rotation. It is also in non-standard ciphertext format. When using alpha characters for cipher text it is normal to group the letters into 5 letter clusters, regardless of word boundaries. This helps obfuscate any patterns. This file has kept the plain text word boundaries and carried them to the cipher text. Enjoy!


first login with `ssh krypton1@krypton.labs.overthewire.org -p 2231` with password `KRYPTONISGREAT`

**For Other level `cryptool` may help**


```
# Rot13 to decrypt
YRIRY GJB CNFFJBEQ EBGGRA

# Decrypted
LEVEL TWO PASSWORD ROTTEN
```

### Password for level 1 - 2

ROTTEN

-----------

## Krypton Level 2 → Level 3
Level Info

ROT13 is a simple substitution cipher.

Substitution ciphers are a simple replacement algorithm. In this example of a substitution cipher, we will explore a ‘monoalphebetic’ cipher. Monoalphebetic means, literally, “one alphabet” and you will see why.

This level contains an old form of cipher called a ‘Caesar Cipher’. A Caesar cipher shifts the alphabet by a set number. For example:

plain:  a b c d e f g h i j k ...
cipher: G H I J K L M N O P Q ...

In this example, the letter ‘a’ in plaintext is replaced by a ‘G’ in the ciphertext so, for example, the plaintext ‘bad’ becomes ‘HGJ’ in ciphertext.

The password for level 3 is in the file krypton3. It is in 5 letter group ciphertext. It is encrypted with a Caesar Cipher. Without any further information, this cipher text may be difficult to break. You do not have direct access to the key, however you do have access to a program that will encrypt anything you wish to give it using the key. If you think logically, this is completely easy.

One shot can solve it!

Have fun.

Additional Information:

The encrypt binary will look for the keyfile in your current working directory. Therefore, it might be best to create a working direcory in /tmp and in there a link to the keyfile. As the encrypt binary runs setuid krypton3, you also need to give krypton3 access to your working directory.

Here is an example:

krypton2@melinda:~$ mktemp -d
/tmp/tmp.Wf2OnCpCDQ
krypton2@melinda:~$ cd /tmp/tmp.Wf2OnCpCDQ
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ ln -s /krypton/krypton2/keyfile.dat
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ ls
keyfile.dat
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ chmod 777 .
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ /krypton/krypton2/encrypt /etc/issue
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ ls

### Approach

first login with `ssh krypton2@krypton.labs.overthewire.org -p 2231` with password `ROTTEN`

it is using Monoalphabetic encryption i.e "one alphabet"

example: - plain:	a b c d e f g ...
		   cipher:	G H I J K L M ...


cipher in file `OMQEMDUEQMEK` 

plain : abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
cipher: MNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKL

to decrypt just need to pass cipher `ord('a') - ord('M')` to get cypher number

```python
#!/usr/local/bin/python3

cipher = "OMQEMDUEQMEK"


num = ord('M') - ord('A')

for char in cipher:
	currentNum = ord(char) - num
	if currentNum < 65:
		currentNum += 26

	correctChar = chr(currentNum)
	print(correctChar, end="")

```

### Password for level 3 - 4

CAESARISEASY

---------

## Krypton Level 3 → Level 4
Level Info

Well done. You’ve moved past an easy substitution cipher.

The main weakness of a simple substitution cipher is repeated use of a simple key. In the previous exercise you were able to introduce arbitrary plaintext to expose the key. In this example, the cipher mechanism is not available to you, the attacker.

However, you have been lucky. You have intercepted more than one message. The password to the next level is found in the file ‘krypton4’. You have also found 3 other files. (found1, found2, found3)

You know the following important details:

    The message plaintexts are in English (*** very important) - They were produced from the same key (*** even better!)

Enjoy.

### Approach

first login with `ssh krypton3@krypton.labs.overthewire.org -p 2231` with password `CAESARISEASY`

decrypted cipher from [here](https://planetcalc.com/8047/)

found key = `BOIHGKNQVTWYURXZAJEMSLDFPC`

```bash
decrypted cipher = "INCRY PTOGR APHYA CAESA RCIPH ERALS OKNOW NASAC AESAR SCIPH ERTHE SHIFT CIPHE RCAES ARSCO DEORC AESAR SHIFT ISONE OFTHE SIMPL ESTAN DMOST WIDEL YKNOW NENCR YPTIO NTECH NIQUE SITIS ATYPE OFSUB STITU TIONC IPHER INWHI CHEAC HLETT ERINT HEPLA INTEX TISRE PLACE DBYAL ETTER SOMEF IXEDN UMBER OFPOS ITION SDOWN THEAL PHABE TFORE XAMPL EWITH ASHIF TOFAW OULDB EREPL ACEDB YDBWO ULDBE COMEE ANDSO ONTHE METHO DISNA MEDAF TERJU LIUSC AESAR WHOUS EDITT OCOMM UNICA TEWIT HHISG ENERA LSTHE ENCRY PTION STEPP ERFOR MEDBY ACAES ARCIP HERIS OFTEN INCOR PORAT EDASP ARTOF MOREC OMPLE XSCHE MESSU CHAST HEVIG ENREC IPHER ANDST ILLHA SMODE RNAPP LICAT IONIN THERO TSYST EMASW ITHAL LSING LEALP HABET SUBST ITUTI ONCIP HERST HECAE SARCI PHERI SEASI LYBRO KENAN DINPR ACTIC EOFFE RSESS ENTIA LLYNO COMMU NICAT IONSE CURIT YSHAK ESPEA REPRO DUCED MOSTO FHISK NOWNW ORKBE TWEEN ANDHI SEARL YPLAY SWERE MAINL YCOME DIESA NDHIS TORIE SGENR ESHER AISED TOTHE PEAKO FSOPH ISTIC ATION ANDAR TISTR YBYTH EENDO FTHES IXTEE NTHCE NTURY NEXTH EWROT EMAIN LYTRA GEDIE SUNTI LABOU TINCL UDING HAMLE TKING LEARA NDMAC BETHC ONSID EREDS OMEOF THEFI NESTE XAMPL ESINT HEENG LISHL ANGUA GEINH ISLAS TPHAS EHEWR OTETR AGICO MEDIE SALSO KNOWN ASROM ANCES ANDCO LLABO RATED WITHO THERP LAYWR IGHTS MANYO FHISP LAYSW EREPU BLISH EDINE DITIO NSOFV ARYIN GQUAL ITYAN DACCU RACYD URING HISLI FETIM EANDI NTWOO FHISF ORMER THEAT RICAL COLLE AGUES PUBLI SHEDT HEFIR STFOL IOACO LLECT EDEDI TIONO FHISD RAMAT ICWOR KSTHA TINCL UDEDA LLBUT TWOOF THEPL AYSNO WRECO GNISE DASSH AKESP EARES

WELLD ONETH ELEVE LFOUR PASSW ORDIS BRUTE"
```

```
WELLDONETHELEVELFOURPASSWORDISBRUTE
```

### Password for Level 4 - 5

BRUTE

------------

## Krypton Level 4 → Level 5
Level Info

Good job!

You more than likely used some form of FA and some common sense to solve that one.

So far we have worked with simple substitution ciphers. They have also been ‘monoalphabetic’, meaning using a fixed key, and giving a one to one mapping of plaintext (P) to ciphertext (C). Another type of substitution cipher is referred to as ‘polyalphabetic’, where one character of P may map to many, or all, possible ciphertext characters.

An example of a polyalphabetic cipher is called a Vigenère Cipher. It works like this:

If we use the key(K) ‘GOLD’, and P = PROCEED MEETING AS AGREED, then “add” P to K, we get C. When adding, if we exceed 25, then we roll to 0 (modulo 26).

P P R O C E E D M E E T I N G A S A G R E E D\
K G O L D G O L D G O L D G O L D G O L D G O\

becomes:

P 15 17 14 2 4 4 3 12 4 4 19 8 13 6 0 18 0 6 17 4 4 3\
K 6 14 11 3 6 14 11 3 6 14 11 3 6 14 11 3 6 14 11 3 6 14\
C 21 5 25 5 10 18 14 15 10 18 4 11 19 20 11 21 6 20 2 8 10 17\

So, we get a ciphertext of:

VFZFK SOPKS ELTUL VGUCH KR

This level is a Vigenère Cipher. You have intercepted two longer, english language messages. You also have a key piece of information. You know the key length!

For this exercise, the key length is 6. The password to level five is in the usual place, encrypted with the 6 letter key.

Have fun!


### Approach

for [here](https://www.dcode.fr/vigenere-cipher) found key i.e., `FREKEY`

and password is `CLEARTEXT`

### Password for level 5 - 6

CLEARTEXT

---------

## Krypton Level 5 → Level 6
Level Info

FA can break a known key length as well. Lets try one last polyalphabetic cipher, but this time the key length is unknown.

Enjoy.

### Approach

used [this](https://www.dcode.fr/vigenere-cipher) found key i.e., `KEYLENGTH`

and password is `RANDOM`

### Password for level 6 - 7

RANDOM

-----------


## Krypton Level 6 → Level 7
Level Info

Hopefully by now its obvious that encryption using repeating keys is a bad idea. Frequency analysis can destroy repeating/fixed key substitution crypto.

A feature of good crypto is random ciphertext. A good cipher must not reveal any clues about the plaintext. Since natural language plaintext (in this case, English) contains patterns, it is left up to the encryption key or the encryption algorithm to add the ‘randomness’.

Modern ciphers are similar to older plain substitution ciphers, but improve the ‘random’ nature of the key.

An example of an older cipher using a complex, random, large key is a vigniere using a key of the same size of the plaintext. For example, imagine you and your confident have agreed on a key using the book ‘A Tale of Two Cities’ as your key, in 256 byte blocks.

The cipher works as such:

Each plaintext message is broken into 256 byte blocks. For each block of plaintext, a corresponding 256 byte block from the book is used as the key, starting from the first chapter, and progressing. No part of the book is ever re-used as key. The use of a key of the same length as the plaintext, and only using it once is called a “One Time Pad”.

Look in the krypton6 directory. You will find a file called ‘plain1’, a 256 byte block. You will also see a file ‘key1’, the first 256 bytes of ‘A Tale of Two Cities’. The file ‘cipher1’ is the cipher text of plain1. As you can see (and try) it is very difficult to break the cipher without the key knowledge.

If the encryption is truly random letters, and only used once, then it is impossible to break. A truly random “One Time Pad” key cannot be broken. Consider intercepting a ciphertext message of 1000 bytes. One could brute force for the key, but due to the random key nature, you would produce every single valid 1000 letter plaintext as well. Who is to know which is the real plaintext?!?

Choosing keys that are the same size as the plaintext is impractical. Therefore, other methods must be used to obscure ciphertext against frequency analysis in a simple substitution cipher. The impracticality of an ‘infinite’ key means that the randomness, or entropy, of the encryption is introduced via the method.

We have seen the method of ‘substitution’. Even in modern crypto, substitution is a valid technique. Another technique is ‘transposition’, or swapping of bytes.

Modern ciphers break into two types; symmetric and asymmetric.

Symmetric ciphers come in two flavours: block and stream.

Until now, we have been playing with classical ciphers, approximating ‘block’ ciphers. A block cipher is done in fixed size blocks (suprise!). For example, in the previous paragraphs we discussed breaking text and keys into 256 byte blocks, and working on those blocks. Block ciphers use a fixed key to perform substituion and transposition ciphers on each block discretely.

Its time to employ a stream cipher. A stream cipher attempts to create an on-the-fly ‘random’ keystream to encrypt the incoming plaintext one byte at a time. Typically, the ‘random’ key byte is xor’d with the plaintext to produce the ciphertext. If the random keystream can be replicated at the recieving end, then a further xor will produce the plaintext once again.

From this example forward, we will be working with bytes, not ASCII text, so a hex editor/dumper like hexdump is a necessity. Now is the right time to start to learn to use tools like cryptool.

In this example, the keyfile is in your directory, however it is not readable by you. The binary ‘encrypt6’ is also available. It will read the keyfile and encrypt any message you desire, using the key AND a ‘random’ number. You get to perform a ‘known ciphertext’ attack by introducing plaintext of your choice. The challenge here is not simple, but the ‘random’ number generator is weak.

As stated, it is now that we suggest you begin to use public tools, like cryptool, to help in your analysis. You will most likely need a hint to get going. See ‘HINT1’ if you need a kicktstart.

If you have further difficulty, there is a hint in ‘HINT2’.

The password for level 7 (krypton7) is encrypted with ‘encrypt6’.

Good Luck!

### Approach

```
PNUKLYLWRQKGKBE
```

tried to cipher 15 `A` with algoritham

```
plain:	AAAAAAAAAAAAAAA

cipher:	EICTDGYIYZKTHNS

plain:	BBBBBBBBBBBBBBB

cipher:	FJDUEHZJZALUIOTJ
```

from the result we can say that it is using cipher with key

decrypting with python

```python3
#!/usr/local/bin/python3

encrypted_A = "EICTDGYIYZKTHNS"
encrypted_password = "PNUKLYLWRQKGKBE"

for i in range(len(encrypted_password)):
	num_diff = ord(encrypted_A[i]) - ord('A')

	num_after_diff = ord(encrypted_password[i]) - num_diff

	if num_after_diff < 65:
		num_after_diff += 26

	print(chr(num_after_diff), end="")
```

### Password for level 7

LFSRISNOTRANDOM

-----------

# CTF Completed

################################################
