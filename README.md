# Entanglement Entropy in Kicked Ising Chains

A numerical study of entanglement entropy dynamics and Hilbert space fragmentation in periodically driven (Floquet) transverse-field Ising chains with periodic boundary conditions.

## Overview

This repository contains numerical simulations exploring the violation of the Eigenstate Thermalization Hypothesis (ETH) and prethermal Hilbert space fragmentation in a kicked Ising model. The code demonstrates how certain periodic driving protocols can lead to entanglement entropy that saturates below the thermal Page value, indicating non-ergodic behavior and fragmentation of the quantum Hilbert space.

## Physical System

The model studies a **kicked transverse-field Ising chain** of length $L$ with periodic boundary conditions (PBC):

$$H(t) = H_0(t) + H_1$$

where:
- $H_0(t) = -J(t)\sum_{i=1}^{L}\sigma_i^z\sigma_{i+1}^z - h(t)\sum_{i=1}^{L}\sigma_i^z$ (time-dependent Ising interactions)
- $H_1 = -g\sum_{i=1}^{L}\sigma_i^x$ (weak transverse perturbation with $|g| \ll \{|J_0|, |h_0|\}$)
- $\sigma_{L+1}^z \equiv \sigma_1^z$ (periodic boundary conditions)

The couplings $J(t)$ and $h(t)$ are periodically modulated, creating a Floquet system with discrete time-translation symmetry.

## Key Features

### 1. **Entanglement Entropy Dynamics**
- Computes bipartite entanglement entropy for subsystems
- Compares time-evolved entanglement against the Page value (thermal/ETH prediction)
- Demonstrates saturation below thermal values at specific resonant periods $T = n\pi/J_0$

### 2. **Hilbert Space Fragmentation Analysis**
- Constructs and analyzes connectivity graphs of quantum states
- Identifies fragmented sectors that cannot thermalize
- Computes fragment-specific Page values using Monte Carlo sampling
- Shows how fragmentation leads to reduced entanglement entropy

### 3. **Parameter Dependence Studies**
- Variation of entanglement entropy with coupling strength $J_0$
- Analysis across different fragment structures
- Exploration of the prethermal regime

## Requirements

The code is implemented as a Jupyter notebook designed to run in Google Colab or any Jupyter environment with the following dependencies:

```python
numpy
scipy
matplotlib
quspin  # Quantum spin dynamics package
```

## Installation & Usage

### Option 1: Google Colab (Recommended)
Click the badge below to open directly in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Knerdy-got-moves/Entanglement-entropy-in-Ising-chains/blob/main/Periodic_Frag_and_EE_kicked_Ising_chain.ipynb)

The notebook will automatically install QuSpin when run.

### Option 2: Local Installation

```bash
# Clone the repository
git clone https://github.com/Knerdy-got-moves/Entanglement-entropy-in-Ising-chains.git
cd Entanglement-entropy-in-Ising-chains

# Install dependencies
pip install numpy scipy matplotlib quspin

# Launch Jupyter
jupyter notebook Periodic_Frag_and_EE_kicked_Ising_chain.ipynb
```

## Notebook Structure

The notebook is organized into the following sections:

1. **Model Definition**: Mathematical description of the kicked Ising Hamiltonian
2. **Hamiltonian Construction**: Building the Floquet operator with periodic boundary conditions
3. **Time Evolution**: Computing $U(T) = e^{-iH_-T/2}e^{-iH_+T/2}$ for one period
4. **Random State Generation**: Haar-random pure states from the Hilbert space
5. **Entanglement Entropy Calculation**: Bipartite entanglement via reduced density matrices
6. **ETH Violation**: Demonstrating saturation below the Page value
7. **Fragmentation Analysis**:
   - Constructing the $\mathcal{O}$ operator
   - Finding connectivity graphs
   - Identifying largest fragments
   - Fragment-specific Page values
8. **Results & Visualization**: Plots of entanglement entropy vs. time, parameters, and fragments

## Key Results

The simulations demonstrate:

- **ETH Violation**: At resonant periods $T = n\pi/J_0$, entanglement entropy saturates below the thermal Page value
- **Prethermal Fragmentation**: The Hilbert space breaks into disconnected fragments that cannot thermalize on intermediate timescales
- **Reduced Thermalization**: States within fragments can only thermalize to fragment-specific ensemble values, not the full thermal ensemble

## Physical Interpretation

This work connects to several important concepts in quantum many-body physics:

- **Eigenstate Thermalization Hypothesis (ETH)**: Generic isolated quantum systems thermalize internally
- **ETH Violation**: Certain integrable or many-body localized systems fail to thermalize
- **Floquet Systems**: Periodically driven quantum systems with emergent behavior
- **Hilbert Space Fragmentation**: Dynamical constraints that partition the state space
- **Prethermal Regime**: Long-lived non-thermal states before eventual thermalization

## References

### Eigenstate Thermalization Hypothesis
1. J. M. Deutsch, "Quantum statistical mechanics in a closed system," [Phys. Rev. A 43, 2046 (1991)](https://doi.org/10.1103/PhysRevA.43.2046)
2. M. Srednicki, "Chaos and quantum thermalization," [Phys. Rev. E 50, 888 (1994)](https://doi.org/10.1103/PhysRevE.50.888)
3. M. Rigol, V. Dunjko, and M. Olshanii, "Thermalization and its mechanism for generic isolated quantum systems," [Nature 452, 854 (2008)](https://doi.org/10.1038/nature06838)

### Page Entropy
4. D. N. Page, "Average entropy of a subsystem," [Phys. Rev. Lett. 71, 1291 (1993)](https://doi.org/10.1103/PhysRevLett.71.1291)

### Floquet Systems & Fragmentation

5. P. Sala et al., "Ergodicity Breaking Arising from Hilbert Space Fragmentation in Dipole-Conserving Hamiltonians," [Phys. Rev. X 10, 011047 (2020)](https://doi.org/10.1103/PhysRevX.10.011047)
6. V. Khemani, M. Hermele, and R. Nandkishore, "Localization from Hilbert space shattering: From theory to physical realizations," [Phys. Rev. B 101, 174204 (2020)](https://doi.org/10.1103/PhysRevB.101.174204)
7. S. Ghosh, I. Paul, and K. Sengupta, "Prethermal Fragmentation in a Periodically Driven Fermionic Chain," [Phys. Rev. Lett. 130, 120401 (2023)](https://doi.org/10.1103/PhysRevLett.130.120401)



### QuSpin Package
8. P. Weinberg and M. Bukov, "QuSpin: a Python package for dynamics and exact diagonalization of quantum many body systems," [SciPost Phys. 2, 003 (2017)](https://doi.org/10.21468/SciPostPhys.2.1.003)

## Contributing

Contributions, suggestions, and discussions are welcome! Feel free to open issues or submit pull requests.

## License

This project is open source. Please cite appropriately if you use this code in your research.

## Author

Created for research and educational purposes in quantum many-body physics and quantum information theory.

---

**Keywords**: Floquet systems, Ising model, entanglement entropy, ETH violation, Hilbert space fragmentation, quantum thermalization, periodic driving, QuSpin, numerical simulation
