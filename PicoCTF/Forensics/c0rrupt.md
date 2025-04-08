### Descripcion
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.
### Solucion
Le hicimos un xxd | head al archivo, para ver sus primeros bits, por que al parecer estaban dañados, parecia ser un png, ya que tenia algunos bits iguales a los png, por lo que remplazamos los que creiamos que no eran.
con hexeditor, fuimos cambiando, despues de eso, tuvimos que con pngcheck, ir verificando a ver que chunk estaba mal, hasta llegar a poderlo abrir, a continuacion voy poniendo los errores que fuimos corrigiendo
```bash 
❯ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  invalid chunk name "C"DR" (43 22 44 52)
ERRORS DETECTED in mystery
```
```bash
❯ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery
```
```bash
❯ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
```
```bash
❯ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)
0002f080: 4432 a766 c35b 2dff b4f5 7e47 3b8f 0591  D2.f.[-...~File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).
```
![[Pasted image 20250408155942.png]]
### Tags
#hexeditor #chunks #png #file-corruptions
