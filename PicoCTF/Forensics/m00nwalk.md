### Descripcion

### Solucion
![[Pasted image 20250408124240.png]]
Buscamos sobre la pista que nos dice como enviaron las imagenes de la luna a la tierra, y nos dio el resultado de que se enviarian por SSTV

Ahora la segunda pista me decia que el nombre de la mascota de CMU que era: Scoty
Por lo que buscamos en internet SSTV Scoty para ver que se hacia, descargamos un programita que nos ayudaba de git hub y lo corrimos
```bash 
❯ sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
```
Ahora examinamos la imagen que nos da, y ahí se encuentra la flag. 

### Tags
#esteganografia
