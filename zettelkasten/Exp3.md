202404071110

Tags: #onlinelearning

# Exp3
An algorithm for [[Adversarial Setting]].

<u>Exp</u>onential weight algorithm for <u>Exp</u>lore and <u>Exp</u>loit.

### Exponential Weighting:
Exponential values of loss can be used to determine the probability of choosing an arm.  For example:
Suppose the loss for arm1 = 3, arm2 = 10.  The negative of these can be used to maximize the choice of lowest loss:
$$
\frac{e^{-\eta 3}}{e^{-\eta 3} + e^{-\eta 10}} > \frac{e^{-\eta 10}}{e^{-\eta 3} + e^{-\eta 10}}
$$
which means, the probability of choosing arm1 is greater based on observed loss.  The left hand side is closer to 1, the right hand side is closer to 0.

The same can be used for reward rather than loss.  For example:
Suppose the reward for arm1 = 3, arm2 = 15.  Then:

$$
\frac{e^{\eta 3}}{e^{\eta 3} + e^{\eta 15}} < \frac{e^{\eta 15}}{e^{\eta 3} + e^{\eta 15}}
$$

### Issue with Exponential Weighting:
Exponential Weighting can be used to develop a [[Probability Distribution]] over the arms based on historical knowledge, which can be sampled from to choose the next arm.  The problem is you do not have full feedback of all possible losses/rewards, just the reward/loss based on the arm you chose.

##### Solution:
Develop estimations for arms that were not chosen.

[[Importance Sampling Estimators]] for $\{x_{tj}, y_{tj}\}$:
Let:
$I_{t-1} = (A_1, X_1, A_2, X_2, \dots, A_{t-1}, X_{t-1})$

The **Player** chooses:
$P_{tj} = P(A_t = j | I_{t-1})$

The [[Estimator]]s are:
$\hat{x}_{tj} = \frac{\chi_{\{A_t = j\}} \cdot X_t}{P_{tj}}$
($\chi_{\{A_t = j\}}$ is the indicator function; 1 for if $j$ was chosen at time $t$, 0 otherwise. )
meaning, there is makeup for the times that the arm was not chosen by "amplifying" it by dividing by the probability.

### Estimation Equivalency:
The estimated value of the reward is equivalent to the expected reward:

$$
\begin{flalign}
\mathbb{E}\left[\hat{x}_{tj} | I_{t-1}\right] &= \mathbb{E}\left[\frac{\chi_{\{A_t = j\}}X_t}{P_{tj}} | I_{t-1}\right] \\
&= \frac{1}{P_{tj}} \mathbb{E}\left[\chi_{\{A_t = j\}} | I_{t-1}\right] x_{tj} \\
&= \frac{1}{P_{tj}} P_{tj} \cdot x_{tj} \\
&= x_{tj}
\end{flalign}
$$
The problem with this is it is a high [[Variance]] estimator.

### Algorithm:
Assume losses are being observed (not rewards):

Let the cumulative loss $\hat{L}_{tj} = \sum_{s=1}^t \hat{y}_{sj}$
$\hat{L}_{0, j} = 0$
$\hat{y}_{sj} = \frac{\chi_{\{A_s = j\}Y_s}}{P_{sj}}$

input: $\eta > 0$

For each time $t=1, 2, \dots, n$:
$$
P_{tj} = \left(\frac{e^{-\eta \hat{L}_{t-1}, j}}{\sum_{\gamma = 1}^k e^{-\eta \hat{L}_{t-1}, \gamma}}\right)
$$
- draw a sample $A_t \sim P_{tj}$
- Update $\hat{L}_{t,j} = \hat{L}_{t-1, j} + \hat{y}_{t,j}$

For setting $\eta$:
$\eta = \sqrt{\frac{\ln{k}}{nk}}$


---
# References
