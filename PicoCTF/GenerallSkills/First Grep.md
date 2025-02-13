### Description
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.

### Hints
Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

### Solución 
```
PecheZ-picoctf@webshell:~/retos$ cat file | grep "pico"
picoCTF{grep_is_good_to_find_things_5af9d829}
```