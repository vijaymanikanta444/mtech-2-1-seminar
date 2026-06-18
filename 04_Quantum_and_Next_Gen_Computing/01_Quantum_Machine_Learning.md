---
layout: page
title: Quantum Machine Learning — Where Quantum Meets AI
---

# Quantum Machine Learning — Where Quantum Meets AI

**Overview:** Variational quantum circuits, quantum advantage for optimization problems, current limitations and realistic timelines.

---

### 1. What is it? — Definition and core concept

Quantum Machine Learning (QML) combines quantum computing and machine learning, exploiting quantum phenomena (superposition, entanglement, interference) to improve learning algorithms. Unlike classical ML where data is classical bits, QML operates on quantum bits (qubits) existing in superposition—simultaneously 0 and 1 until measured. Potential advantages: (1) Exponential speedup on certain problems (linear system solving, optimization), (2) Sampling exponentially large spaces efficiently, (3) Quantum kernel methods achieving higher expressivity. QML includes quantum-classical hybrids: quantum computer solves subproblems, classical computer coordinates—practical given current limited qubit counts.

### 2. Why now? — What recent development made this relevant

Quantum hardware matured: IBM, Google, IonQ, Rigetti built systems with 50-1000 qubits (error-prone, but usable). Google's "quantum advantage" paper (2019) demonstrated quantum superiority on specific tasks. NISQ era (Noisy Intermediate-Scale Quantum) accepted that near-term quantum computers are imperfect; algorithms designed for noisy machines emerged (variational quantum algorithms). Venture capital flooded QML startups (100+ companies). Academia (MIT, UC Berkeley, University of Waterloo) invested heavily in research. Financial institutions (JP Morgan, Goldman Sachs) explored quantum algorithms for portfolio optimization, derivatives pricing. Pharmaceutical companies (Merck, AstraZeneca) investigated quantum for drug discovery. Cloud access (IBM Quantum Experience, AWS Braket) made experiments accessible.

### 3. How does it work? — Technical architecture or mechanism

**Variational Quantum Algorithms (VQA)**: Hybrid approach. Quantum circuit U(θ) with tunable parameters θ processes input; measures output; cost function C(θ) evaluates performance. Classical optimizer (gradient descent) updates θ to minimize cost. Repeat until convergence. Example: QAOA (Quantum Approximate Optimization Algorithm)—maps optimization problem to Ising model, quantum circuit approximates optimal solution. **Quantum kernel methods**: Data mapped to quantum space via quantum feature map, then classical classifier (SVM) operates on quantum features. Potentially exponential feature space with polynomial quantum circuit depth. **VQE (Variational Quantum Eigensolver)**: Finds lowest eigenvalue of Hamiltonian (ground state energy); useful for simulating molecules. **Quantum neural networks (QNN)**: Trainable quantum circuits acting as neural networks; backprop replaced with parameter shift rule (computes gradients on quantum hardware).

### 4. Real-world application — At least one deployed example

VW (Volkswagen) used QAOA on IBM quantum computers to optimize traffic flow in Beijing—routing taxis more efficiently (simulations showed 25% congestion reduction vs. classical approach). JPMorgan tested quantum algorithms for portfolio optimization—finding efficient asset allocation for investments. Merck used quantum simulation to model molecular dynamics for drug candidates. Google's quantum team demonstrated quantum machine learning on toy problems (classifying points) with quantum advantage over classical methods (though limited practical impact currently). IBM Quantum Experience enables researchers worldwide to run experiments; QML papers increasingly report results on real quantum hardware.

### 5. Challenges and open problems — What is still unsolved

(1) **Quantum noise**: Current qubits decohere (lose quantum properties) within microseconds; errors accumulate, corrupting results. Error correction requires thousands of physical qubits per logical qubit. (2) **Barren plateaus**: Training variational quantum algorithms faces "barren plateaus"—gradients vanish for random initializations, making optimization impossible. (3) **Classical simulation**: Many proposed QML algorithms are simulatable classically (no quantum advantage). Proving quantum speedup is hard. (4) **Vanishing gradients**: Parameter shift rule for gradient computation becomes inefficient for large circuits. (5) **Limited expressivity**: Current circuits express limited function classes; unclear if they scale to general problems. (6) **Scalability**: Most QML algorithms demonstrated on tiny problems (5-10 qubits); scaling to 1000+ qubits is years away. (7) **Comparison fairness**: Comparing quantum vs. classical unfair—classical benchmarks often suboptimal.

### 6. Future scope — Where research is heading in 2–5 years

(1) **Error correction breakthroughs**: Quantum error correction codes achieving logical qubits with error rates < physical qubits. (2) **Better QML algorithms**: Discovering algorithms with proven exponential speedup over classical methods. (3) **Hybrid quantum-classical**: Quantum co-processors integrated with classical systems (like GPUs); QML becomes specialized tool for optimization subproblems. (4) **Larger quantum computers**: Systems with 1000s of qubits arriving; enabling exploration of meaningful problems. (5) **Quantum advantage demonstration**: Clear cases (drug discovery, optimization) showing practical quantum superiority. (6) **Standardized QML frameworks**: High-level abstractions enabling non-experts to write QML code. (7) **Quantum-inspired classical**: Classical algorithms inspired by quantum properties (tensor networks) achieving speedups without quantum hardware.

---

## Key Topics to Explore:

- Quantum bits (qubits) and superposition
- Variational quantum circuits
- Quantum advantage in optimization
- QAOA (Quantum Approximate Optimization Algorithm)
- VQE (Variational Quantum Eigensolver)
- Current hardware limitations
