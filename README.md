# Potassium Channel Characterization in Starburst Amacrine Cells

## Background
The perception of sight begins at the back of the eye in a layer of neurons called the retina. Within the retina, light-sensing neurons known as rods and cones convert photons of light into electrical signals. Starburst Amacrine Cells (SACs) are a special type of neuron located downstream of the rods and cones. They get their name from their highly branched, starburst like morphology, which is visible in the accompanying image of a SAC labeled with fluorescent dye. These cells are known to play a crucial role in direction selectivity, which is the retinas ability to respond preferentially to motion in specific directions. Direction selectivity is an essential aspect of perceiving motion. 

Neurons generate and transmit electrical signals through the controlled movement of ions, such as potassium, across their membranes. This movement occurs through specialized proteins called ion channels and produces measurable electric currents. Whole-cell electrophysiology is a technique used to study these currents by gently inserting a glass electrode into the neuron to record its electrical activity.

This project focused on studying the potassium channels found in SACs using the whole-cell electrophysiology technique. Experiments were designed to specifically isolate, record, and manipulate potassium currents, with the goal of identifying and characterizing the types of potassium channels involved in direction selectivity.

![amacrine1](https://github.com/user-attachments/assets/112e4e5f-688b-4adb-a3ca-611b574c1806)

## Language
- Python
  - [pandas](https://pandas.pydata.org/)
  - [h5py](https://pypi.org/project/h5py/)
  - [SciPy](https://scipy.org/)
  - [Seaborn](https://seaborn.pydata.org/)
  - [Matplotlib](https://matplotlib.org/)

## Data 
Time-series electrical recordings of potassium currents were collected using whole-cell electrophysiology and saved in HDF5 format. Each HDF5 file contains multiple sweeps, with each sweep representing the cell’s response at a specific holding voltage.

Recordings were sampled at 10 kHz (10,000 samples per second). The measured current values are in picoamperes (pA), and the applied voltages are in millivolts (mV).

To prepare the data for analysis, each sweep must be zero-baseline normalized to remove the initial offset and ensure consistency across recordings.

## Versions
- PotassiumCurrentStepAnalysisClass20250312.ipynb is the most complete analysis and is to be used in Poleg-Polsky Lab's Google Colab space.

- The final working version is comprised of four classes.
  - **PotassiumCurrentStepsImport**, imports the HDF5 file, normalizes the baseline, optionally subracts out the capacitive   current, and returns the data as a normalized NumPy array.
  - **SustainedPotassiumCurrentStepAnalysis**, analyses the sustained peak current by voltage step for multiple trials, calculates the mean and the standard error of the mean (SEM), and plots the result.
  - **TransientPotassiumCurrentStepAnalysis**, analyses the transient peak current by voltage step for multiple trials, calculates  the mean and the SEM, and plots the result.
  - **CurrentDecayStepAnalysis**, measures the exponential decay time of the transient current for multiple trials, calculates the mean and the SEM, and plots the result.


## Experimental Conditions
- Starburst Amacrine Cells in Chat-Cre/tdTomato mice were targeted for whole cell recording.
- For grna experiments and expeiments with bath application of drugs internal solution consisted of, 110 mM KMeS04H, 10 mM NaCl, 5 mM HEPES, 2 mM EGTA, 10 mM CrPhos, 4 mM Mg-ATP, and 0.4 mM Na-GTP was used.
- Cells were held in voltage clamp at -80mV and sustained and transient currents were recorded as voltage steps of (-110, -100, -90, -80, -70, -60, -50, -40, -30, -20) were applied.
- For experiments involving pharmacology, control currents were first recorded then drug was applied for approximately 20 minuets and the evoked currents were again recorded.
- As an added control, at the end of each experiment cells were held in current clamp and a series of depolarizing steps were applied to ensure cell did not fire action potentials.

<img width="936" height="489" alt="NormalizedTrace20241113_0" src="https://github.com/user-attachments/assets/6e9ace85-7f8c-41b6-805f-afa543ce359f" />

*Figure: Example of a single experiment after applying Class PotassiumCurrentStepsImport with capacitive current subtraction.*

## Results
<img width="669" height="485" alt="VoltageStepSustainedCurrentGRNA" src="https://github.com/user-attachments/assets/2c545dcc-0c7f-4064-b6e3-ec6603573c71" />

*Figure: Example of an experimental condition after applying Class SustainedPotassiumCurrentStepAnalysis.*

<img width="669" height="485" alt="VoltageStepTransientCurrentGRNA" src="https://github.com/user-attachments/assets/299174f1-4503-475f-83a0-be8b3d3282f8" />
*Figure: Example of an experimental condition after applying Class TransientPotassiumCurrentStepAnalysis.*

<img width="669" height="485" alt="VoltageStepCurrentDecayTimeGRNA" src="https://github.com/user-attachments/assets/9de8be57-cf70-4bee-a5f8-b9b1deb16588" />
*Figure: Example of an experimental condition after applying Class CurrentDecayStepAnalysis.*
