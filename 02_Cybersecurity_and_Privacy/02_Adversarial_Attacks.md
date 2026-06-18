---
layout: page
title: Adversarial Attacks on Deep Learning Models
---

# Adversarial Attacks on Deep Learning Models

**Overview:** How tiny pixel perturbations fool image classifiers. Implications for autonomous vehicles and facial recognition systems.

---

### 1. What is it? — Definition and core concept

Adversarial Attacks are carefully crafted, imperceptible perturbations to inputs that fool machine learning models into incorrect predictions. For example, adding carefully chosen pixel noise to a Stop sign image causes a deep neural network to classify it as a Yield sign—imperceptible to humans but catastrophic for autonomous vehicles. Formally, given model f(x) = y (correct classification of image x), adversaries find x' = x + δ (x + noise δ) such that f(x') = y' (incorrect class) where δ is small and x' appears identical to humans. Adversarial attacks exploit the non-linearity and high-dimensionality of neural networks; models confidently misclassify seemingly obvious inputs. Attacks fall into two categories: (1) **White-box**: Attacker knows model architecture/weights; (2) **Black-box**: Attacker only queries model output.

### 2. Why now? — What recent development made this relevant

Deep neural networks' susceptibility to adversarial examples was discovered empirically (Szegedy et al., 2013) and formalized theoretically (Goodfellow et al., 2015 FGSM). Deployment of neural networks in high-stakes domains (autonomous vehicles, medical diagnosis, facial recognition) exposed real risk: a few pixels could disable safety-critical systems. Autonomous vehicle research (Eykholt et al., 2018) showed physical adversarial patches (printed stickers) on stop signs fool real-world detectors. Facial recognition systems (Evtimov et al., 2016) defeated by special glasses. Security research community recognized adversarial robustness as fundamental unsolved problem. Enterprise adoption of AI created urgency—production models must be robust. Adversarial training and certified defenses emerged, driving research funding and regulatory interest.

### 3. How does it work? — Technical architecture or mechanism

**FGSM (Fast Gradient Sign Method)**: Simplest attack. Compute gradient of loss ∇L(x, y_true) w.r.t. input x. Perturb x in gradient direction: x' = x + ε \* sign(∇L(x, y_true)), where ε is step size. Moves input toward higher loss (wrong class). One step, very fast. **PGD (Projected Gradient Descent)**: Iterative; applies FGSM multiple times, projecting back to ε-ball around x to maintain imperceptibility. Stronger than FGSM. **C&W (Carlini & Wagner)**: Formulates attack as optimization: minimize ||x' - x||\_2 subject to f(x') ≠ y_true. Finds minimal perturbation guaranteed to fool model; often stronger than PGD. **Transferability**: Adversarial examples on Model A often fool Model B—enables black-box attacks by crafting examples on open-source surrogate models, then attacking target model. **Defense**: Adversarial training (training on adversarial examples), certified defenses (randomized smoothing guarantees robustness within ε-ball), and detection (identifying adversarial inputs).

### 4. Real-world application — At least one deployed example

Tesla autopilot vulnerability: Adversarial patches (printed patterns) placed on roads fool lane detection, causing vehicles to swerve dangerously. Researchers (Eykholt et al., 2018) demonstrated this in simulation and real vehicles. Similarly, facial recognition systems (used by law enforcement, airports) are fooled by adversarial eyeglasses, defeating identity verification. Medical imaging: Adversarial perturbations in CT scans cause radiologist AI to misclassify tumors as benign. Bank fraud detection systems can be evaded by adversaries who subtly modify transaction patterns. Spam detection (Gmail, Twitter) is adversarially manipulated by attackers crafting emails/tweets that bypass filters. Defense: Companies like Tesla now train models on adversarial examples; Apple uses adversarial training for Face ID. Autonomous vehicle standards (ISO, SAE) mandate adversarial robustness testing.

### 5. Challenges and open problems — What is still unsolved

(1) **Robustness-accuracy tradeoff**: Adversarial training improves robustness but degrades accuracy on clean data; finding Pareto-optimal solutions is hard. (2) **Certified defenses scale**: Randomized smoothing (provably robust) is 100x slower than standard inference; impractical for real-time systems. (3) **Black-box robustness**: Even models trained on adversarial examples are vulnerable to novel attacks; universal defense remains elusive. (4) **Physical adversarial examples**: Robustness in clean test environments doesn't translate to physical world (lighting, angles, occlusion variations). (5) **Detection failure**: No reliable method detects adversarial examples; detection can itself be adversarially attacked. (6) **Transferability understanding**: Why do adversarial examples transfer between models? Theoretical understanding is incomplete. (7) **Semantic perturbations**: Attacks beyond pixel perturbations (e.g., rotating objects) are less studied.

### 6. Future scope — Where research is heading in 2–5 years

(1) **Physical adversarial defense**: Models trained on physically realistic augmentations achieving robust-in-the-wild performance. (2) **Interpretability + robustness**: Integrating adversarial robustness with explainability (robust models should have consistent, trustworthy explanations). (3) **Certified defenses efficiency**: Randomized smoothing variants achieving 2-5x speedup via efficient sampling and GPU utilization. (4) **Multimodal robustness**: Defending against adversarial attacks on combined vision-language models (text + image). (5) **Continual learning**: Updating models continuously to defend against new attack types without catastrophic forgetting. (6) **Generalization theory**: Fundamental theory of why adversarial robustness is hard; PAC-learning bounds for robust learning. (7) **Regulatory standards**: ISO/IEC standards mandating adversarial robustness testing for autonomous systems; certification frameworks emerge.

---

## Key Topics to Explore:

- Adversarial examples and perturbations
- FGSM (Fast Gradient Sign Method)
- Transferability of adversarial attacks
- Implications for autonomous vehicles
- Facial recognition vulnerabilities
- Defense mechanisms and robustness
