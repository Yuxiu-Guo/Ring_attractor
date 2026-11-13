# Neuronal Nonlinearity and Connectivity Tuning in Finite Ring Attractors

### Overview

This project investigates how neuronal input–output nonlinearities affect the existence, stability, and performance of approximately continuous attractors in small recurrent neural networks.

Building on the finite ring-attractor framework of Noorman et al. (2024), we examine how different neuronal response functions influence phase drift and sensitivity to connectivity perturbations.

The analysis focuses on a network of **N = 6 neurons**, comparing:

- Threshold-linear (ReLU) response
- Sigmoid response
- Softplus response with varying sharpness parameters (β)

### Research Questions

1. How do different nonlinear response functions affect stationary bump solutions and their local stability?
2. Does local phase marginality guarantee accurate continuous ring attractor representations?
3. How sensitive is orientation memory performance to perturbations in excitatory and inhibitory connectivity?
4. How does neuronal nonlinearity influence the relationship between connectivity tuning precision and memory performance?

### Model

We consider the recurrent network:
\[
\tau \frac{dh_j}{dt}
=
-h_j+c_{\mathrm{ff}}
+\frac{1}{N}\sum_k
\left[J_I+J_E\cos(\theta_j-\theta_k)\right]\phi(h_k).
\]
Here, \(J_E\) and \(J_I\) control tuned excitation and uniform inhibition, respectively, while \(\phi\) represents the neuronal response function.

### Numerical Analysis
The current implementation includes:

- **Fixed-point analysis:** Solving for stationary bump profiles and connectivity parameters along a preferred-orientation phase-marginality branch.
- **Stability analysis:** Computing local eigenvalues at preferred and midpoint orientations.
- **Phase-drift simulations:** Evaluating deterministic orientation drift from different initial conditions without velocity input.
- **Connectivity perturbations:** Independently varying \(J_E\) and \(J_I\) to characterize finite-time memory error and low-drift regions.
- **Nonlinearity comparisons:** Exploring sigmoid and softplus response functions under common simulation protocols.

### Repository Contents

- `ra_utilities.py` — Ring-attractor simulation utilities.
- `data/` — Numerical results, including stationary solutions and phase-drift performance.
- `figs/` — Visualizations of neuronal response functions, phase trajectories, and connectivity-tuning landscapes.
- And two ipynb notebooks which I will keep modify and enrich upon.
- 
### Current Status

**Work in progress.** The current results provide an exploratory numerical characterization of how neuronal nonlinearities influence local marginality, phase drift, and connectivity sensitivity in finite networks.

Further analysis aims to clarify the dynamical mechanisms underlying these observations, particularly the roles of phase pinning, nonlinear response structure, and bump-profile stability.

### Acknowledgments and Code Attribution

The ring-attractor simulation utilities in `ra_utilities.py` were provided by Kylie from the Redwood Center for Theoretical Neuroscience at UC Berkeley and are based on the network model introduced by Noorman et al. (2024).

### Reference

Noorman, M., et al. (2024). *Maintaining and updating accurate internal representations of continuous variables with a handful of neurons.* Nature Neuroscience.

https://doi.org/10.1038/s41593-024-01766-5
