---
layout: page
title: Edge AI — Running Intelligence at the Device Level
---

# Edge AI — Running Intelligence at the Device Level

**Overview:** TinyML, ONNX runtime, model quantization. How AI is moving from data centers to smartphones, sensors, and IoT devices.

---

### 1. What is it? — Definition and core concept

Edge AI refers to running machine learning models directly on edge devices (smartphones, IoT sensors, embedded systems, autonomous vehicles, drones) rather than sending raw data to cloud servers for inference. Inference happens locally on the device itself, reducing latency, bandwidth, and privacy risks. Edge devices have limited computational resources (CPU, memory, power), requiring model optimization techniques: quantization (reducing precision from float32 to int8), pruning (removing low-weight connections), distillation (training smaller models), and architecture search (finding efficient network designs). The goal: Deploy models on megabyte-constrained devices running on AA batteries.

### 2. Why now? — What recent development made this relevant

Mobile devices now have sufficient compute (modern smartphone SoCs rival 2015 GPUs). Cloud inference faced latency problems—sending video to cloud, processing, returning decision took hundreds of milliseconds, inadequate for real-time use (autonomous vehicles, VR). Privacy concerns (users unwilling to send biometric data to cloud) drove local processing demand. 5G networks promised high bandwidth but edge inference remains more efficient (no network round-trip, always available offline). TensorFlow Lite (2017), PyTorch Mobile (2019), ONNX Runtime optimized for edge deployment. Regulatory pressure (GDPR, on-device consent) made edge processing mandate. Emergence of specialized edge chips (Apple Neural Engine, Google TPU Lite, Qualcomm Snapdragon) enabled efficient inference.

### 3. How does it work? — Technical architecture or mechanism

**Model optimization pipeline**: (1) **Quantization**: Convert weights/activations from float32 (4 bytes) to int8 (1 byte), 4x size reduction with minimal accuracy loss. Quantization-aware training simulates quantization during training, maintaining accuracy. (2) **Pruning**: Remove connections with low magnitude; remove entire filters/channels. Can reduce parameters by 90% with minor accuracy impact. (3) **Distillation**: Train small "student" model to mimic large "teacher" model; knowledge transfer enables tiny models. (4) **Architecture search (NAS)**: Automatically find efficient architectures (MobileNet, EfficientNet) for resource constraints. (5) **Compilation**: Convert models to optimized hardware formats via TVM, MLIR, enabling OS-level optimizations. **Execution**: Models run within frameworks: TensorFlow Lite (Android/iOS), PyTorch Mobile, ONNX Runtime, CoreML (Apple). Hardware acceleration: NPU (Neural Processing Unit) or GPU sub-cores when available.

### 4. Real-world application — At least one deployed example

Google Pixel phones run face unlock on-device using quantized models (~50MB) executing in 100ms on Tensor SoC. Raw facial data never leaves phone—privacy-maximized biometric authentication. Apple's on-device ML processes Siri, text recognition, photo search locally; sensitive data stays private. Qualcomm Snapdragon runs object detection (YOLO) on smartphones enabling augmented reality, barcode scanning in real-time. Tesla's autopilot runs vision models (detected via teardowns: 300MB+ models quantized to int8) on car's custom Autopilot Computer Processing Unit for real-time lane detection. Medical devices: Portable ultrasound machines with on-device AI for cardiac imaging enable clinics without on-site AI experts. Agriculture: Edge AI on autonomous drones detects crop diseases, enabling targeted pesticide application.

### 5. Challenges and open problems — What is still unsolved

(1) **Accuracy-efficiency tradeoff**: Quantizing models to run on tiny devices (1-100MB) degrades accuracy; maintaining usable performance remains hard. (2) **Model customization**: Generic models don't suit all devices; customizing models per device type is tedious. (3) **Power efficiency**: Even quantized models drain battery fast; balancing inference quality and battery life is unsolved. (4) **Latency variability**: Burst traffic or background processes interfere; deterministic low-latency inference hard on consumer devices. (5) **Over-the-air updates**: Pushing new models to billions of devices is challenging; rollback on errors is hard. (6) **Hardware diversity**: Every phone SoC differs (different CPU/NPU/GPU); optimizing per hardware is complex. (7) **Federated learning integration**: Combining edge inference with on-device training for federated learning remains immature.

### 6. Future scope — Where research is heading in 2–5 years

(1) **Efficient architectures**: Novel architectures (e.g., State Space Models) potentially more efficient than transformers for edge. (2) **Better compression**: Techniques beyond quantization/pruning (e.g., dynamic computation graphs, conditional execution) enable deeper networks on edge. (3) **Specialized hardware**: Custom edge chips (ARM, Apple, Qualcomm) with domain-specific instructions for AI (vector operations, sparsity support). (4) **Continual learning on edge**: Models updating locally with new data, adapting to user's device over time. (5) **Federated training on edge**: Not just inference but training on device, feeding updates to global model securely. (6) **Semantic compression**: Compressing models by learning high-level semantics rather than raw parameters. (7) **Standardized deployment**: ONNX and other standards becoming industry default, reducing fragmentation.

---

## Key Topics to Explore:

- TinyML framework
- ONNX runtime
- Model quantization and pruning
- Optimization for mobile and IoT
- Latency and bandwidth considerations
- Real-time inference at the edge
