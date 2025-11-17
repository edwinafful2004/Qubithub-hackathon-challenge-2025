# QInterpreter Real-World Application Challenge

This repository contains the submission for the QubitHUB QInterpreter Challenge. The project analyzes the translation of a 2-Qubit Bell State across multiple quantum frameworks, documenting and fixing compatibility issues.

## Project Files

This repository contains two primary files:

- **Bell_State_Challenge_Report.pdf**: The complete solution document. This PDF details the chosen problem (2-Qubit Bell State), the original Qiskit code, the translation issues found (e.g., deprecated functions, backend errors, measurement mismatches), the fixes and workarounds applied, and a final comparison of results.
- **code.py**: A Python script (originally from Google Colab) containing the complete, working, and fixed code for all tested frameworks:
  - Qiskit (Original Implementation)
  - Cirq (Translated & Fixed)
  - PennyLane (Translated & Fixed)
  - Amazon Braket (Translated & Fixed)
  - PyQuil (Translated & Fixed)

## How to Run

The code.py file is designed to be run in an environment like **Google Colab** or a **Jupyter Notebook**.

- Open [Google Colab](https://colab.research.google.com/).
- Go to File > Upload notebook and select the code.py file from this repository.
- Run the cells in order.

All necessary Python libraries (Qiskit, Cirq, etc.) are installed directly by the script using !pip install commands.

## Summary of Findings

This project successfully translated a Qiskit Bell State circuit and identified several key cross-framework compatibility issues, which are detailed in the report. Key findings include:

- **Deprecated Functions**: Updating Aer.get_backend() to AerSimulator() in Qiskit.
- **Backend Mismatches**: Replacing cloud-based backends with local simulators (e.g., LocalSimulator for Braket, WavefunctionSimulator for PyQuil).
- **Measurement Convention Errors**: Manually normalizing PennyLane's \[+1, -1\] eigenvalue

results to Qiskit's \[0, 1\] bit format.

- **Data Format Differences**: Converting the output of Amazon Braket's measurement array into standard bitstrings for comparison.
