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
All data obtained from python scripts are saved in .npy files. Each .npy files has the time evolution of fibril mass for wide range of discrete point concentration mostly between 0.6µM to 500µM. Here, we describe how we name the different .npy files.  
1) default_LLPS.npy represents the simulation obtained from the defaults parameter listed in the main text Table 1.
2) default_w/oLLPS.npy represents the simulation obtained from the default parameter listed in the main text Table 1 but not considering droplet phase.
3) nd8.npy, nd10.npy, and nd15.npy represent the simulation obtained from default parameter but varying only critical droplet size n<sub>d</sub>.
4) binodal20.npy, binodal40.npy, binodal80.npy represent the simulation obtained by varying binodal concentration φ<sub>BN</sub>.

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

