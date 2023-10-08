202211041854

Tags: #deeplearning

# Imitation Learning
A type of [[Reinforcement Learning]] where an agent's actions change the state of the world.  An expert/oracle/human provides data for the agent to learn from.  For example, playing a game and having the agent learn.  The expert provides trajectories with high returns for rewards.

Policy: [[Supervised Learning]]

Difficulties:
- Expert has to provide a large amount of data
- Drifting of the agent from the expert's trajectory can cause unseen consequences.  For example, in a driving game, if the agent goes off-track and the expert never showed this scenario to learn from, it can do unexpected things like driving in the wrong direction.  The expert would have to provide even more data for these scenarios.

---
# References
