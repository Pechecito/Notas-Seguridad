### Descripcion
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values)
### Solucion
Con factordb metemos la N, para ver si se podia factorizar.
y si, nos dio los dos numeros, por lo que ya teniamos p y q
![[Pasted image 20250522133939.png]]
A partir de aqui, y con las formulas, ya podemos realizar el decifrado de la bandera
```python
c = 843044897663847841476319711639772861390329326681532977209935413827620909782846667
n = 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
e = 65537
p = 2159947535959146091116171018558446546179
q = 658558036833541874645521278345168572231473

t = (p-1)*(q-1)

d = pow(e, -1, t)

m = pow(c,d,n)
flag = bytes.fromhex(hex(m)[2:]).decode()
print(flag)
```
### Tags
