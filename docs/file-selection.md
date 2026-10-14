# Project Files

## Network model

`simulation/ieee39_network_parameters.m` defines the network, machine and controller parameters. `simulation/ieee39_fault_location.slx` contains the IEEE 39-bus model. The preload callback initialises the parameters when the model opens.

The model uses MATLAB R2024a and Simscape Electrical Specialized Power Systems.

## Research report

`docs/fault-location-thesis.pdf` describes the impedance-based method, machine-learning models, measurement-noise study and renewable-generation scenarios. It also contains the final comparison tables and annexes.

The workflow diagram and comparison figures provide an overview of the methodology and results.

## Dataset

`data/fault-feature-sample.csv` contains 110 example cases. `data/dataset-summary.json` gives the full dataset counts, and `docs/data-guide.md` explains the columns and sample selection.
