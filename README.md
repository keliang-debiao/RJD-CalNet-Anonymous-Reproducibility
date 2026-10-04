RJD-CalNet Anonymous Reproducibility Package
Package scope
This package contains the implementation, configuration files, data-preparation utilities, verification utilities, and tests for RJD-CalNet. Dataset archives, audio files, annotations, and prepared data tables are not included.
Repository contents
- rjd_calnet/ contains the Python source package.
  - models/ provides the tokenizer, expert modules, network, and prediction head.
  - data/ provides dataset handling, schema checks, grouped splits, and fold-specific preprocessing.
  - The remaining modules provide pipeline execution, training utilities, losses, metrics, calibration, ensemble aggregation, baseline workflows, robustness analyses, statistical analyses, and reporting utilities.
- configs/ contains YAML configuration files.
  - locked.yaml defines the fixed data, split, model, training, calibration, and evaluation settings.
  - data_schema.yaml defines the required processed-data fields.
  - ablations/, baselines/, and robustness/ contain the corresponding workflow configurations.
- scripts/ contains command-line utilities for repository checks, Kaggle data retrieval, DEAM feature extraction, data preparation, source-manifest construction, protocol execution, baseline handling, robustness runs, model profiling, static-contract checks, and reference-record verification.
- data/README.md describes the expected local data layout, public dataset sources, feature preparation requirements, and data-handling boundaries.
- tests/ contains tests for calibration, preprocessing, grouped split construction, model contracts, and ensemble aggregation.
- reference_results/ contains CSV reference records organized by internal validation, baselines, external evaluation, calibration, robustness, statistical analysis, and efficiency analysis.
- reference_logs/ contains concise reference log records for the locked protocol, internal validation, external evaluation, ablation and calibration workflows, and efficiency profiling.
Entry points
The rjd_calnet.cli module provides commands for data auditing, cross-validation, frozen external evaluation, statistical analysis, ablation workflows, and run summarization. The shell script scripts/run_locked_protocol.sh sequences the repository check, data audit, cross-validation, external evaluation, and summary steps.
Data boundary
The package is structured to work with DEAM and PMEmo data placed locally under data/raw/ and data/processed/. Source data remain outside version control; the package stores code, configurations, tests, reference records, and logs only.
