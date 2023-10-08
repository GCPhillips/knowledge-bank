202306011039

Tags: #machinelearning

# Decision Tree
A type of [[Model]] where each node has two possible paths which lead to more nodes or leaves.  The leaves are the responses from the provided input literals.

```mermaid
graph TD
	A(Color?) --> |other| B(not-tasty)
	A --> |pale green to pale yellow| C(Softness?)
	C --> |other| D(not-tasty)
	C --> |slightly soft| E(tasty)
```
The above example is parameterized by a two-dimensional bit vector, where the first bit represents Color and the second bit represents Softness.

---
# References
