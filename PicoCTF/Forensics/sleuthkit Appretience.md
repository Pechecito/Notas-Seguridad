### Descripcion
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/136/disk.flag.img.gz)
### Solucion
Listamos las particiones y con el comando de fls, analizamos los archivos 
```bash
❯ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
❯ fls disk.flag.img -o 360448
d/d 451:	home
d/d 11:	lost+found
d/d 12:	boot
d/d 1985:	etc
d/d 1986:	proc
d/d 1987:	dev
d/d 1988:	tmp
d/d 1989:	lib
d/d 1990:	var
d/d 3969:	usr
d/d 3970:	bin
d/d 1991:	sbin
d/d 1992:	media
d/d 1993:	mnt
d/d 1994:	opt
d/d 1995:	root
d/d 1996:	run
d/d 1997:	srv
d/d 1998:	sys
d/d 2358:	swap
V/V 31745:	$OrphanFiles
```
Ahora hacemos un recursivo en todos los archivos -r grep flag, para ver si hay un archivito que se llame flag, y ahora le hacemos con un icat para abrir 
```js
❯ fls disk.flag.img -o 360448 -r | grep flag
++ r/r * 2082(realloc):	flag.txt
++ r/r 2371:	flag.uni.txt
```
```js
❯ icat disk.flag.img -o 360448 2371
picoCTF{by73_5urf3r_3497ae6b}
```
### Tags
