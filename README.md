# Quantum Teleportation Simulator

This repository contains a quantum teleportation implementation using Google's Cirq framework. Quantum teleportation is a fundamental protocol in quantum information science that allows the transfer of quantum states from one location to another without physically moving the qubit itself.

## Overview

The project demonstrates several key quantum computing concepts:

- Basic quantum logic gates implementation (AND gate)
- 1-bit quantum addition
- Full quantum teleportation protocol

The teleportation protocol successfully transfers an arbitrary quantum state from one qubit to another using entanglement and classical communication.

## Features

- **Quantum AND Gate**: Implementation of a quantum AND operation using Hadamard and Toffoli gates  
- **1-bit Quantum Adder**: Circuit that adds two quantum bits and produces a sum and carry output  
- **Quantum Teleportation**: Complete implementation that:
  - Creates an arbitrary quantum state
  - Establishes entanglement between "Alice" and "Bob" qubits
  - Performs measurement and classical communication
  - Reconstructs the original quantum state at the receiver's end

## Requirements

- Python 3.6+
- Google Cirq
- NumPy

## Installation

```bash
pip install cirq numpy
```

## Usage

The notebook provides examples of how to:

- Initialize qubits
- Apply quantum gates
- Run quantum circuits on a simulator
- Analyze the results of quantum operations

### For teleportation specifically:

```python
# Create and run the teleportation circuit
circuit = create_teleportation_circuit()
result = sim.simulate(circuit)

# Visualize the state before and after teleportation
input_state = cirq.bloch_vector_from_state_vector(message.final_state_vector, 0)
output_state = cirq.bloch_vector_from_state_vector(final_results.final_state_vector, 2)
```

## How Quantum Teleportation Works

The implementation follows these steps:

1. **Preparation**: Alice and Bob share an entangled pair of qubits  
2. **Input**: A random quantum state is created for teleportation  
3. **Bell Measurement**: Alice entangles her part of the entangled pair with the message qubit and measures both  
4. **Classical Communication**: The measurement results are sent to Bob (simulated with CNOT and CZ gates)  
5. **Reconstruction**: Bob applies corrections to his qubit based on Alice's measurement results  

The Bloch sphere representation confirms the successful teleportation by showing identical vectors for the input and output states.

## Example Output

**Bloch sphere of randomly made Message:**  
x: -0.4069  
y: -0.3393  
z: -0.8481  

**Bloch Sphere of BOB qubit at Final State:**  
x: -0.4069  
y: -0.3393  
z: -0.8481  

## License

MIT

## Acknowledgements

This project utilizes Google's Cirq framework for quantum simulation.
