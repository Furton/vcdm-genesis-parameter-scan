# Genesis VCDM Scan Table

This repository contains one data file:

- `genesis_scan_table.csv`

The file is a precomputed grid table for the Genesis VCDM model. It has **512,000 rows** and **6 columns**.

## Priors and grid

The scan uses **80 points** for each input parameter, giving `80 × 80 × 80 = 512,000` grid points.

| Parameter | Prior range | Grid type |
|---|---:|---|
| `alpha` | `1e-30` to `1e-21` | logarithmic |
| `d` | `0.1` to `0.4` | linear |
| `kappa` | `1e-9` to `1e-4` | logarithmic |

## Columns

| Column | Description |
|---|---|
| `alpha` | Input parameter |
| `d` | Input parameter |
| `kappa` | Input parameter |
| `Ps` | Calculated scalar power spectrum; not normalized |
| `ns` | Scalar spectral index |
| `alpha_s` | Running of the scalar spectral index |

## Interpolation

The file stores the calculated scalar power spectrum `Ps`. This `Ps` is not normalized.

To evaluate `ns` and `alpha_s`, we use **cubic spline interpolation** of `Ps`.
