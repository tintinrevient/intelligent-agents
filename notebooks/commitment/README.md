## Commitment

### Social commitment
* C(x, y, p): x commits to y to bring about p (**commitment**)
	* C(customer, merchant, payment)
* CC(x, y, p, q): x commits to y to bring about q, if y brings about p first (**conditional commitment**)
	* CC(customer, merchant, delivery, payment)

**Protocol states** are represented by **Social commitments**:
![protocol-states](./pix/protocol-states.png)

### Reasoning rules

![reasoning-rule](./pix/reasoning-rule.png)

* **Detach**: CC(x, y, p, q) ceases to exist, if p becomes true, and C(x, y, q) is created.
* **Discharge** active: C(x, y, q) ceases to exist, if q becomes true.
* **Discharge** conditional: CC(x, y, p, q) ceases to exist, if p becomes true, and C(x, y, q) is created.
* **Cancel** active: C(x, y, q) remains open, and q becomes false.

