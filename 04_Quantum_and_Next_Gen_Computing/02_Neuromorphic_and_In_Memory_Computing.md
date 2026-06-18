---
layout: page
title: Neuromorphic and In-Memory Computing
---

# Neuromorphic and In-Memory Computing

**Overview:** Processing data where it is stored — eliminating the von Neumann bottleneck. Samsung, IBM research directions.

---

### 1. What is it? — Definition and core concept

Neuromorphic and In-Memory Computing both aim to overcome the "von Neumann bottleneck"—the separation of memory and processing units in traditional computers. Data constantly shuttles between memory and CPU, consuming energy and bandwidth. In-Memory Computing (IMC) performs computations directly where data is stored—eliminating data movement. For example, in DRAM, operations occur within memory cells. Neuromorphic computing, discussed separately, mimics the brain's integrated memory-computation architecture. In-Memory AI accelerators use ReRAM (resistive RAM) or PCM (phase-change memory) to store weights; computations exploit Ohm's law (V=IR) to perform matrix operations directly, avoiding data transfer.

### 2. Why now? — What recent development made this relevant

Data center energy consumption dominates cloud computing costs (~40% of infrastructure expense goes to data movement). AI workloads (massive matrix multiplications) waste 90% of energy moving data between memory and CPU. Emerging memory technologies (ReRAM, PCM, MRAM) enable in-memory computation: Samsung demonstrated in-memory AI achieving 100x energy efficiency vs. traditional architecture. Academic results (MIT, Berkeley) proved feasibility. ASIC manufacturers (Intel, Qualcomm) investing in in-memory compute. Machine learning's explosive growth (training/inference dominates data center compute) creates urgent need for efficient compute. Environmental concerns (data center carbon footprint) drove adoption. Regulatory pressure (carbon reporting, ESG mandates) incentivizes energy-efficient tech.

### 3. How does it work? — Technical architecture or mechanism

**Resistive RAM (ReRAM)**: 2D crossbar array where rows/columns intersect at memory cells containing variable resistors. Resistance values store weights. Applying voltage performs analog matrix multiplication—current flow through resistor values realizes Ohm's law computation. Example: Matrix-vector multiplication achieved by applying voltage vector to rows, measuring current at columns; output current ∝ (weight matrix) × (input vector). **Phase-Change Memory (PCM)**: Cells with variable resistance based on crystalline state; applied heat changes resistance. **Processing-in-memory (PIM)**: Memory array directly computes, eliminating data movement. **Analog compute**: Unlike digital processors (discrete 0/1), analog exploits continuous voltage/current to perform operations in-situ. Trade-off: Less precise but dramatically more energy-efficient. **ADC/DAC**: Analog-to-digital converters digitize results for downstream digital processing.

### 4. Real-world application — At least one deployed example

Samsung and IBM collaboration deployed in-memory AI prototype on 8 Gb ReRAM array—dense layer inference (1000×1000) with weights stored in ReRAM achieved 3.4x energy efficiency vs. conventional GPU on fixed-point quantized neural networks. Intel's Loihi (mentioned in neuromorphic section) integrates memory-compute. MIT demonstrated analog in-memory chip for protein folding simulations—protein sequence processing in analog crossbar arrays, results feed downstream digital processors. Graphcore's IPU (Intelligence Processing Unit) designs blur memory/compute; custom architecture co-locates both. SambaNova Systems deployed in-memory dataflow architecture for graph analytics and ML, achieving 10x throughput improvement on sparse problems vs. GPUs.

### 5. Challenges and open problems — What is still unsolved

(1) **Precision/Noise**: Analog computation is inherently noisy; tolerating errors while maintaining model accuracy is difficult. (2) **Programming model**: Expressing algorithms for in-memory execution requires new paradigms; traditional code doesn't map naturally. (3) **Testing/Debugging**: Verifying correctness of analog computation is hard; traditional debugging tools ineffective. (4) **Scalability**: Scaling crossbar arrays to 1M+ weights faces challenges: leakage currents, sneak paths (unintended current paths). (5) **Device variability**: Manufacturing ReRAM/PCM is imprecise; devices vary; compensating for variability is complex. (6) **Standardization**: No agreed-upon in-memory compute architectures; each vendor proprietary. (7) **Software stack**: Lacking compilers and frameworks for in-memory platforms; adoption limited by software maturity.

### 6. Future scope — Where research is heading in 2–5 years

(1) **Hybrid analog-digital**: Systems combining analog in-memory compute for linear algebra with digital for non-linear operations (activations). (2) **3D crossbars**: Stacking crossbar arrays vertically to increase density and interconnect efficiency. (3) **Neuromorphic + in-memory fusion**: Combining spiking neural networks with in-memory substrates for ultra-efficient brain-like compute. (4) **Standardized interfaces**: JEDEC, IEEE standardizing in-memory compute APIs; reducing vendor lock-in. (5) **Compiler infrastructure**: MLIR, TVM support for in-memory targets enabling tool reuse. (6) **Fault tolerance**: Techniques (redundancy, error correction) making analog compute as reliable as digital. (7) **Commercial adoption**: In-memory AI accelerators (startup Mythic, established players) becoming mainstream for inference; data centers adopting by 2027.

---

## Key Topics to Explore:

- Von Neumann bottleneck
- Processing in memory (PIM)
- ReRAM and memristors
- Samsung's developments
- IBM research initiatives
- Energy efficiency improvements
