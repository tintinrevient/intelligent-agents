## JADE

### Architecture

![infrastructure](./pix/infrastructure.png)

* **DF** (Directory Facilitator): Agent service registration
* **AMS** (Agent Management System): Agent registration, incl. agents' lifecycle and AID (Agent Identifier)
* **GADT** (Global Agent Descriptor Table): Agent registration, incl. agents' status and location
* **LADT** (Local Agent Descriptor Table)
* **CT** (Container Table): Container registration, incl. containers' object reference and transport address
* **MTP** (Message Transport Protocol)
* **IMTP** (Internal Message Transport Protocol)

It has a close resemblance to MicroService architecture:
* Main Container <-> Eureka Server
* Container <-> Docker
* Asynchronous Message-Based Communication <-> RabbitMQ

### Container

![infrastructure](./pix/container.png)

### Tool

The class diagram of JADE tools is as below:

![class-diagram](./pix/class-diagram.png)


### References

* https://jade.tilab.com/

