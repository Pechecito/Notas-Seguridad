#### Description

Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/474/enc_flag).

### solution
Pareceria ser una cadena en base 64 por los cartacteres y el signo igual, por lo que le hice un decode base 64, el reto tenia como nombre repetitions, por lo que lo decidi de hacer varias veces 
```bash
❯ cat enc_flag | base64 --decode | base64 --decode | base64 --decode | base64 --decode | base64 --decode | base64 --decode
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_3f81f7be}
```