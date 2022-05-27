# May '22 British Fever Writeup

## Problem

Oh NO! WHAT ARE THOSE -> [({})] !!! WE CALL THEM BRACKETS, BUT WHAT DO THE BRITS SEY??? (Note to warp the flag in CTF{} and ensure alphabetical characters are all upper-case). You may find [this](https://en.wikipedia.org/wiki/Rail_fence_cipher) useful.

File Content: ```q}wq #cs%bs# cd!}$}c z%pb`prd b#dt```

## Solution

Use the Rail Fence Cipher

```
q       }       w       q
 #     c s     % b     s #
  c   d   !   }   $   }   c
   z %     p b     ` p     r d
    b       #       d       t
```

```
q#czb%dc}s!p#b}%wb$`dp}sq#crtd
```

Then use a ROT47 to find the answer: 

```
BR4K3T54NDPAR3NTH3S15ANDBR4CE5
```

