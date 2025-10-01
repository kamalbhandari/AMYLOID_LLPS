# Introduction
Protein aggregation into amyloid fibrils is a hallmark of numerous neurodegenerative diseases and systematic diseases. Many amyloid protein undergo liquid-liquid phase separation, forming protein-rich condensates before fibrilization. However, the role of LLPS in modulation amyloid aggregation remains unclear due to conflicting reports of promotion, inhibition, and biphasic effects.

In this project, we develop an integrated thermodynamics-kinetics model that incorporates LLPS-induced heterogeneity to analyze amyloid aggregation pathways. The model captures the time evolution of monomers, droplets, oligomers, and fibrils under varying conditions, including the presence of salt. Using this framework, we systematically investigate how key parameters affect aggregation kinetics and provide insights into the complex interplay betyween LLPS and amyloid fibril formation.

# Repository Overview  
This repository contains python scripts for modeling the kinetics of amyloid aggregation.

# Repository structure  
* /Data/ - Contains all .npy files used to produce plots.
* /Python script/ - Contains all python source codes files.
  
# Data directory  
This folder contains .npy files generated from our python simulations. Each file stores the time evolution of fibril mass at multiple discrete point concentrations (typically between 0.6µM to 500µM). These datasets support the figures presented in the main text and supplementary information. These data are available at Zenodo:(https://doi.org/10.5281/zenodo.15499212). 

# Python script directory  
### simulate_kinetics_0.py  
Simulates and plots the time evolution of monomers, droplets, oligomers, and fibrils concentration for a given single total protein concentration. Print out the concentration of monomers, droplet mass, oligomer mass and fibril mass. Saves the time evolution of fibril mass in .npy files.
### simulate_kinetics.py  
Simulates and plots the time evolution of monomers, droplets, oligomers, and fibrils concentration for a set of discrete point protein concentration. Saves the time evolution of fibril mass in .npy files.
### simulate_kinetics_salt.py  
Simulates and plots the time evolution of monomers, droplets, oligomers, and fibril concentration for a given set of protein concentration points under varying salt concentrations. Saves the time evolution of fibril mass in .npy files.
### simulate_kinetics_oligomer.py 
Simulates and plots the time evolution of monomers, droplets, oligomers, and fibril concentration for a given set of protein concentration points under the assumption of LLPS driven by oligomers, instead of monomers. Saves the time evolution of fibril mass in .npy files.
### analyze_kinetics.py  
Plots half-time, lag-time, fibril aggregation rate, and time evolution of fibril mass fraction as a function of concentration. It supports .npy data files representing fibril mass over time across various concentrations. Users may: either use the precomputed data provided on Zenodo or generate new datasets using simulate_kinetics.py and then analyze them with this script.
