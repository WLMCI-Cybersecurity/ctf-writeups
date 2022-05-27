# April '22: Colours Writeup

## Problem

How many colours are there? 

gencolour.py Content: 

```python=
from Crypto.Util.number import getPrime, long_to_bytes,bytes_to_long
from random import randint

p,q,r = getPrime(100), getPrime(100), getPrime(100)

N = p * q * r
e = 65537
FLAG = "CTF{REDACTED}"
c = pow(bytes_to_long(bytes(FLAG, 'utf-8')), e, N)

print(N)
print(c)
print(e)
```

gencolouroutput.txt Content: 

```
N = 659200495002818721079012162193610119996546703710389162510182097296633808594294326043762627
c = 296622876377905304435377807367551788749706494079008208574885218125933333291933962740825901
e = 65537
```

## Solution

Notice that `N` is the product of `3` primes, which makes the problem an RSA problem.

The first thing to do is to factor `N` into its primes. As `N` is not that large, factorization should not take too long.

```
p = 700962405485427260649951056011
q = 748779714907566774490122977611
r = 1255939525083762448076194288987
```

Next, the goal becomes to find phi, which is defined as the numbers from `1` to `N` coprime to `N`. Using the principle of inclusion exclusion: 

```
phi = N - p * q - p * r - q * r + p + q + r - 1
```

Next we can find `d` to find the value of the flag.

```
d = pow(e, -1, phi)
```

Finally, we can find the flag:

```
flag = pow(c, d ,N)
```
