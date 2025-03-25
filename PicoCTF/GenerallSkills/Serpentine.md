### Description
Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/37/serpentine.py)

### Solución 
Modifique el codigo para hacerlo entrar a la funcion
```python
❯ python3 fixme2.py
  68   │     elif choice == 'b':
  69   │       #print('\nOops! I must have misplaced the print_flag function! Check my source code!\n\n')
  70   │       print_flag()



What would you like to do? (a/b/c) b
picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}
```
