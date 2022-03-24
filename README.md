# QuantumChemistryQiskit
Tutorials of Quantum Chemistry in Quantum Computers using Qiskit


## Fundamentals 

[Qiskit](https://github.com/Qiskit/qiskit.git) implements several application modules for different purposes. In this case, since we are going to be interested in Quantum Chemisty we are going to work with the module [Qiskit_Nature](https://github.com/Qiskit/qiskit-nature.git)

Qiskit Nature works with several implementations for typical Quantum Chemistry applications and requires a classic SCF (Self Consistent Field) driver to produce the inputs for the Quantum Computers.
Briefly, the main implementations can be divided into:
1. Thermodynamics: To get the vibrational spectrum
2. Vibrational Spectrum Calculation
    2.1 UVCC VS
    2.2 Analytical VS
3. BOPES Sampler: To explore ground state or excited state potential energy surfaces
4. Excited State Calculations
    2.1 ES-ESC (Quantum Eigensolver)
    2.2 QEOM (Quantum Equation of Motion Implementation)
5. Ground State Calculations
    5.1 Minumum Eigenvalue GSC
    5.2 OOVQE
    5.3 VQEAdapt

The general structure of Qiskit Nature is splitting any of the applications in:
Problem > Solver > Result
Or in terms of code
```
result = solver.solve(problem)
```
Any of the problems follows this flow:
1. Use of an Electronic Structure Driver (Classic)
2. Gets a group of electronic properties of the molecule
3. Do a base transformation
4. Give back the second quantization operators in terms of femionic operators 

Once we have the fermionic operators we just need to transform those into Qbits with a mapper, use qbit operators and go trough any of the quantum algorithms stated above

All the documentation refered to all the details of the methods and algorithms can be found in IBM Qiskit Nature [Documentation](https://qiskit.org/documentation/nature/index.html)