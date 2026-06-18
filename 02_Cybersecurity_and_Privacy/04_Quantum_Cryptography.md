---
layout: page
title: Quantum Cryptography and Post-Quantum Security Standards
---

# Quantum Cryptography and Post-Quantum Security Standards

**Overview:** NIST's post-quantum cryptography standards (2024). Why RSA will become obsolete and what replaces it.

---

### 1. What is it? — Definition and core concept

Quantum Cryptography uses quantum mechanics principles to secure communications against eavesdropping. Two paradigms exist: (1) **Quantum Key Distribution (QKD)**: Securely establishes encryption keys using quantum properties; even if eavesdropped, the quantum state collapses, revealing the breach. (2) **Post-Quantum Cryptography (PQC)**: Classical cryptographic algorithms believed resistant to quantum computers (lattice-based, code-based, hash-based). The distinction: QKD addresses future threats; PQC addresses today's "harvest now, decrypt later" attacks where adversaries collect encrypted data now, waiting for quantum computers to crack it later. Classical cryptography (RSA, ECC) is vulnerable to quantum algorithms (Shor's algorithm, 1994) running in polynomial time on quantum computers.

### 2. Why now? — What recent development made this relevant

Quantum computing progress accelerated: IBM, Google, and startups (IonQ, Rigetti) built quantum processors with 100+ qubits. Google claimed "quantum advantage" (2019) solving specific problems faster than classical computers. While current quantum computers can't yet factor large numbers (Shor's algorithm requires millions of physical qubits; today's are hundreds), the trajectory suggests cryptographically-relevant quantum computers arriving in 15-30 years. Simultaneously, adversaries employ "harvest now, decrypt later" attacks: collecting encrypted communications today for future decryption. NIST formalized this threat (2022) and standardized post-quantum cryptography algorithms. Governments (China, USA, EU) mandated migration to PQC. Financial institutions, healthcare, and defense recognized urgency; banks holding encrypted data for 40+ years face retroactive decryption. China announced quantum computer breakthroughs (2024), accelerating PQC adoption timelines.

### 3. How does it work? — Technical architecture or mechanism

**Quantum Key Distribution (BB84 Protocol, 1984)**: Alice sends random bits encoded in random bases (rectilinear or diagonal). Bob measures using random bases. They publicly compare bases; keep bits measured with matching bases (50% retained). Eavesdropper Eve measuring with wrong basis introduces errors detectable by Alice-Bob. Security is information-theoretic—impossible to eavesdrop perfectly. **Post-Quantum Cryptography (NIST Standards, 2024)**: (1) **Lattice-based** (Kyber, Dilithium): Hard problem is finding short vectors in high-dimensional lattices. Assumed resistant to quantum algorithms. (2) **Code-based** (Classic McEliece): Hard problem is decoding random linear codes; believed quantum-hard. (3) **Hash-based** (SPHINCS+): Security relies on hash function properties; unconditionally secure post-quantum. (4) **Multivariate polynomial-based**: Solving systems of multivariate equations over finite fields. NIST selected Kyber (KEM) and Dilithium (signature) as primary standards; others as alternatives.

### 4. Real-world application — At least one deployed example

China's Micius satellite (2017-present) implements QKD over 1200 km distances, establishing secure communication with ground stations. Banks (Standard Chartered, Commonwealth Bank) pilot QKD networks for inter-branch communication. US Department of Energy deployed QKD in the Quantum Internet Alliance testbed, linking national labs. Google, Amazon, and Microsoft initiated PQC migration: libraries now support post-quantum algorithms. Signal, Wire, and other messaging apps began integrating PQC algorithms. Financial standards (ISO, NIST) mandate PQC adoption by 2030. The European Quantum Internet Alliance deployed QKD across Europe (quantum internet backbone). Practical deployment remains limited due to QKD equipment cost ($100K+) and range limitations (~200km), but adoption accelerates.

### 5. Challenges and open problems — What is still unsolved

(1) **QKD range/speed**: Quantum signals degrade over distance (loss ~50% per 50km); long-distance requires repeaters (quantum repeaters are hard to build). (2) **PQC standardization maturity**: Standards finalized (2024) but implementations nascent; cryptographic agility (swapping algorithms) in deployed systems is hard. (3) **Key size**: Post-quantum keys are 2-100KB vs. <1KB for RSA; storage/transmission overhead significant. (4) **Performance**: PQC operations slower than classical crypto; 1000x slower in some cases; real-time systems struggle. (5) **Security assumptions**: PQC relies on hardness assumptions not mathematically proven; quantum algorithms discovering shortcuts is a risk. (6) **Hybrid transition**: Transitioning existing systems to PQC without breaking compatibility requires hybrid approaches (run classical + PQC in parallel) that complicate deployment. (7) **Quantum repeaters**: Essential for long-distance QKD but remain largely theoretical; building reliable repeaters is unsolved.

### 6. Future scope — Where research is heading in 2–5 years

(1) **Quantum repeaters maturation**: Lab-to-field deployment enabling continent-spanning QKD networks. (2) **PQC hardware acceleration**: Specialized chips (TPM, HSM) accelerating post-quantum operations by 100x. (3) **Hybrid crypto transition**: Standards and tooling enabling painless classical→PQC migration; cryptographic agility by default. (4) **Satellite QKD**: Expanding to global QKD coverage via satellite constellation (Micius successors). (5) **Formal security proofs**: Mathematical proofs that PQC algorithms are quantum-hard (under accepted complexity assumptions). (6) **Quantum Internet Alliance maturation**: Functional continental quantum internet backbone operational. (7) **Regulatory mandates**: Governments enforcing PQC adoption timelines; deprecated algorithms (RSA, ECC) phased out by 2030-2035.

---

## Key Topics to Explore:

- Quantum key distribution (QKD)
- Post-quantum cryptography standards
- Lattice-based cryptography
- Hash-based signatures
- Why RSA is vulnerable to quantum attacks
- Migration strategies for existing systems
