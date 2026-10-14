# Dataset Guide

## Dataset and sample

The sample is selected from `core_ml_dataset_cv5_within_line.csv`, which contains 21,317 rows and 310 columns across 34 line pairs. The accompanying dataset summary reports three failed cases. The dataset summary counts 309 features in the initial table; the final models use a selected 289-feature electrical-core vector.

The sample retains all columns except `folder_path`, `folder_name` and `run_index`, leaving 307 columns. It takes the first two rows in source order for each of 11 fault classes and five fold labels: 110 rows total. 

## Column families

- `fault_type`: classification target. A/B/C denote phases; G denotes ground. Included classes are AB, ABC, ABCG, ABG, AC, ACG, AG, BC, BCG, BG and CG.
- `true_distance_fraction`: regression target, fault distance divided by line length.
- `true_distance_km`: physical distance target.
- `from_bus`, `to_bus`: modeled line identifiers.
- `line_total_length_km`: line length, also usable to convert normalized error to kilometres.
- `fault_resistance_ohm`: fault resistance used in the simulation.
- `cv_fold`: stored cross-validation fold assignment.
- `send_*`, `recv_*`: sending-/receiving-terminal electrical descriptors.
- `v`, `i`: voltage and current families; `pre`, `post`, `delta`: pre-fault, post-fault and incremental quantities.
- `_re`, `_im`, `_mag`, `_ang_deg`: real, imaginary, magnitude and angle components. Further sequence and ratio columns are present.

The final electrical-core inputs are selected separately from the target, fold and case-identification columns.

## Storage

The complete dataset is about 129 MB. The CSV in this repository is a 110-case sample for exploring the measurement and target columns.
