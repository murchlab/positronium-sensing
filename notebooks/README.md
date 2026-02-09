# Notebooks

Run the notebooks in numeric order. Each notebook starts with an overview written for readers who want to understand the **data-processing logic** (not the experimental control stack).

## Dependency overview

```mermaid
flowchart TD
  data["`data/`"] --> nb01["01: Z-gate curves<br/>(Fig. 2c,d)"]
  data --> nb02["02: AC Stark shift sweeps<br/>(Fig. 2e,f)"]
  data --> nb03["03: FI extraction<br/>(readout-corrected singlet + single-qubit)"]
  data --> nb04["04: FI extraction<br/>(raw extraction)"]
  data_analysis["`data_analysis/`"] --> nb06["06: Combined SI panels + Fig. 3"]
  nb03 --> data_analysis
  nb04 --> data_analysis
  nb05["05: Gate-corrected singlet<br/>(figure assembly)"] --> nb06

  data --> nb07["07: Integration weights demo"]
  data --> nb08["08: Readout correction (IBU) demo"]
  nbA01["A01 (optional): create demo ADC dataset"] --> nb07
  data --> nbA01

  nb01 --> main_text["`main_text_figures/`"]
  nb02 --> main_text
  nb06 --> main_text
  nb03 --> si["`si_figures/`"]
  nb04 --> si
  nb05 --> si
  nb06 --> si
  nb07 --> si
  nb08 --> figures["`figures/`"]
```

## Recommended order (with purpose)
- `01_z_gate_curves_fig2cd.ipynb`: loads single-qubit Rabi datasets and exports the Fig. 2c,d curves.
- `02_ac_stark_shift_sweeps_fig2ef.ipynb`: fits a AC Stark shift model to AC Stark shift sweeps and exports the Fig. 2e,f panels.
- `03_singlet_readout_corrected_fi_analysis.ipynb`: converts `t → α`, extracts `P(α)` and `FI(α)` (readout-corrected), and writes `data_analysis/*_readout_corrected.csv`.
- `04_singlet_raw_fi_analysis.ipynb`: extracts raw probabilities using readout confusion matrices, extracts `FI(α)`, and writes `data_analysis/*_raw.csv`.
- `05_singlet_gate_corrected_fi_analysis.ipynb`: loads gate-corrected singlet `alpha, P, FI` CSVs and exports the corresponding SI panels.
- `06_combined_si_figures_and_fig3.ipynb`: combines the three singlet styles (readout-corrected/raw/gate-corrected) on a shared `α` grid and exports the combined SI panels and Fig. 3.
- `07_readout_integration_weights_demo.ipynb`: demonstrates windowed downsampling + LDA-based integration weights on an included ADC dataset.
- `08_readout_fidelity_correction_ibu_demo.ipynb`: demonstrates Iterative Bayesian Update (IBU) readout-fidelity correction on an included dataset.

Optional:
- `A01_integration_weights_demo_training_data.ipynb`
