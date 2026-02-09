# Data

This folder contains the **released input datasets** needed to run the analysis notebooks in [`notebooks/`](../notebooks/).

The emphasis is on *analysis reproducibility*: most inputs are already in the form of time samples and measured (or readout-corrected) populations, rather than raw digitizer traces.

## CSV conventions
- Time lists are one-column CSVs with header `t_list` (values are in **ns**).
- Population files contain probabilities in `[0, 1]` and include a header row with column names.

**Files**
- **Singlet (two-qubit) datasets**
  - Time samples (ns):
    - [`singlet_Ux_t_list_1218.csv`](./singlet_Ux_t_list_1218.csv), [`singlet_Uy_t_list_1218.csv`](./singlet_Uy_t_list_1218.csv), [`singlet_Uz_t_list_1218.csv`](./singlet_Uz_t_list_1218.csv)
  - Readout-corrected two-qubit populations:
    - [`singlet_Ux_P_1218.csv`](./singlet_Ux_P_1218.csv), [`singlet_Uy_P_1218.csv`](./singlet_Uy_P_1218.csv), [`singlet_Uz_P_1218.csv`](./singlet_Uz_P_1218.csv)
  - Population columns:
    - `P_00, P_01, P_10, P_11` in computational-basis order `|00⟩, |01⟩, |10⟩, |11⟩`.

- **Unentangled (single-qubit) datasets used for FI baselines**
  - Time samples (ns):
    - [`Ux_Uy_Uz_pre_xz_meas_xz_t_list_1218.csv`](./Ux_Uy_Uz_pre_xz_meas_xz_t_list_1218.csv)
  - Readout-corrected single-qubit populations:
    - [`Ux_Uy_Uz_pre_xz_meas_xz_P_Q1_Ux_1218.csv`](./Ux_Uy_Uz_pre_xz_meas_xz_P_Q1_Ux_1218.csv), [`Ux_Uy_Uz_pre_xz_meas_xz_P_Q1_Uy_1218.csv`](./Ux_Uy_Uz_pre_xz_meas_xz_P_Q1_Uy_1218.csv), [`Ux_Uy_Uz_pre_xz_meas_xz_P_Q1_Uz_1218.csv`](./Ux_Uy_Uz_pre_xz_meas_xz_P_Q1_Uz_1218.csv)
    - [`Ux_Uy_Uz_pre_xz_meas_xz_P_Q2_Ux_1218.csv`](./Ux_Uy_Uz_pre_xz_meas_xz_P_Q2_Ux_1218.csv), [`Ux_Uy_Uz_pre_xz_meas_xz_P_Q2_Uy_1218.csv`](./Ux_Uy_Uz_pre_xz_meas_xz_P_Q2_Uy_1218.csv), [`Ux_Uy_Uz_pre_xz_meas_xz_P_Q2_Uz_1218.csv`](./Ux_Uy_Uz_pre_xz_meas_xz_P_Q2_Uz_1218.csv)
  - Population columns:
    - `ground, excited` corresponding to `|0⟩, |1⟩`.

- **Z-gate / Rabi-curve datasets (Fig. 2c,d)**
  - Time samples (ns):
    - [`Q1_x_rabi_t_list_1213_1230.csv`](./Q1_x_rabi_t_list_1213_1230.csv), [`Q1_y_rabi_t_list_1213_1230.csv`](./Q1_y_rabi_t_list_1213_1230.csv)
  - Single-qubit populations with `ground, excited` columns:
    - [`Q1_x_rabi_P_Q1_px_rabi_1213_1230.csv`](./Q1_x_rabi_P_Q1_px_rabi_1213_1230.csv), [`Q1_x_rabi_P_Q1_mx_rabi_1213_1230.csv`](./Q1_x_rabi_P_Q1_mx_rabi_1213_1230.csv)
    - [`Q1_y_rabi_P_Q1_py_rabi_1213_1230.csv`](./Q1_y_rabi_P_Q1_py_rabi_1213_1230.csv), [`Q1_y_rabi_P_Q1_my_rabi_1213_1230.csv`](./Q1_y_rabi_P_Q1_my_rabi_1213_1230.csv)
  - Files with an additional `_e_` tag are included in the data release but are not used by the figure-export notebook.

- **AC Stark shift sweeps (Fig. 2e,f)**
  - Frequency sweep:
    - Drive frequency samples (GHz; multiplied by `1e9` in the notebook):
      - [`ACS_f_sweep_ACS_frequency_0208.csv`](./ACS_f_sweep_ACS_frequency_0208.csv), [`ACS_f_sweep_ACS_frequency_0408.csv`](./ACS_f_sweep_ACS_frequency_0408.csv)
    - Fitted frequency shifts (Hz; plotted as MHz):
      - [`ACS_f_sweep_Q1_delta_freq_array_0208.csv`](./ACS_f_sweep_Q1_delta_freq_array_0208.csv), [`ACS_f_sweep_Q1_delta_freq_array_0408.csv`](./ACS_f_sweep_Q1_delta_freq_array_0408.csv)
      - [`ACS_f_sweep_Q2_delta_freq_array_0208.csv`](./ACS_f_sweep_Q2_delta_freq_array_0208.csv), [`ACS_f_sweep_Q2_delta_freq_array_0408.csv`](./ACS_f_sweep_Q2_delta_freq_array_0408.csv)
  - Amplitude sweep:
    - [`ACS_amp_sweep_Amp_1213_1035.csv`](./ACS_amp_sweep_Amp_1213_1035.csv): drive amplitude in arbitrary units (`amp`).
    - [`ACS_amp_sweep_Q1_delta_freq_amp_array_1213_1035.csv`](./ACS_amp_sweep_Q1_delta_freq_amp_array_1213_1035.csv), [`ACS_amp_sweep_Q2_delta_freq_amp_array_1213_1035.csv`](./ACS_amp_sweep_Q2_delta_freq_amp_array_1213_1035.csv): fitted frequency shifts (Hz).

- **Integration-weights demo inputs (HDF5)**
  - [`integration_weights.hdf5`](./integration_weights.hdf5): integration window definitions and reference weight vectors.
  - [`res_1_IJK_sample.hdf5`](./res_1_IJK_sample.hdf5): a small included sample record used by the demo.
  - [`ADC_sample.hdf5`](./ADC_sample.hdf5): a small demo dataset produced by [`notebooks/A01_integration_weights_demo_training_data.ipynb`](../notebooks/A01_integration_weights_demo_training_data.ipynb) (used by [`notebooks/07_readout_integration_weights_demo.ipynb`](../notebooks/07_readout_integration_weights_demo.ipynb)).

**Naming conventions**
- `1218` is a date tag that is part of the filename. The notebooks treat it as a label, not as a parameter that changes the analysis.
