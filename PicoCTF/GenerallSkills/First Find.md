#### Description

Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/500/files.zip)

### Solution
```bash
❯ unzip files.zip
Archive:  files.zip
❯ ls
 acceptable_books   adequate_books   satisfactory_books   13771.txt.utf-8   14789.txt.utf-8
❯ grep -r "pico" ./
./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt:picoCTF{f1nd_15_f457_ab443fd1}
./14789.txt.utf-8:brassa un picotin d'orge_. Comme depuis une demi-heure environ c'était
```
