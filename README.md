# QubitHUB QInterpreter Challenge: Bell State Hackathon 
> **Event:** IBM Qiskit Fall Fest x QubitHub 2025  
> **Researcher:** Edwin Kofi Afful  
> **Focus:** Cross-Platform Quantum Interoperability & Circuit Transcription

---

## The Challenge
The core objective of this project was to evaluate the **QInterpreter** transcription engine by implementing a 2-qubit Bell State $|\Phi^+\rangle$ and successfully migrating it across five distinct quantum programming ecosystems. 

As a hackathon entry, this project demonstrates the ability to rapidly diagnose **Intermediate Representation (IR) bugs** and engineer real-time architectural patches to maintain data integrity across heterogeneous backends.

### 🛠️ The Multi-Framework Stack
The circuit was successfully validated across the following pipeline:
**Qiskit** (Source) $\longrightarrow$ **Cirq** $\longrightarrow$ **PennyLane** $\longrightarrow$ **Amazon Braket** $\longrightarrow$ **PyQuil**

---

## Project Assets
* **[Bell_State_Challenge_Report.pdf](./Bell_State_Challenge_Report.pdf)**: Comprehensive technical audit detailing "Fail-States," version mismatch analysis, and statistical validation of Pauli Expectation values.
* **[code.py](./code.py)**: A production-ready script optimized for **Google Colab**, featuring automated dependency management and unified result visualization.
* **[Participation Certificate](./Qiskit_FallFest_Certificate_Edwin_Afful.pdf)**: Official recognition from the **IBM Qiskit Fall Fest x QubitHub 2025**.

---

## Technical Debugging & Patches
Under hackathon constraints, I identified and resolved several systemic "breaking" issues to ensure cross-platform parity:

| Issue | Root Cause | Engineering Patch |
| :--- | :--- | :--- |
| **Convention Mismatch** | PennyLane uses $\pm 1$ eigenvalues; Qiskit uses $0/1$ bits. | Engineered an inline normalization function to standardize output. |
| **Backend Isolation** | Cloud QVMs (PyQuil/Braket) unreachable in Colab. | Re-engineered the stack to use `WavefunctionSimulator` and `LocalSimulator`. |
| **API Deprecation** | Legacy Qiskit syntax caused execution termination. | Migrated to the modern `AerSimulator()` stable API. |
| **Bit-Ordering** | Inconsistent qubit mapping (MSB vs LSB) across frameworks. | Applied bit-reversal scripts to ensure '00' and '11' state parity. |

---

## Benchmarks (1024 Shots)
| Framework | '00' Counts | '11' Counts | Result |
| :--- | :--- | :--- | :--- |
| **Qiskit** | ~512 | ~512 | ✅ Validated |
| **PennyLane** | ~510 | ~514 | ✅ Validated |
| **PyQuil** | ~515 | ~509 | ✅ Validated |
| **Braket** | ~520 | ~504 | ✅ Validated |
| **Cirq** | ~511 | ~513 | ✅ Validated |

---

## How to Run
This repository is optimized for **one-click verification** in Google Colab:
1. Open a new notebook in **Google Colab**.
2. Upload **`code.py`**.
3. Execute the script. It will automatically install the necessary quantum libraries and generate the comparison matrix.

---

## Certification & Recognition
**IBM Qiskit Fall Fest x QubitHub 2025** I participated in this technical challenge to benchmark the limits of cross-platform quantum transcription. This repository represents my successful implementation and documentation of the 2-qubit Bell State migration.  
**[View Participation Certificate](./Qiskit_FallFest_Certificate_Edwin_Afful.pdf)**

---

## Skills Demonstrated
* **Quantum DevOps:** Automated environment setup and cross-platform library management.
* **Transcription Auditing:** Deep-dive analysis of Intermediate Representations (IR).
* **Statistical Verification:** Ensuring physical consistency ($\langle X \otimes X \rangle, \langle Z \otimes Z \rangle$) across simulators.

---
**Conclusion:** This project confirms that while automated tools like QInterpreter are vital for the ecosystem, **human oversight (Quantum DevOps)** is essential to resolve hardware-specific measurement conventions and backend mismatches.
