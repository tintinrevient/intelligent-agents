## Trust

### Luhmann’s distinction
* **Hope**: Wish it will come true (no basis)
* **Confidence**: Think it will come true (based on evidence)
* **Trust**: Commit to action with partly uncertain consequences

### Computational trust
1. Send request to service providers
2. Receive a service
3. Evaluate the service
4. Update the **model** of service providers based on **evidence**

**Local trust**:
* many service providers
* service providers enter and leave

**Institutional trust**:
* **centralized** reputation system
* **privacy**: raters may not reveal true ratings in public
* **trust**: it is unknown where the ratings come from

**Social trust**:
* ask those you trust
* **context**: the context of usage may be unspecified
* **satisfaction criteria**: the expectations of the raters may be different

### Beta-Reputation system

* **Beta density function** is used for **binary events**
* α = r + 1 and β = s + 1
	* r = occurrences of x (successful transactions)
	* s = occurrences of x' (unsuccessful transactions)
* The probability expectation of **beta distribution**: E(p) = α / (α + β)

<p float="left">
	<img src="./pix/beta-distribution.png" width="600" />
</p>

* X(p<sup>X</sup><sub>T</sub>) = T’s reputation by agent X
* E(p<sup>X</sup><sub>T</sub>) = (r<sup>X</sup><sub>T</sub> +1) / (r<sup>X</sup><sub>T</sub> + s<sup>X</sup><sub>T</sub> + 2) -> [0, 1]
* Rep(r<sup>X</sup><sub>T</sub>, s<sup>X</sup><sub>T</sub>) = (E(p<sup>X</sup><sub>T</sub>) - 0.5) * 2 -> [-1, 1]

### Belief theory

w<sup>X</sup><sub>Y</sub> = (b<sup>X</sup><sub>Y</sub>, d<sup>X</sup><sub>Y</sub>, u<sup>X</sup><sub>Y</sub>): X’s opinion of Y for **belief**, **disbelief**, **uncertainty**

Given X’s opinion of Y (w<sup>X</sup><sub>Y</sub> = (b<sup>X</sup><sub>Y</sub>, d<sup>X</sup><sub>Y</sub>, u<sup>X</sup><sub>Y</sub>)) and Y’s opinion of T (w<sup>Y</sup><sub>T</sub> = (b<sup>T</sup><sub>T</sub>, d<sup>Y</sup><sub>T</sub>, u<sup>Y</sup><sub>T</sub>)), how much X should trust T (w<sup>X</sup><sub>T</sub> = (b<sup>X</sup><sub>T</sub>, d<sup>X</sup><sub>T</sub>, u<sup>X</sup><sub>T</sub>))?

**individual b, d, u**
* b = r / (r + s + 2)
* d = s / (r + s + 2)
* u = 2 / (r + s + 2)

**transitive b, d, u**
* b<sup>X</sup><sub>T</sub> = b<sup>X</sup><sub>Y</sub> * b<sup>Y</sup><sub>T</sub>
* d<sup>X</sup><sub>T</sub> = b<sup>X</sup><sub>Y</sub> * d<sup>Y</sup><sub>T</sub>
* u<sup>X</sup><sub>T</sub> = d<sup>X</sup><sub>Y</sub> + u<sup>X</sup><sub>Y</sub> + b<sup>X</sup><sub>Y</sub> * u<sup>Y</sup><sub>T</sub>

**Discounted reputation** (r<sup>X</sup><sub>T</sub>, s<sup>X</sup><sub>T</sub>) = (2*b/u, 2*d/u)

Rep(r<sup>X</sup><sub>T</sub>, s<sup>X</sup><sub>T</sub>) = (((r + 1) / (r + s + 2)) - 0.5) * 2 -> [-1, 1]

