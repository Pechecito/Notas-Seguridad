### Description
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/26/fixme1.py)

### Solución 
SIgno de comparacion debe ser doble == solo tenia 1 
```python
❯ python3 fixme2.py
  File "/home/peche/picoctf/generalSkills/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
❯ nvim fixme2.py
❯ python3 fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
```
