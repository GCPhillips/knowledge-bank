202404070916

Tags: #onlinelearning

# Adversarial Setting

**Adversary** chooses arm rewards
**Player** chooses arm to play

## Explanation:
**Adversary** has information about the players actions and rewards up to time $t$ as well as the first stage of the player's [[Policy]] (i.e. what is the probability distribution with respect to the way the player chooses the arms),
**Player** has information about each action and reward.


At each time $t = 1, 2, \dots, n$:
#### 1.) Adversary
**Adversary** chooses [[Reward]] for each arm $j$:
$$
x_{tj} \in [0,1], j=1, 2, \dots, n
$$
There are no assumptions on how they are chosen; it is an arbitrary reward.
Equivalently, a loss for each arm $j$:
$$
\begin{flalign}
y_{tj} &\in [0,1], j=1, 2, \dots, n \\
y_{tj} &= (1 - x_{tj})
\end{flalign}
$$
This equivalency works because we are bounded $[0,1]$

#### 2.) Player
**Player** chooses [[Action]] $A_t \in {1, 2, \dots, k}$
Action is chosen in a two-step process:
###### a.)
A policy $\pi = (\pi_1, \pi_2, \dots, \pi_n)$  is fixed before start of play (each $\pi_i$ is the $i^{th}$ time step), where:
$$
\begin{flalign}
\pi_t : (A_1, x_1, A_2, x_2, \dots, A_{t-1}, x_{t-1}) \rightarrow P_t \\
\text{(i.e. At each time step $t$, the entire history of actions and rewards is viewed)}
\end{flalign}
$$

where $P_t$ is a [[Probability Distribution]] over ${1, 2, \dots, k}$,
$\mathcal{P}_{k-1}$ is a [[Probability Simplex]] over k dimensions, and
$P_t \in \mathcal{P}_{k-1}$

###### b.)
After this probability distribution over arms is chosen, a sample is drawn from this probability distribution.
The **Player** has access to random bits not known by the **Adversary**.  The player uses these bits to select an action based on the policy $P_t = (P_{t1}, P_{t2}, \dots, P_{tk})$, i.e.:
$P(A_t = j | A_1, x_1, \dots, A_{t-1}, x_{t-1}) = P_{tj}$ and 
$P_t \in \mathbb{R}^k$ (a k-sized [[vector]])

i.e., the player will choose the arm that it drew from the distribution.

#### 3.) Bandit Feedback
The **Player** gets to observe the reward/loss according to the specific action at time $t$, i.e.:
if $A_t = j$, then the player gets to only observe $x_{tj}$ (or $y_{tj}$).  

<u>The other arms' rewards are NOT revealed</u>.


### Regret:
Regret is with respect to the best fixed arm policy in hindsight.

$$
R_n(\pi, x) = \underset{i \leq j \leq k}{\max}\sum_{t=1}^n x_{tj} - \mathbb{E}\left[\sum_{t=1}^n x_{t{A_t}}\right]
$$
where $\pi$ is the policy chosen by the **Player**,
$x$ is the sequence of rewards chosen by the **Adversary** (the [[Environment]]),
the $\max$ term is the highest fixed arm reward in hindsight,
the $\mathbb{E}$ term is the expected value of the accumulated reward of what the player has seen over time horizon $n$.

For loss, the equivalent is:
$$
R_n(\pi, y) = \mathbb{E}\left[\sum_{t=1}^n y_{tA_t}\right] - \underset{i \leq j \leq k}{\min} \sum_{t=1}^n y_{tj}
$$


---
# References
