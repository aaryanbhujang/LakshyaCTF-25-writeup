## 🕯️ Hall of Echoes  
**Category:** Miscellaneous  
**Points:** 100  
**Difficulty:** Medium

---

### 🧠 Challenge Description

> In the hall of echoes, eight pillars stand tall,  
> The first whispers “16” as the ancient call.  
> Next, “98” glimmers on the second in line,  
> Then “89” follows, a secret sign.  
> “15” the fourth, then “35” in the lore,  
> “75” echoes next from the old stone door.  
> The last two, “17” and “17”, complete the thrall,  
> Combine them to yield a product, a product of prime.  
>  
> High above in a celestial dance,  
> Seven stars conceal a code at a glance.  
> Begin with “62”, then “78” appears bright,  
> A “04” then “06” in the shimmering night.  
> Follow with “667”, then “94” in sight,  
> Ending with “81” – the exponent of light.  
>  
> Yet whispers linger of an unseen art—  
> A secret mirror that sets the truth apart.  
> For those who dare invert what’s on display,  
> A hidden key awaits to show the way.  
> Unlock that private cipher, subtle yet prime,  
> And inscribe its secret as your flag in time:  
>  
> `LakshyaCTF{key}`

---

### 🧩 Solution Overview

- From the first stanza (the pillars), we extract:

16 | 98 | 89 | 15 | 35 | 75 | 17 | 17 → N = 1698891535751717 (modulus)


- From the second stanza (the stars), we extract:

62 | 78 | 04 | 06 | 667 | 94 | 81 → e = 627804066679481 (public exponent)


---

### 🔍 Step-by-Step

1. **Factor the modulus:**

 Using [FactorDB](http://factordb.com), we factor:

1698891535751717 = 23285137 × 72960341


2. **Compute φ(N):**

φ(N) = (p - 1) * (q - 1) = (23285137 - 1) * (72960341 - 1)


3. **Compute the private exponent (d):**

Using Python and the `Crypto.Util.number` library:
```python
from Crypto.Util.number import inverse

p = 23285137
q = 72960341
e = 627804066679481
phi = (p - 1) * (q - 1)
d = inverse(e, phi)

print(d)
```
Output:

d = 1216997203097801

---

🛠️ Tools Used

    FactorDB

    Python + pycryptodome

    Knowledge of RSA (modulus, exponent, private key derivation)
