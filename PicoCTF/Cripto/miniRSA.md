### Descripcion
What happens if you have a small exponent? There is a twist though, we padded the plaintext so that (M ** e) is just barely larger than N. Let's decrypt this: [ciphertext](https://mercury.picoctf.net/static/387dc6431820338cc74324cc5cc9550f/ciphertext)
### Solucion
Descargamos la libreria gmpy2. Para hacer aritmetica con numeros muy grandes. 
Nos da una N una e y un texto cifrado
Hacemos un pequeño script 
```python
from gmpy2 import iroot 
 
N = 1615765684321463054078226051959887884233678317734892901740763321135213636796075462401>
e = 3
C = 1220012318588871886132524757898884422174534558055593713309088304910273991073554732659>


for k in range(1, 100000):
    candidate = C + k * N
    m_root, exact = iroot(candidate, e)
    if exact:
        print(f"[+] Found exact cube root with k={k}")
        print("Decrypted plaintext (as integer):", m_root)
        print("Decrypted plaintext (ASCII):", bytes.fromhex(hex(m_root)[2:]))
        break
```
Este código intenta recuperar el mensaje original `m` a partir del cifrado `C`, el módulo `N`, y `e = 3` usando una técnica llamada **Håstad’s Broadcast Attack** (en una variante más simple).
Y si eso pasa, entonces:
C = m^e mod N = m^e
(Porque no alcanza a "envolverse" con el módulo, o sea, no se hace el residuo `mod N`)
Entonces, puedes simplemente sacar la **raíz cúbica de `C`** para recuperar `m`:
m = ∛C

---

### ¿Y por qué usa un `for` con `k`?

Si `m^e > N`, entonces sí hay "envolvimiento" con el módulo y `C` ya **no es igual** a `m^e`, sino:

C = m^e mod N
⇒ m^e = C + k·N
Por eso el código prueba distintos valores de `k` (desde 1 hasta 100000) hasta encontrar un `k` tal que:
m = ∛(C + k·N)
Y que esa raíz cúbica sea **exacta**, lo que indica que encontró el mensaje original.
### Tags
