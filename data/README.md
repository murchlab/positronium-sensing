# Data

This folder contains the **released input datasets** needed to run the analysis notebooks in `notebooks/`.

The emphasis is on *analysis reproducibility*: most inputs are already in the form of time samples and measured (or readout-corrected) populations, rather than raw digitizer traces.

## CSV conventions
- Time lists are one-column CSVs with header `t_list` (values are in **ns**).
- Population files contain probabilities in `[0, 1]` and include a header row with column names.

**Files**
- **Singlet (two-qubit) datasets**
  - `singlet_U{ x,y,z }_t_list_1218.csv`: time samples (ns).
  - `singlet_U{ x,y,z }_P_1218.csv`: readout-corrected two-qubit populations with columns:
    - `P_00, P_01, P_10, P_11` in computational-basis order `|00⟩, |01⟩, |10⟩, |11⟩`.

- **Unentangled (single-qubit) datasets used for FI baselines**
  - `Ux_Uy_Uz_pre_xz_meas_xz_t_list_1218.csv`: time samples (ns).
  - `Ux_Uy_Uz_pre_xz_meas_xz_P_Q{1,2}_U{ x,y,z }_1218.csv`: readout-corrected single-qubit populations with columns:
    - `ground, excited` corresponding to `|0⟩, |1⟩`.

- **Z-gate / Rabi-curve datasets (Fig. 2c,d)**
  - `Q1_{x,y}_rabi_t_list_1213_1230.csv`: time samples (ns).
  - Single-qubit populations with `ground, excited` columns:
    - `Q1_x_rabi_P_Q1_px_rabi_1213_1230.csv`, `Q1_x_rabi_P_Q1_mx_rabi_1213_1230.csv`
    - `Q1_y_rabi_P_Q1_py_rabi_1213_1230.csv`, `Q1_y_rabi_P_Q1_my_rabi_1213_1230.csv`
  - Files with an additional `_e_` tag are included in the data release but are not used by the figure-export notebook.

- **AC Stark shift sweeps (Fig. 2e,f)**
  - Frequency sweep:
    - `ACS_f_sweep_ACS_frequency_{0208,0408}.csv`: drive frequency samples (GHz; multiplied by `1e9` in the notebook).
    - `ACS_f_sweep_Q{1,2}_delta_freq_array_{0208,0408}.csv`: fitted frequency shifts (Hz; plotted as MHz).
  - Amplitude sweep:
    - `ACS_amp_sweep_Amp_1213_1035.csv`: drive amplitude in arbitrary units (`amp`).
    - `ACS_amp_sweep_Q{1,2}_delta_freq_amp_array_1213_1035.csv`: fitted frequency shifts (Hz).

- **Integration-weights demo inputs (HDF5)**
  - `integration_weights.hdf5`: integration window definitions and reference weight vectors.
  - `res_1_IJK_sample.hdf5`: a small included sample record used by the demo.
  - `ADC_sample.hdf5`: a small synthetic dataset produced by `notebooks/A01_*` (used by `notebooks/07_*`).

**Naming conventions**
- `1218` is a date tag that is part of the filename. The notebooks treat it as a label, not as a parameter that changes the analysis.
