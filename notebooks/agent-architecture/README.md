## Agent Architecture

### Reflex Agent

* Require a large **condition-action rules** for realistic scenarios

![reflex-agent](./pix/reflex-agent.png)

### Reflex Agent with States

* **Remember the past** through internal state
* Example: The agent does not want to receive more than three emails a day

![reflex-agent-with-states](./pix/reflex-agent-with-states.png)

### Goal-based Agent

* Identify **goal states** where the goal holds
* Perform **actions** that will take the agent to goal states
* **Goal types**:
	* Perform goal: an action
	* Achieve goal: goal state
	* Maintain goal: continue to establish a condition
	* Query goal: obtain piece of information
* **Goal operations**:
	* Adopt
	* Activate
	* Suspend
	* Drop

![goal-based-agent](./pix/goal-based-agent.png)

### Utility-based Agent

* **Utility**: **how good is a state**

![utility-based-agent](./pix/utility-based-agent.png)

### BDI Agent

* **Belief**: What the agent thinks is true
* **Desire**: The **set of states** that the agent would like to be in (may be **inconsistent**)
* **Intention**: A **subset of desires** for which the agent will act towards (**consistent**)
