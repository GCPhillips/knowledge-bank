202403121531

Tags: #reinforcementlearning 

# Explore-Then-Commit (ETC)
Algorithm for [[Multi-Armed Bandit]] that performs round-robin to average out rewards, then chooses the arm with the highest average reward.

```
let k = total arms
let m = total evaluations of each arm

for each m:
	for each k:
		total_k += val_k
get average for each total_k, return highest and keep using that arm
```

The way the value for $m$ **(for a k=2 system)** is chosen is by the [[Suboptimality Gap]].
$$
m(\triangle, n) = \max \{1, \lceil \frac{4}{\triangle^2} \ln(\frac{n\triangle^2}{4}) \rceil \}
$$

---
# References
