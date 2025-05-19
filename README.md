# Introduction
Protein aggregation into amyloid fibrils is a hallmark of numerous neurodegenerative diseases and systematic diseases. Many amyloid protein undergo liquid-liquid phase separation, forming protein-rich condensates before fibrilization. However, the role of LLPS in modulation amyloid aggregation remains unclear due to conflicting reports of promotion, inhibition, and biphasic effects.

In this project, we develop an integrated thermodynamics-kinetics model that incorporates LLPS-induced heterogeneity to analyze amyloid aggregation pathways. The model captures the time evolution of monomers, droplets, oligomers, and fibrils under varying conditions, including the presence of salt. Using this framework, we systematically investigate how key parameters affect aggregation kinetics and provide insights into the complex interplay betyween LLPS and amyloid fibril formation.

# Repository Overview  
This repository contains python scripts for modeling the kinetics of amyloid aggregation. All simulation results are saved for reproducibilty, and final figures are consolidated into a single pdf for convenience.

# Repository structure  
* /data/ - Contains all .npy files used to produce plots.
* /figures/ - Contains all figures in pdf.
* /codes/ - Contains all python source codes files.
# Python scripts  
### simulate_kinetics.py  
Simulates and plots the time evolution of monomers, droplets, oligomers, and fibrils concentration. Saves the fibril mass and the corresponding time in .npy files.
### simulate_kinetics_salt.py  
Simulates and plots the time evolution of monomers, droplets, oligomers, and fibril concentration under varying salt concentrations.  
### analyze_kinetics.py  
Plots half-time, lag-time, fibril aggregation rate, and time evolution of fibril mass fraction as a function of concentration.

