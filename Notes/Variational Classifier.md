---
date updated: '2021-05-06T11:26:35+08:00'

---

# Variational Classifier

[Medium Article Explaining](https://medium.com/swlh/qa2-explaining-variational-quantum-classifiers-b584c3bd7849)

[Article examining QML in Hilbert Space](https://medium.com/xanaduai/analyzing-data-in-infinite-dimensional-spaces-4887717be3d2)

### Intuition

By embedding the input features into Hilbert Space, we are effectively blowing up the data for analysis

Quantum computers can compute inner products in a large space easily. The potential advantage arises in that the feature mapping could potentially produce kernels that classical computers cannot.

They are thought to have an edge over classical models through higher effective dimension and faster training abilities.

### Data Encoding

We use a feature map to move input data from classical to quantum states.

1. Basic Embedding
   1. We encode the data into binary strings

2. Amplitude Embedding
   1. Encode the data as amplitudes of a quantum state
   2. A classical data point with N features will have a n-qubit quantum state, where $N = 2^n$
   3. Input ought to be normalized before embedding

3. Angle Embedding

### Workflow

_Important to use PennyLane's version of Numpy_

1. Create a device with n qubits (wires)

2. Define a "block" -> elementary circuit architecture that repeats to build the variational circuit
   1. This is completely customizable
   2. Typically consist of U3 Rotation (phi, theta and omega) and CNOT
   3. These are weights and tunable

3. State Preparation

4. Define the quantum node
   1. Invoke stateprep
   2. Build the "layers" using the blocks
   3. Return expval on observable value

5. Define the cost function
6. Define metric function (accuracy)

### Additional Materials

Definitions
Domain: possible inputs into a function
Co-domain: possible output from the function
Range: actual output from the function
