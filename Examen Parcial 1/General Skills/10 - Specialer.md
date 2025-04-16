## Descripción:
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.`ssh -p 52261 ctf-player@saturn.picoctf.net`. The password is `fd7746b4`

Hints:
What programs do you have access to?

## Solución:
```
artacas-picoctf@webshell:~$ ssh -p 52261 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:52261 ([13.59.203.175]:52261)' can't be established.
ED25519 key fingerprint is SHA256:lMXKIC17ONzyUJx7ZYBY5VSwoxCz20uq5/Nm+IhXKew.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:52261' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 
Specialer$ ls
-bash: ls: command not found
Specialer$ 
Specialer$ 
!          ]]         break      command    coproc     done       esac       false      function   if         local      pushd      return     source     times      ulimit     wait       
./         alias      builtin    compgen    declare    echo       eval       fc         getopts    in         logout     pwd        select     suspend    trap       umask      while      
:          bash       caller     complete   dirs       elif       exec       fg         hash       jobs       mapfile    read       set        test       true       unalias    {          
[          bg         case       compopt    disown     else       exit       fi         help       kill       popd       readarray  shift      then       type       unset      }          
[[         bind       cd         continue   do         enable     export     for        history    let        printf     readonly   shopt      time       typeset    until      
Specialer$ 
!          ]]         break      command    coproc     done       esac       false      function   if         local      pushd      return     source     times      ulimit     wait       
./         alias      builtin    compgen    declare    echo       eval       fc         getopts    in         logout     pwd        select     suspend    trap       umask      while      
:          bash       caller     complete   dirs       elif       exec       fg         hash       jobs       mapfile    read       set        test       true       unalias    {          
[          bg         case       compopt    disown     else       exit       fi         help       kill       popd       readarray  shift      then       type       unset      }          
[[         bind       cd         continue   do         enable     export     for        history    let        printf     readonly   shopt      time       typeset    until      
Specialer$ echo *
abra ala sim
Specialer$ echo abra/*
abra/cadabra.txt abra/cadaniel.txt
Specialer$ echo ala/* 
ala/kazam.txt ala/mode.txt
Specialer$ echo sim/*
sim/city.txt sim/salabim.txt
Specialer$ echo sim/city.txt
sim/city.txt
Specialer$ for folder in abra ala sim
> do
>   cd "$folder"
>   for file in *
>   do
>     if [ -f "$file" ]; then
>       echo "$folder/$file:"
>       printf "%s\n\n" $(<"$file")
>     fi
>   done
>   cd ..
> done
abra/cadabra.txt:
Nothing

up

my

sleeve!

abra/cadaniel.txt:
Yes,

I

did

it!

I

really

did

it!

I'm

a

true

wizard!

ala/kazam.txt:
return

0

picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_38f5cc78}

ala/mode.txt:
Yummy!

Ice

cream!

sim/city.txt:
05ed181c-4aa0-4d4a-8505-2fe6ca9097d3

sim/salabim.txt:
#He

was

so

kind,

such

a

gentleman

tied

to

the

oceanside#

Specialer$ 
```

## Notas:
Le di doble Tab para ver qué comandos tenía disponibles, después con un for recorrí todos los directorios mostrando el contenido de sus archivos y la flag estaba en ala/kazam.txt

