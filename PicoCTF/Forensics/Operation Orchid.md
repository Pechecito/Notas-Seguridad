### Descripcion
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/212/disk.flag.img.gz)
### Solucion
Vemos las particiones, analizamos la ultima, analizamos el root, y ahi esta la flag, pero ahora esta encodeada, vemos el historial, y de ahi vemos como de codifico, ahora solo se hace lo inverso, para sacar la flag encodeada

```js
❯ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
❯ fls disk.flag.img -o 411648
d/d 460:	home
d/d 11:	lost+found
d/d 12:	boot
d/d 13:	etc
d/d 81:	proc
d/d 82:	dev
d/d 83:	tmp
d/d 84:	lib
d/d 87:	var
d/d 96:	usr
d/d 106:	bin
d/d 120:	sbin
d/d 466:	media
d/d 470:	mnt
d/d 471:	opt
d/d 472:	root
d/d 473:	run
d/d 475:	srv
d/d 476:	sys
d/d 2041:	swap
V/V 51001:	$OrphanFiles
❯ fls disk.flag.img -o 411648 472
r/r 1875:	.ash_history
r/r * 1876(realloc):	flag.txt
r/r 1782:	flag.txt.enc
❯ icat disk.flag.img -o 411648 1782
Salted__0��!�-6V����0�U��l��&�:�pj_1�0�|�h
                                          �Ȥ7� ���؎$�'%%                                                                                       ❯ icat disk.flag.img -o 411648 1875
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
```

Sacamos la bandera y le hecemos lo inverso
```js
❯ openssl aes256 -salt -d -in flag.txt -out flag1.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
4027C68B367F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
❯ ls
 scoped_direIpoII                                                                       󰆨 bspwm_1_0-socket
 systemd-private-27770b2669124061b15638ec9dd418c8-colord.service-JgLwJ7                  disk.flag.img
 systemd-private-27770b2669124061b15638ec9dd418c8-fwupd.service-0PluhP                   flag.txt
 systemd-private-27770b2669124061b15638ec9dd418c8-haveged.service-L3BqHb                 flag1.txt

❯ cat flag1.txt
picoCTF{h4un71ng_p457_0a710765}
```
### Tags