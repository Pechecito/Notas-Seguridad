### Description
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

### Solución 
Modifique el script para que probara con todas las posibles contraseñas
```python
def level_3_pw_check(passwd):
  27   │     user_pw = passwd
  28   │     user_pw_hash = hash_pw(user_pw)
  29   │     
  30   │     if( user_pw_hash == correct_pw_hash ):
  31   │         print("Welcome back... your flag, user:")
  32   │         decryption = str_xor(flag_enc.decode(), user_pw)
  33   │         print(decryption)
  34   │         return
  35   │     print("That password is incorrect")
  36   │ 
  37   │ 
  38   │ 
  39   │ #level_3_pw_check()
  40   │ 
  41   │ 
  42   │ # The strings below are 7 possibilities for the correct password. 
  43   │ #   (Only 1 is correct)
  44   │ pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]
  45   │ for paswordPrueba in pos_pw_list:
  46   │     level_3_pw_check(paswordPrueba)



❯ python3 level3.py
That password is incorrect
That password is incorrect
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
That password is incorrect
That password is incorrect
That password is incorrect
That password is incorrect

```
