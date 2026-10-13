# File Selection and Reproduction Status

## Included

- The supplied MATLAB network-parameter script and Simulink model, renamed descriptively with the preload callback and saved diagram paths updated. Creator/editor metadata was removed; numerical parameters and model dynamics were preserved.

- Anonymous thesis: one replacement cover, the abstract, and the original technical contents through the annexes. Original printed page numbers and scholarly references are retained.
- Two figures taken from the thesis for navigation and context.
- A small, deterministic feature-table sample, its selection description, and the original aggregate dataset counts.

## Excluded

- Raw simulation runs in the dataset folders and large full/derived CSV tables.
- Temporary files, failed-run logs, tuning retries, duplicate results and smoke-test output.
- Serialized `.pkl` and `.keras` models. The inspected ANN has 298 inputs, whereas the thesis describes a final 289-input configuration; it cannot be labelled the final thesis model. No serialized model was loaded or executed.
- Experimental result summaries, including nearby ANN/SVM/RF summaries, whose scores do not match the final thesis tables.
- Personal title pages, dedications, acknowledgements and hidden PDF metadata.

## Needed for a reproducible code repository

1. MATLAB fault-sweep automation and data-export functions used for the thesis experiments.
2. Python feature-extraction, fold-assignment, preprocessing, training and evaluation scripts for the final experiments.
3. The final 289-feature selection and the renewable 27-feature residual-learning pipeline.
4. Tested runtime versions, data-generation instructions and a small reproducible execution case.

The supplied model was saved in R2024a and references Simscape Electrical Specialized Power Systems libraries. Its preload callback now points to the included parameter script. Static archive/XML checks passed, but no simulation has been validated. The retained model alone has not been established as the complete setup for every thesis scenario. No replacement training implementation has been invented.
