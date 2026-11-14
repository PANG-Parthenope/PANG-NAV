# PANG-NAV

**MATLAB software for GNSS Single Point Positioning (SPP) and Receiver Autonomous Integrity Monitoring (RAIM-FDE).**

PANG-NAV was developed by the PArthenope Navigation Group (PANG). It processes single-frequency GNSS measurements from RINEX files, supporting GPS-only and combined GPS/Galileo positioning. The software includes weighted least-squares estimation, satellite geometry and visibility analysis, RAIM fault detection and exclusion, horizontal and vertical protection levels, and optional position-error analysis against reference coordinates.

## Scientific reference

Angrisano, A., Gaglione, S., Crocetto, N., & Vultaggio, M. (2020). **PANG-NAV: a tool for processing GNSS measurements in SPP, including RAIM functionality.** *GPS Solutions*, 24, article 19. https://doi.org/10.1007/s10291-019-0935-y

The paper originally referred readers to the NOAA/National Geodetic Survey GPS Toolbox website for the MATLAB package, sample datasets and user manual. This repository is intended to restore access to the original research software.

## Getting started

1. Install MATLAB. The minimum supported MATLAB version and any required toolboxes have **not yet been verified**.
2. Open MATLAB and set `PANG_NAV/` as the current working folder.
3. Open `PANG_NAV/Main.m` and review the settings, including `gnss_systems`, `Weight_flag`, `RAIM_flag`, `mask_angle`, `SNR_lim` and optional error analysis.
4. Run `Main` in the MATLAB Command Window (or use the Run button).
5. When prompted, select the RINEX observation file, mixed navigation file and GPS navigation file. Sample files are in `PANG_NAV/data/`.

See `docs/PANG-NAV_User_Manual_corrected.pdf` for detailed settings, input formats and output variables.

## Code and data

- `PANG_NAV/Main.m`: entry point.
- `PANG_NAV/library/`: MATLAB functions, including RINEX and RAIM routines.
- `PANG_NAV/data/`: bundled example files, including BRUX observations and a version with simulated blunders.
- `docs/`: user manual.

## Reproducibility and status

This is a **publication-preparation copy** of the historical MATLAB code. Algorithms have not been intentionally modified. The package has **not been executed or validated in MATLAB** during preparation. Results should be independently checked before research or operational use. This research software is not certified for safety-critical navigation.

## Citation

Please cite the peer-reviewed article above when using PANG-NAV. Machine-readable citation metadata are provided in `CITATION.cff`.

## Licensing and publication approval

**Not yet licensed for public redistribution.** BSD-3-Clause is the proposed license, subject to confirmation by all relevant rights holders and review of any third-party components and dataset terms. Do not publish this preparation package as an open-source release until those checks are completed and an authorized `LICENSE` file is added.
