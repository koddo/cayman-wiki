---
title:  "Combinatorics"
layout: default

---


- Q: Задача Муавра --- метод точек и перегородок
см. фото с занятия
<http://www.mi-ras.ru/~podolskii/files/lecture2.pdf>


<https://www.dropbox.com/home/hse_math?preview=exam+problems+-+old.pdf>
problems from 6 to 10

- Q: How many 4-digit numbers are there which have only odd digits? What is the sum of all these numbers? Two ways of counting.
- A: <https://www.dropbox.com/s/7a5qkhxq883colt/exam%20combinatorics%20example.pdf?dl=0> --- Problem 3
<https://www.dropbox.com/home/hse_math?preview=combinatorics.pdf> --- Problem 48, see solution

The quick way is to notice every number has a pair that gives us sum like this:

```
 3795
+
 7315
-----
11110
```

For every number except $5555$ there's a pair. We have $5^3 - 1 = 624$ pairs. So the answer is $(5^3 - 1)/2 \cdot 11110 + 5555 \ = \ 5^4 \cdot 1111$

Long answer is: we have the numbers in form $1000a + 100b + 10c + d$.
Let's isolate and count sum of the values of $a$: it can be one $5^3$ times (for every value of other latters), it can be three $5^3$ number of times, etc.
The sum therefore is $1\cdot5^3 + 3\cdot5^3 + 5\cdot5^3 + 7\cdot5^3 + 9\cdot5^3 = 5^4$.
Same thing for $b,c,d$.
So the answer is $1000*5^4 + 100*5^4 + 10*5^4 + 1*5^4 = 5^4\cdot1111$.
