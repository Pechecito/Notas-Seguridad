### Description

Our flag printing service has started glitching!`$ nc saturn.picoctf.net 62142`

## Hints

1. ASCII is one of the most common encodings used in programming.
2. We know that the glitch output is valid Python, somehow!
3. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solution
```bash
PecheZ-picoctf@webshell:~/retos$ python 
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}')
picoCTF{gl17ch_m3_n07_bda68f75}
```