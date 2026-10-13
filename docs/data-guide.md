# Dataset Guide

## Source and scope

The sample is selected from `core_ml_dataset_cv5_within_line.csv`, which contains 21,317 rows and 310 columns across 34 line pairs. The accompanying dataset summary reports three failed cases. Its `feature_count` value of 309 describes the earlier supplied table and must not be equated with the thesis's final 289-input electrical-core vector.

The sample retains all columns except `folder_path`, `folder_name` and `run_index`, leaving 307 columns. It takes the first two rows in source order for each of 11 fault classes and five fold labels: 110 rows total. This deterministic sample is not representative of the full distance, resistance or line distributions.

## Column families

- `fault_type`: classification target. A/B/C denote phases; G denotes ground. Included classes are AB, ABC, ABCG, ABG, AC, ACG, AG, BC, BCG, BG and CG.
- `true_distance_fraction`: regression target, fault distance divided by line length.
- `true_distance_km`: physical distance target.
- `from_bus`, `to_bus`: modeled line identifiers.
- `line_total_length_km`: line length, also usable to convert normalized error to kilometres.
- `fault_resistance_ohm`: known simulation condition, not automatically an available field measurement.
- `cv_fold`: original stored fold assignment, not a predictor.
- `send_*`, `recv_*`: sending-/receiving-terminal electrical descriptors.
- `v`, `i`: voltage and current families; `pre`, `post`, `delta`: pre-fault, post-fault and incremental quantities.
- `_re`, `_im`, `_mag`, `_ang_deg`: real, imaginary, magnitude and angle components. Further sequence and ratio columns are present.

Do not infer a complete final-model feature list by treating all numerical columns as inputs. Recover the original feature-selection code before retraining. Targets, fold labels and identifiers can otherwise introduce leakage.

## Storage

The full source CSV is about 129 MB and is excluded, together with its duplicate/derived variants and raw simulation recordings. The public sample contains no local filesystem paths. The original full data remain untouched in the user's source location.
