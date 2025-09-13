# Silvaco_mosfet_designs 
Project Title:

Silvaco TCAD MOSFET Simulation Suite

Overview:

This repository contains a set of Silvaco TCAD input files (.in) for simulating various MOSFET devices. The simulations are performed using the ATLAS device simulator, and the results are visualized with TonyPlot. The primary objective is to analyze the electrical characteristics (e.g., I-V curves) of different transistor types, including Fully Depleted Silicon-on-Insulator (FDSOI), Partially Depleted Silicon-on-Insulator (PDSOI), and conventional bulk MOSFETs with different gate dielectrics (SiO2 and HfO2).

Prerequisites:

To run these simulations, you need to have a working installation of Silvaco TCAD, including the DeckBuild, ATLAS, and TonyPlot modules. These tools are used for running the simulation scripts and visualizing the output data.

File Descriptions:

FDSOI.in: This file simulates a Fully Depleted Silicon-on-Insulator (FDSOI) MOSFET. The code defines the device geometry with an oxide layer (SiO2) acting as a buried oxide (BOX) layer and a very thin silicon body. The simulation sweeps the gate voltage (vgate) from -0.2 V to 1 V for four different drain voltage (vdrain) settings: 0.5 V, 0.2 V, 0.8 V, and 1 V. The output logs (drain_volatge_0.1.log, etc.) contain the drain current vs. gate voltage data.

PDSOI.in: This file simulates a Partially Depleted Silicon-on-Insulator (PDSOI) MOSFET. It is similar to the FDSOI file but includes an additional silicon region (region number=13) at the bottom of the device, which represents a partially depleted body. The simulation and output logging setup are identical to the FDSOI.in file.

HFO2_90MOSFET.in: This file simulates a conventional bulk MOSFET (no buried oxide). The key difference from the other files is the use of Hafnium Dioxide (HFO2) as the gate dielectric material. The simulation sweeps the gate voltage from 0 V to 1 V at a fixed drain voltage of 0.5 V, and the results are saved to mosfet90.log.

90_mosfet.in: This file simulates a conventional bulk MOSFET with Silicon Dioxide (SiO2) as the gate dielectric. It follows a similar structure to the HFO2_90MOSFET.in file, but the dielectric material is defined as SiO2. The simulation and logging setup are the same.

How to Run the Simulations:

1.Open the DeckBuild environment.

2.Go to File > Empty Document to clear the text window.

3.Load one of the .in files (e.g., FDSOI.in) into DeckBuild.

4.Click the "Run" button to execute the simulation. The simulation will run and save the specified output log files in the same directory.

5.After the simulation is complete, the tonyplot command at the end of the script will automatically launch TonyPlot to visualize the results. For example, tonyplot -overlay drain_volatge_0.1.log drain_volatge_0.2.log drain_volatge_0.3.log drain_volatge_0.4.log will plot all four I-V curves on a single graph.

Analysis of Results:

The simulation files are configured to produce Id-Vg (drain current vs. gate voltage) curves. 
The output log files can be opened in TonyPlot to analyse key device parameters such as:

1.Threshold Voltage (V th): The gate voltage at which the device begins to conduct.

2.Subthreshold Swing (SS): The gate voltage required to change the drain current by one decade in the subthreshold region.

3.On/Off Current Ratio (I on /I off): The ratio of the drain current in the "on" state to the "off" state.

The tonyplot commands at the end of each script provide a convenient way to visualize these characteristics, and the -overlay flag is particularly useful for comparing the performance of the same device under different bias conditions. The structure files (.str) can also be viewed in TonyPlot to see the device geometry and internal physical quantities.
