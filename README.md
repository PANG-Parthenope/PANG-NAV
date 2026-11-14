PANG-NAV

MATLAB Software for GNSS Single Point Positioning (SPP) and Receiver Autonomous Integrity Monitoring (RAIM-FDE)

Developed by the PArthenope Navigation Group (PANG)
University of Naples Parthenope, Italy

Website: https://www.panglab.eu

⸻

Overview

PANG-NAV is a MATLAB-based software package developed by the PArthenope Navigation Group (PANG) for processing single-frequency Global Navigation Satellite System (GNSS) measurements.

The software implements Single Point Positioning (SPP) algorithms using GPS and Galileo observations, including Receiver Autonomous Integrity Monitoring with Fault Detection and Exclusion (RAIM-FDE).

PANG-NAV processes GNSS measurements stored in RINEX files to estimate receiver position and clock offset. It also provides information about satellite visibility, satellite geometry, positioning availability, and solution reliability.

The RAIM-FDE module allows the detection and exclusion of anomalous measurements and the computation of horizontal and vertical protection levels.

When reference coordinates are available, PANG-NAV can perform positioning error analysis.

The software supports both static and kinematic GNSS data processing.

PANG-NAV was originally presented in the following scientific publication:

Angrisano, A., Gaglione, S., Crocetto, N., & Vultaggio, M. (2020).
PANG-NAV: a tool for processing GNSS measurements in SPP, including RAIM functionality.
GPS Solutions, 24, Article 19.
https://doi.org/10.1007/s10291-019-0935-y

The original software was distributed through the GPS Toolbox repository of the National Geodetic Survey (NOAA).

Following the discontinuation of the original distribution service, PANG-NAV has been made available through the PANG GitHub repository and archived on Zenodo to support continued accessibility and reproducible scientific research.

⸻

Main Features

GNSS Processing

* GPS-only positioning.
* Combined GPS/Galileo positioning.
* Single-frequency GNSS measurements.
* RINEX observation and navigation file processing.
* Static and kinematic positioning.

Single Point Positioning

* Weighted Least Squares (WLS) position estimation.
* Receiver clock offset estimation.
* GPS/Galileo inter-system time offset estimation.
* Satellite orbit propagation.
* Satellite clock and relativistic corrections.
* Klobuchar ionospheric correction model.
* Saastamoinen tropospheric correction model.
* Elevation-dependent observation weighting.

Receiver Autonomous Integrity Monitoring

* RAIM Fault Detection and Exclusion (RAIM-FDE).
* Detection of anomalous pseudorange measurements.
* Exclusion of measurements identified as outliers.
* Observation subset testing.
* Horizontal Protection Level (HPL).
* Vertical Protection Level (VPL).
* Solution reliability assessment.
* Reliable positioning availability.

Performance Analysis

* Satellite visibility analysis.
* Position Dilution of Precision (PDOP).
* Positioning solution availability.
* Horizontal and vertical positioning errors.
* Statistical positioning error indicators.
* Graphical visualization of positioning results.

⸻

Download

Official GitHub Release

The official PANG-NAV software distribution is available through GitHub Releases.

Download PANG-NAV v1.0.0

The release includes:

* MATLAB source code.
* GNSS sample datasets.
* User manual.
* Software documentation.
* License and terms of use.

Zenodo Archive

PANG-NAV v1.0.0 is also permanently archived on Zenodo.

Software DOI:
https://doi.org/10.5281/zenodo.24221377

Access PANG-NAV on Zenodo

The Zenodo archive provides a persistent reference to the published software version.

⸻

Software Requirements

PANG-NAV has been developed in the MATLAB environment.

The original implementation was developed and tested using MATLAB versions available at the time of the 2020 publication.

Compatibility with recent MATLAB releases has not yet been systematically verified.

The software requires access to suitable GNSS observation and navigation files in RINEX format.

The accompanying user manual describes the supported input formats and configuration parameters.

⸻

Installation

1. Download the PANG-NAV software package from the GitHub Releases page.
2. Extract the ZIP archive to a local directory.
3. Start MATLAB.
4. Set the MATLAB current working directory to the folder containing Main.m.
5. Open Main.m in the MATLAB Editor.
6. Configure the processing parameters in the settings section.
7. Run the program by pressing Run or entering the following command in the MATLAB Command Window:

Main

During execution, PANG-NAV prompts the user to select the required RINEX files.

⸻

Input Data

PANG-NAV processes GNSS measurements stored in RINEX files.

The software requires:

1. A RINEX observation file containing GNSS measurements.
2. A mixed GNSS navigation file containing broadcast ephemerides.
3. A GPS navigation file containing the parameters required by the Klobuchar ionospheric model.

The original user manual describes the use of RINEX version 3.2.

The repository includes sample GNSS datasets that can be used to explore the software functionality.

Reference Position

When positioning error analysis is enabled, a reference solution can be supplied.

The reference coordinates may be obtained from the RINEX header for static receivers or loaded from an external MATLAB .mat file.

The reference solution must follow the format described in the user manual.

⸻

Configuration

The main processing parameters are defined in the settings section of Main.m.

Parameter	Description
dt_data	Processing interval in seconds
gnss_systems	GNSS configuration: GPS or GPS/Galileo
Weight_flag	Observation weighting configuration
RAIM_flag	Enables or disables RAIM processing
mask_angle	Satellite elevation mask in degrees
SNR_lim	Minimum signal-to-noise ratio in dB-Hz
Error_Analysis_flag	Enables positioning error analysis
Static_Solution_fromRINEX	Uses reference coordinates from the RINEX header

GNSS Configuration

gnss_systems = 1;  % GPS only
gnss_systems = 2;  % GPS/Galileo

Observation Weighting

Weight_flag = 0;  % Equal weights
Weight_flag = 1;  % Elevation-dependent weighting

RAIM Configuration

RAIM_flag = 0;  % RAIM disabled
RAIM_flag = 1;  % RAIM enabled

Additional RAIM parameters include:

* HAL: Horizontal Alarm Limit.
* VAL: Vertical Alarm Limit.
* PFA: Probability of False Alarm.
* PMD: Probability of Missed Detection.
* sigma_pr: Standard deviation of pseudorange measurements.

These parameters should be selected according to the considered application.

⸻

Output

PANG-NAV provides MATLAB variables containing the estimated navigation solution and associated performance indicators.

Main Output Variables

Variable	Description
X	Estimated receiver position and clock offsets
epochs	Processing epochs
DOPs	Position Dilution of Precision
nr_sat	Number of available and used satellites
Sol_availability	Positioning solution availability
RAIM_Results	RAIM reliability indicators
PLs	Horizontal and vertical protection levels
Reliable_availability	Reliable positioning availability
e_H_g	Horizontal positioning errors
e_U_g	Vertical positioning errors
Error_Table_Pos	Statistical positioning error indicators

Some output variables are available only when RAIM or error analysis is enabled.

Graphical Outputs

PANG-NAV can generate plots showing:

* Horizontal positioning results.
* Receiver height versus time.
* Satellite visibility.
* DOP evolution.
* Horizontal and vertical protection levels.
* Horizontal and vertical positioning errors.

Further details are provided in the user manual.

⸻

Documentation

The complete PANG-NAV User Manual is available in the repository.

PANG-NAV User Manual

The manual describes:

* Software configuration.
* Required input files.
* GNSS processing procedures.
* RAIM settings.
* Output variables.
* Graphical results.

⸻

Scientific Reference

The algorithms and methodology implemented in PANG-NAV are described in:

Angrisano, A., Gaglione, S., Crocetto, N., & Vultaggio, M. (2020).

PANG-NAV: a tool for processing GNSS measurements in SPP, including RAIM functionality.

GPS Solutions, 24, Article 19.

https://doi.org/10.1007/s10291-019-0935-y

Users of PANG-NAV are requested to cite this publication when reporting scientific results obtained using the software.

⸻

Software Citation

The archived software version can be cited as:

PArthenope Navigation Group (2026).

PANG-NAV: GNSS Single Point Positioning and RAIM Software.

Version 1.0.0. Zenodo.

https://doi.org/10.5281/zenodo.24221377

For reproducibility, users are encouraged to identify the software version used in their research.

The scientific paper and the software archive represent complementary references:

* The scientific publication describes the methodology and algorithms.
* The Zenodo DOI identifies the archived software distribution.

⸻

License

PANG-NAV is distributed under the:

PANG-NAV Academic and Research License — Version 1.0

Copyright © 2020 Ciro Gioia. All rights reserved.

The license permits free use and modification of the software for non-commercial scientific research and educational purposes.

Commercial use and redistribution of the original or modified software require prior written authorization.

Users must retain the original copyright and attribution notices and comply with the citation requirements specified in the license.

The complete terms and conditions are available in the LICENSE file.

Authorization Requests

Requests for commercial use, redistribution, or other permissions should be addressed to:

Antonio Angrisano
antonio.angrisano@unime.it

Salvatore Gaglione
salvatore.gaglione@uniparthenope.it

⸻

Disclaimer

PANG-NAV is provided for scientific research and educational purposes.

The software is provided without warranty, subject to the terms and limitations specified in the license.

PANG-NAV has not been certified for operational or safety-critical navigation applications.

The implementation of RAIM algorithms and the computation of protection levels do not imply compliance with aviation, maritime, or other safety-critical certification standards.

⸻

Project Information

Software: PANG-NAV
Research Group: PArthenope Navigation Group (PANG)
Institution: University of Naples Parthenope
Website: https://www.panglab.eu
GitHub: https://github.com/PANG-Parthenope/PANG-NAV
Software DOI: https://doi.org/10.5281/zenodo.24221377
Scientific Publication DOI: https://doi.org/10.1007/s10291-019-0935-y

⸻

PArthenope Navigation Group (PANG)
Positioning · Navigation · Geospatial Technologies