# Data: spectral transfer learning for dielectric metasurfaces (300–600 THz)

Data accompanying the manuscript *"Spectral transfer learning for data-efficient inverse
design of high-index dielectric metasurfaces in the visible and near-infrared"*
(N. Hosen, submitted to *Materials Letters*). Only data are shared here; the neural-network
and optimization code builds on the code released by Xu et al. (Adv. Photonics Nexus 3,
026002, 2024) and is not redistributed.

## Files

### `meta-atom_complex_transmission_300-600THz_1960samples.xlsx`
Full-wave (CST Microwave Studio) complex transmission of dielectric cylinder meta-atoms on a
200-nm SiO₂ substrate (ε = 2.25), 220-nm unit cell, periodic boundaries in x and y,
open (PML) boundaries in z, normal-incidence plane wave, field probe 2 µm above the structure.
1960 rows (one meta-atom per row; two parameter combinations appear twice).

| Column | Meaning | Unit | Range |
|---|---|---|---|
| `e` | relative permittivity ε of the cylinder | – | 13–18 |
| `g_um` | gap g to the neighbouring meta-atom | µm | 0.010–0.150 |
| `h_um` | cylinder height h | µm | 0.050–0.155 |
| `r_um` | cylinder radius r | µm | 0.010–0.105 |
| `t_300THz` … `t_600THz` | complex transmission coefficient at 101 frequencies, 300–600 THz in 3-THz steps | – | \|t\| ≤ 1.03 |

Complex values are stored as text in Python format, e.g. `(0.729-0.512j)`.
Read them with `complex(cell.replace(" ", ""))`.

### `metalens_570THz_inverse_design_101_atoms.xlsx`
Inverse-design result for the 570-THz cylindrical metalens (f = 30 µm, 101 meta-atoms, 250-nm pitch).
Columns: `atom` (1–101), `unique_id` (mirror symmetry: atom j = atom 100 − j), `x_um`,
`permittivity`, `gap_nm`, `height_nm`, `radius_nm`, `phase_target_pi`, `phase_pred_pi`
(phase in units of π), `phase_error_deg`, `amp_target`, `amp_pred`, `amp_error`.

### `fig1a-d_coupled_dipole_model.xlsx`
Coupled-dipole Huygens' model (Fig. 1a–d): |t|² of the total, electric and magnetic
contributions and the total phase (rad), for separated (`sep_*`; 1400/1200 nm) and
overlapped (`ovl_*`; 1300 nm) resonances, damping γ = 3×10¹³ s⁻¹.

### `fig1e_Si_nanodisk_array_spectrum_r242nm.xlsx`
Simulated transmittance and phase (rad) of a Si nanodisk array (r = 242 nm, h = 220 nm,
embedded in n = 1.66), Fig. 1e.

## License
CC BY 4.0. Please cite the article above when using these data.
