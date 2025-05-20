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
1. default_LLPS.npy →  Simulation using the defaults parameter listed in Table 1 ( main text), including LLPS effects.
2. default_w/oLLPS.npy → Same as 1, but without droplet phase (LLPS) included.
3. nd8.npy, nd10.npy, nd15.npy → Simulations with different droplet nucleation size n<sub>d</sub>.
4. binodal20.npy, binodal40.npy, binodal80.npy → Simulations with varying binodal concentration φ<sub>BN</sub>.
5. nf3.npy, nf5.npy → Simulations with different fibril nucleation size n<sub>f</sub>.
6. w/oLLPS_nf3.npy, w/oLLPS_nf5.npy → Same as 5, but without droplet phase (LLPS) included.
7. crowder.npy →  Simulation including the presence of molecular crowders.
8. sequester.npy → Simulation including sequestering agents.
9. cocondensate0.1.npy, cocondensate1.npy, cocondensate10.npy → Simulations with co-condenates in droplets, with the coefficient σ = 0.1, 1 and 10 repectively.
10. salt0.25.npy, salt0.5.npy, salt0.75.npy, salt1.npy → Simulations including salt concentration of 0.25M, 0.5M,0.75M, and 1M repectively.
11. sigma0.1.npy, sigma10.npy →  Simulations with varying the coefficient σ.
12. Ca_d3.npy, Ca_d1_3.npy → Simulations with different value of coefficient Ca/d.
13. Ca3.npy, Ca1/3.npy → Simulations with varying values of Ca.
14. deltaGf2.npy, deltaGf5.npy, deltaGf7.npy, delataGf10.npy →  Simulations with varying fragmentation free energy coefficient ΔG<sub>f</sub>.
15. deltaGs1.npy, deltaGs2.npy, deltaGs3.npy, delataGs5.npy → Simulations with varying secondary nucleation free energy coefficient ΔG<sub>s</sub>.
16. ddGminus4.6.npy, ddGplus4.6.npy → Simulations varying the difference between ΔG<sub>HD</sub> and ΔG<sub>LD</sub>.
17. ddG0dGminus2.npy, ddG0dGminus2.npy → Simulations varying both  ΔG<sub>HD</sub> and ΔG<sub>LD</sub> equally.
    
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

