202310092111

Tags: #nlp 

# Nucleus Sampling
A method where the top probabilities are used after a cutoff instead of using all possible next words.  This helps avoid the problem with [[Beam Search]] of degeneration, looping, and unlikely sequences being generated.

If the highest probability is greater than $p\%$ then it will be chosen.

After selecting the words, a normalization process is performed.

##### Example

Assume the words with their probabilities:
```
the      0.7
a        0.1
computer 0.1
tablet   0.08
phone    0.01
server   0.01
```

If $p\%=0.95$ , the first four words would be possibilities, but the last will be dropped:

$$
The\:+\:a\:+\:computer\:+\:tablet
$$
$$
= .7 + .1 + .1 + 0.08 = 0.98
$$
$0.98 > 0.95$, so the words "phone" and "server" are dropped.
Normalization is then performed:
$$
The = \frac{0.7}{0.98},
$$
$$
a = \frac{0.1}{0.98},
$$
$$
computer = \frac{0.1}{0.98},
$$
$$
tablet = \frac{0.08}{0.98}
$$

---
# References
https://www.youtube.com/watch?v=JETxaSaj6_k