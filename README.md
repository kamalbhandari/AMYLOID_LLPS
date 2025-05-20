# Introduction
Protein aggregation into amyloid fibrils is a hallmark of numerous neurodegenerative diseases and systematic diseases. Many amyloid protein undergo liquid-liquid phase separation, forming protein-rich condensates before fibrilization. However, the role of LLPS in modulation amyloid aggregation remains unclear due to conflicting reports of promotion, inhibition, and biphasic effects.

In this project, we develop an integrated thermodynamics-kinetics model that incorporates LLPS-induced heterogeneity to analyze amyloid aggregation pathways. The model captures the time evolution of monomers, droplets, oligomers, and fibrils under varying conditions, including the presence of salt. Using this framework, we systematically investigate how key parameters affect aggregation kinetics and provide insights into the complex interplay betyween LLPS and amyloid fibril formation.

# Repository Overview  
This repository contains python scripts for modeling the kinetics of amyloid aggregation. All simulation results are saved for reproducibilty, and final figures are consolidated into a single pdf for convenience.

# Repository structure  
* /Data/ - Contains all .npy files used to produce plots.
* /Figure/ - Contains all figures in pdf.
* /Python script/ - Contains all python source codes files.
# Data directory  
This folder contains .npy files generated from our python simulations. Each file stores the time evolution of fibril mass for a range of initial protein discrete point concentration (typically between 0.6µM to 500µM). Below is a summary of the naming conventions used for each file, along with the simulation condition it represents.
## File naming and description  
1. default_LLPS.npy →  Simulation using the defaults parameter listed in Table 1 ( main text), including LLPS effects (at concentrations: 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM, 500µM)
2. default_LLPS_24.npy →  Same as 1, but at concentrations: 0.02µM, 0.05µM, 0.08µM, 0.1µM, 0.3µM, 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM)
3. default_LLPS_salt.npy →  Same as 1, but at concentrations: 0.1µM, 0.2µM, 0.3µM, 0.4µM, 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM)
4. default_woLLPS.npy → Same as 1, but without droplet phase (LLPS) included.
5. nd8.npy, nd10.npy, nd12.npy → Simulations with different droplet nucleation size n<sub>d</sub> = 8, 10 and 12 respectively. (at concentrations: 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM)
6. binodal20.npy, binodal40.npy, binodal80.npy → Simulations with varying binodal concentration φ<sub>BN</sub> = 20µM, 40µM and 80µM respectively. (at concentrations: 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM)
7. nf3.npy, nf5.npy → Simulations with different fibril nucleation size n<sub>f</sub> = 3 and 5 respectively. (at concentrations: 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM)
8. woLLPS_nf3.npy, woLLPS_nf5.npy → Same as 5, but without droplet phase (LLPS) included. (at concentrations: 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM)
9. crowder.npy →  Simulation including the presence of molecular crowders. (at concentrations: 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM, 500µM)
10. sequester.npy → Simulation including sequestering agents. (at concentrations: 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM, 500µM)
11. cocondensate0.1.npy, cocondensate1.npy, cocondensate10.npy → Simulations with co-condenates in droplets, with the coefficient σ = 0.1, 1 and 10 repectively. (at concentrations: 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM, 500µM)
12. salt0.25.npy, salt0.5.npy, salt0.75.npy, salt1.npy → Simulations including salt concentration of 0.25M, 0.5M,0.75M, and 1M repectively. (at concentrations: 0.1µM, 0.2µM, 0.3µM, 0.4µM, 0.6µM, 0.8µM, 1µM, 2µM, 4µM, 8µM, 10µM, 20µM, 31µM, 40µM, 50µM, 60µM, 70µM, 80µM, 90µM, 100µM, 200µM, 300µM, 400µM)
13. sigma0.1.npy, sigma10.npy →  Simulations with varying the coefficient σ = 0.1 and 10 respectively.
14. Cad3.npy, Cad1_3.npy → Simulations with different value of coefficient Ca/d = 3 and 1/3 respectively.
15. Ca3.npy, Ca13.npy → Simulations with varying values of Ca = 3 and 1/3 respectively.
16. deltaGf2.npy, deltaGf5.npy, deltaGf7.npy, delataGf10.npy →  Simulations with varying fragmentation free energy coefficient ΔG<sub>f</sub> = 2KT, 5KT, 7KT, and 10KT respectively.
17. deltaGs1.npy, deltaGs2.npy, deltaGs3.npy, delataGs5.npy → Simulations with varying secondary nucleation free energy coefficient ΔG<sub>s</sub> = -1KT, -2KT, -3KT, and -5KT respectively.
18. ddGminus4.6.npy, ddGplus4.6.npy → Simulations varying the difference between ΔG<sub>HD</sub> and ΔG<sub>LD</sub> equal to -4.6KT and +4.6KT respectively.
19. ddG0dGminus2.npy, ddG0dGminus2.npy → Simulations varying both equally ΔG<sub>HD</sub> = ΔG<sub>LD</sub> = -2 KT or + 2KT.
20. woLLPS_dgldminus2.npy, woLLPS_dgldplus2.npy → Simulations
    
# Figure directory
This directory contains all figures associated with the main text and supplementary information (SI). Figures follow the naming convention:  
* FFF_FigX.pdf → corresponds to Figure X in the main text.
* FFF_FigSX.pdf → corresponds to Figure SX in  the SI.
* TOC.pdf → corresponds to Table of Content figure.
# Python script directory  
### simulate_kinetics_0.py  
Simulates and plots the time evolution of monomers, droplets, oligomers, and fibrils concentration for a given single total protein concentration. Print out the concentration of monomers, droplet mass, oligomer mass and fibril mass. Saves the time evolution of fibril mass in .npy files.
### simulate_kinetics.py  
Simulates and plots the time evolution of monomers, droplets, oligomers, and fibrils concentration for a set of discrete point protein concentration. Saves the time evolution of fibril mass in .npy files.
### simulate_kinetics_salt.py  
Simulates and plots the time evolution of monomers, droplets, oligomers, and fibril concentration for a given set of protein concentration points under varying salt concentrations. Saves the time evolution of fibril mass in .npy files.
### analyze_kinetics.py  
Plots half-time, lag-time, fibril aggregation rate, and time evolution of fibril mass fraction as a function of concentration.

