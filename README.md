# Potassium Channel Characterization in Starburst Amacrine Cells

## Background
The perception of sight begins at the back of the eye in a layer of neurons called the retina. Within the retina, light-sensing neurons known as rods and cones convert photons of light into electrical signals. Starburst Amacrine Cells (SACs) are a special type of neuron located downstream of the rods and cones. They get their name from their highly branched, starburst like morphology, which is visible in the accompanying image of a SAC labeled with fluorescent dye. These cells are known to play a crucial role in direction selectivity, which is the retinas ability to respond preferentially to motion in specific directions. Direction selectivity is an essential aspect of perceiving motion. 

Neurons generate and transmit electrical signals through the controlled movement of ions, such as potassium, across their membranes. This movement occurs through specialized proteins called ion channels and produces measurable electric currents. Whole-cell electrophysiology is a technique used to study these currents by gently inserting a glass electrode into the neuron to record its electrical activity.

This project focused on studying the potassium channels found in SACs using the whole-cell electrophysiology technique. Experiments were designed to specifically isolate, record, and manipulate potassium currents, with the goal of identifying and characterizing the types of potassium channels involved in direction selectivity.

![amacrine1](https://github.com/user-attachments/assets/112e4e5f-688b-4adb-a3ca-611b574c1806)

## Language
- Python
  - [pandas](https://pandas.pydata.org/)
  - [SciPy](https://scipy.org/)
  - [Seaborn](https://seaborn.pydata.org/)
  - [Matplotlib](https://matplotlib.org/)

## Data 
Time-series electrical recordings of potassium currents were collected using whole-cell electrophysiology and saved in HDF5 format. Each HDF5 file contains multiple sweeps, with each sweep representing the cell’s response at a specific holding voltage.

Recordings were sampled at 10 kHz (10,000 samples per second). The measured current values are in picoamperes (pA), and the applied voltages are in millivolts (mV).

To prepare the data for analysis, each sweep must be zero-baseline normalized to remove the initial offset and ensure consistency across recordings.
