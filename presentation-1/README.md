## IBM Watson/Question Answering Systems

### What is IBM Watson?

#### Software
**Cognitive computing**: technology platforms based on artificial intelligence and signal processing, which encompass machine learning, reasoning, natural language processing, speech recognition and vision (object recognition), human–computer interaction, dialog and narrative generation.

Features of cognitive systems:
* **Adaptive**: They may learn as information changes, and as goals and requirements evolve. They may resolve ambiguity and tolerate unpredictability. They may be engineered to feed on dynamic data in real time, or near real time.
* **Interactive**: They may interact easily with users so that those users can define their needs comfortably. They may also interact with other processors, devices, and cloud services, as well as with people.
* **Iterative and stateful**: They may aid in defining a problem by asking questions or finding additional source input if a problem statement is ambiguous or incomplete. They may "remember" previous interactions in a process and return information that is suitable for the specific application at that point in time.
* **Contextual**: They may understand, identify, and extract contextual elements such as meaning, syntax, time, location, appropriate domain, regulations, user’s profile, process, task and goal. They may draw on multiple sources of information, including both structured and unstructured digital information, as well as sensory inputs (visual, gestural, auditory, or sensor-provided).

Applications of cognitive systems:
* **Education**: e.g., an assistant that is personalized for each individual student.
* **Healthcare**: e.g., an assistant to evaluate information about the patient, looking through every medical record in depth, searching for indications that can be the source of their problems.

#### Hardware
**Cognitive computer**: it combines artificial intelligence and machine learning algorithms, in an approach which attempts to reproduce the behaviour of the human brain. e.g., a cognitive computer implemented by using neural networks and deep learning is provided by the IBM company's Watson machine. A subsequent development by IBM is the TrueNorth microchip architecture, which is designed to be closer in structure to the human brain than the von Neumann architecture used in conventional computers.

**TrueNorth** is a manycore processor network on a chip design, with 4096 cores, each one having 256 programmable simulated neurons for a total of just over a million neurons. In turn, each neuron has 256 programmable "synapses" that convey the signals between them. Hence, the total number of programmable synapses is just over 268 million (228). Memory, computation, and communication are handled in each of the 4096 neurosynaptic cores, TrueNorth circumvents the von-Neumann-architecture bottleneck and is very energy-efficient.

#### Different Voices

There are critics who argue that a room-sized computer - like the case of Watson - is not a viable alternative to a three-pound human brain.

There are experts who claim that cognitive systems could adopt the biases of their developers.

### Technical Architecture & Implementation

#### Expert system
An expert system is divided into two subsystems: 
* **inference engine**: it applies the rules to the known facts to deduce new facts.
* **knowledge base**: it represents facts and rules.

Approaches:
* if-then rules
* Prolog (logic programming language): first-order logic

Disadvantages:
* knowledge acquisition problem
* the size of the knowledge base increases
* verify whether decision rules are consistent with each other
* prioritize the use of the rules in order to operate more efficiently

Evolutions:
* **truth maintenance**: when facts are altered, dependent knowledge can be altered accordingly.
* **hypothetical reasoning**: the knowledge base can be divided up into many possible views, so the inference engine can explore multiple possibilities in parallel.
* **uncertainty systems**: the first extensions of simply using rules to represent knowledge was also to associate a probability with each rule, such as **fuzzy logic**.
* **ontology classification**: these types of special purpose inference engines are termed **classifiers**, which are very powerful for **unstructured volatile domains**, and are a key technology for the Internet and the emerging **semantic web**.

#### Question Answering

* closed-domain question answering
* open-domain question answering

### Related Technologies
* Affective computing
* Analytics
* Artificial neural network
* Semantic Web
* Social neuroscience
* Synthetic intelligence

### Future of IBM Watson?


### Reference

* https://en.wikipedia.org/wiki/Watson_(computer)
* https://en.wikipedia.org/wiki/Question_answering
* https://en.wikipedia.org/wiki/Expert_system
* https://en.wikipedia.org/wiki/Cognitive_computing
* https://en.wikipedia.org/wiki/Cognitive_computer
* https://en.wikipedia.org/wiki/Von_Neumann_architecture

* https://www.ibm.com/watson

* https://www.youtube.com/watch?v=YgYSv2KSyWg
* https://www.youtube.com/watch?v=lI-M7O_bRNg
