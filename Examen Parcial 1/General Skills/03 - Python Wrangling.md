## Descripción:
Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py) using [this password](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/pw.txt) to get [the flag](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/flag.txt.en)?

Hints:
- Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py`
- $ man python

## Solución:
```
artacas-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py
--2025-04-15 18:56:32--  https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1328 (1.3K) [application/octet-stream]
Saving to: 'ende.py'

ende.py                                                   100%[==================================================================================================================================>]   1.30K  --.-KB/s    in 0s      

2025-04-15 18:56:32 (816 MB/s) - 'ende.py' saved [1328/1328]

artacas-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/pw.txt
--2025-04-15 18:56:42--  https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/pw.txt
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: 'pw.txt'

pw.txt                                                    100%[==================================================================================================================================>]      33  --.-KB/s    in 0s      

2025-04-15 18:56:42 (14.3 MB/s) - 'pw.txt' saved [33/33]

artacas-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/flag.txt.en
--2025-04-15 18:56:53--  https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/flag.txt.en
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: 'flag.txt.en'

flag.txt.en                                               100%[==================================================================================================================================>]     140  --.-KB/s    in 0s      

2025-04-15 18:56:53 (51.4 MB/s) - 'flag.txt.en' saved [140/140]

artacas-picoctf@webshell:~$ cat pw.txt
aa821c16aa821c16aa821c16aa821c16
artacas-picoctf@webshell:~$ python3 ende.py -d flag.txt.en
Please enter the password:aa821c16aa821c16aa821c16aa821c16
picoCTF{4p0110_1n_7h3_h0us3_aa821c16}
```
