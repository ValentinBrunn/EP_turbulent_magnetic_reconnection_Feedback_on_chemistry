# Scripts for Brunn et al. (2026)

This repository contains the analysis notebooks used to compute, compare, and visualise the energetic-particle ionisation models presented in Brunn et al. (2026).

The scripts are provided to document the analysis workflow and to help reproduce the figures and post-processing steps of the paper. Large ProDiMo model outputs are not included in this repository because of their size.

## Repository content

| File | Purpose |
| --- | --- |
| `MainAnalytic.ipynb` | Main semi-analytic calculation of the energetic-particle ionisation rate. It reads a ProDiMo disc model, computes the local turbulent reconnection and particle propagation quantities, and writes an ionisation-rate map. |
| `createzetaSPTurbulent.ipynb` | Interpolates a computed ionisation-rate map onto a target ProDiMo grid and writes a ProDiMo-readable input file. |
| `DiscModelComparison.ipynb` | Comparison notebook for individual ProDiMo models with and without energetic-particle ionisation. It includes diagnostics for ionisation, chemistry, spectra, MRI-related quantities, and non-ideal MHD quantities. |
| `PlotSetofModels.ipynb` | Post-processing and plotting notebook for the full grid of ProDiMo models. It compares EP and NOEP models, produces abundance/ionisation maps, line-flux diagnostics, line-ratio diagnostics, and figure-ready outputs. |

## Requirements

The notebooks were written in Python and require the following main packages:

```bash
numpy
scipy
matplotlib
pandas
prodimopy
import-ipynb
```

Additional standard-library modules such as `os`, `time`, `contextlib`, and `io` are also used.

The package `prodimopy` must also be installed and configured so that ProDiMo output directories can be read.

## External data required

The notebooks expect local ProDiMo output folders and ionisation-rate text files. These files are not included in this repository. Contact a Prodimo developer to access ProDimo outputs. Solution from any disc model can be used if properly formatted.

Model directories used in the notebooks include paths such as:

```text
PMODELS/
PMODELS/GRIDS/NOEP/
PMODELS/GRIDS/EP/
TTauriJWST_Large/
```

These paths may need to be adapted to the local directory structure before running the notebooks.

## Notes on reproducibility

The notebooks were developed as research analysis notebooks. Some cells contain project-specific paths, commented tests, and exploratory calculations.

## Citation

If you use these scripts, please cite:

```text
Brunn et al. (2026), Energetic particles accelerated via turbulent magnetic reconnection in protoplanetary discs -- II. Feedback on chemistry and observables, [journal/reference when available].
```

## License

Unless stated otherwise, the scripts are released under the GPL-3.0 License.
