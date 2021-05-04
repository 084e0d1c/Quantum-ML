---
date updated: '2021-05-04T21:26:55+08:00'

---

# Quantum Machine Learning

#### Youtube Tutorial

[Video Link](https://www.youtube.com/watch?v=qCRB0pPkmuc)

##### What is a Qubit?

- A single qubit can be described by a linear combination of state 0 and state one
- Concretely qubit can have $|0> = [1,0]^T \text{ and } |1> = [0,1]^T$
- Their combinations are added together by $\alpha$ and $\beta$, where they are complex numbers
- The qubit, given by $\phi$ , must be a unit vector where length =1

##### Bloch Sphere

![[bloch_sphere.png]]

- Moving $\theta$ will change the state value
- Moving $\phi$ will change the phase of the quantum state
- Manipulating both will allow us to move it to any point on the sphere

#### PennyLane Documentation

- Designed to be hardware and device agnostic, allowing quantum functions to be easily dispatched to different quantum devices
- We create a Quantum function (circuit + device)
- Classical Gradient decent is possible with PennyLane

![[pennylane.png]]

##### Quantum Embedding

- AngleEmbedding layer -> process data into qubit rotations
  - It encodes N features into the rotation angles of n qubits

- StronglyEntanglingLayers -> entangle the features together to do processing

- PennyLane provides templates for embedding

##### Variational Circuits

An alternative name is "parameterized quantum circuits"
![[variational_circuit.png]]

- Ingredients in a Variational Circuit
  1. Fixed initial state (vacuum state or zero state)
  2. A quantum circuit $U(\theta)$ where the free params are $\theta$ -> the entanglement param is $\theta$
  3. Measurement at the output
- They are trained by classical optimization algorithms and $\theta$ is updated with every step (assuming using Stochastic Gradient Descent)
- A near term solution for quantum models
- Typically they have short gate sequences, to minimize floating error in each output
- Classical input is fed into the quantum circuit alongside weights ($\theta$) and is converted back to classical information by measuring and evaluating the expectation value of the observable value
