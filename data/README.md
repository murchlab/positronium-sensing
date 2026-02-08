# Data

This folder contains the minimal experimental artifacts needed to run the analysis notebooks in `notebooks/`.

**Files**
- `singlet_U{ x,y,z }_t_list_1218.csv`: time samples for singlet experiments.
- `singlet_U{ x,y,z }_P_1218.csv`: readout-fidelity-corrected populations for the singlet experiments (columns correspond to computational-basis outcomes).
- `Ux_Uy_Uz_pre_xz_meas_xz_t_list_1218.csv`: time samples for single-qubit unentangled experiments.
- `Ux_Uy_Uz_pre_xz_meas_xz_P_Q{1,2}_U{ x,y,z }_1218.csv`: readout-fidelity-corrected single-qubit populations used to compute FI for Q1 and Q2.
- `integration_weights.hdf5`, `res_1_IJK_sample.hdf5`, `ADC_sample.hdf5`: small HDF5 artifacts used by the integration-weights notebooks.

**Naming conventions**
- `1218` is a date tag that is part of the filename. The notebooks treat it as a label, not as a parameter that changes the analysis.

