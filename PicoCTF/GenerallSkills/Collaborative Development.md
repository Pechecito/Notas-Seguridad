### Descripcion
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/179/challenge.zip)
### Solucion
```python
┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git init
Reinitialized existing Git repository in /home/peche/picoCTF/GeneralSkilss/collaborative/drop-in/.git/

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git log
commit 5e4b2dae1868abb644627483c78a683286dfe67c (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git branch -a
  feature/part-1
  feature/part-2
  feature/part-3
* main

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git checkout feature/part-1
Switched to branch 'feature/part-1'

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git log
commit 300cff1bf1f64637dd9ff603d90176e8e8bdeb01 (HEAD -> feature/part-1)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    add part 1

commit 5e4b2dae1868abb644627483c78a683286dfe67c (main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ cat flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git log feature/part-2
commit 74989a4f650d024929388b6788d2b4c214a07e49 (feature/part-2)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    add part 2

commit 5e4b2dae1868abb644627483c78a683286dfe67c (main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git diff <commit-id> -- flag.py
-bash: commit-id: No such file or directory

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git diff 74989a4f650d024929388b6788d2b4c214a07e49 -- flag.py
diff --git a/flag.py b/flag.py
index 7ab4e25..6e17fb3 100644
--- a/flag.py
+++ b/flag.py
@@ -1,3 +1,2 @@
 print("Printing the flag...")
-
-print("m@k3s_th3_dr3@m_", end='')
\ No newline at end of file
+print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ cat flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ ls
flag.py

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git log feature/part-3
commit 12c2ae89d8035b7a5aa7cd169dc9e93cc68201be (feature/part-3)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    add part 3

commit 5e4b2dae1868abb644627483c78a683286dfe67c (main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer

┌──(peche㉿Peche)-[~/picoCTF/GeneralSkilss/collaborative/drop-in]
└─$ git diff 12c2ae89d8035b7a5aa7cd169dc9e93cc68201be -- flag.py
diff --git a/flag.py b/flag.py
index c312152..6e17fb3 100644
--- a/flag.py
+++ b/flag.py
@@ -1,3 +1,2 @@
 print("Printing the flag...")
-
-print("w0rk_798f9981}")
+print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file
```
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_798f9981}
### Tags
