# Power System Fault Location with Machine Learning

An IEEE 39-bus transmission-network study comparing impedance-based fault location with machine learning and hybrid residual correction. The research also considers an inverter-based renewable-generation scenario.

## What it does

- Simulates transmission-line faults and analyzes voltage/current measurements at both line terminals.
- Extracts phasors and symmetrical-component features.
- Compares Artificial Neural Networks, Support Vector Machines and Random Forests.
- Studies fault classification, distance estimation, measurement noise and hybrid correction.

## Workflow

![Data preparation and evaluation workflow](docs/workflow.png)

## Results

The following results are reported in the [technical thesis](docs/fault-location-thesis.pdf) for the main 21,317-case dataset.

| Method | Distance MAE (% of line length) | Fault-classification accuracy (%) |
| --- | ---: | ---: |
| Conventional impedance | 3.018 | - |
| ANN | 0.976 | 99.099 |
| Random Forest | 0.664 | 98.274 |
| SVM | 3.247 | 98.494 |

![Standalone fault-location results from the thesis](docs/standalone-comparison.png)

The thesis also presents renewable-generation experiments and physics-informed residual learning.

## Tools

MATLAB R2024a, Simulink and Simscape Electrical Specialized Power Systems for the network model. The research workflow uses Python, scikit-learn and Matplotlib, with Spyder and Anaconda as development tools.

## Explore the project

Open MATLAB in this repository and run:

```matlab
cd simulation
ieee39_network_parameters
open_system('ieee39_fault_location.slx')
```

The model's preload callback initializes the network parameters and stabilizer flags. Inspect the fault blocks and scopes to explore network behavior.

Read the thesis for the methodology and experiments, and open the [feature sample](data/fault-feature-sample.csv) to explore the measurement format. The sample contains 110 simulation cases.

## Project files

| File | Purpose |
| --- | --- |
| `simulation/ieee39_network_parameters.m` | Network, machine and controller parameters |
| `simulation/ieee39_fault_location.slx` | IEEE 39-bus network model |
| [Technical thesis](docs/fault-location-thesis.pdf) | Methodology, experiments and results |
| [Feature sample](data/fault-feature-sample.csv) | Example measurement and target columns |
| [Data guide](docs/data-guide.md) | Column descriptions |
| [Dataset summary](data/dataset-summary.json) | Dataset and fault-class overview |

Developed as a collaborative academic engineering project.
