# Stealing Speed from Planets: Measuring a Gravity Assist

## Overview

This project investigates how a spacecraft can change its velocity relative to the Sun during a planetary flyby without using onboard propellant. Using reconstructed trajectory data from NASA JPL Horizons, it studies the Jupiter gravity assists of **Voyager 2 (1979)** and **New Horizons (2007)**.

The analysis measures the heliocentric velocity change, compares observations with the patched-conic model, checks the model with a numerical simulation, and estimates the propellant required to reproduce the speed gains using a rocket burn.

## Objectives

- Retrieve spacecraft and Jupiter state vectors from NASA JPL Horizons.
- Measure the heliocentric velocity change associated with each Jupiter flyby.
- Correct for the effect of solar gravity over the measurement interval.
- Compare observed flyby parameters with patched-conic predictions.
- Independently simulate hyperbolic flybys under Jupiter's gravity.
- Estimate equivalent propellant requirements using the Tsiolkovsky rocket equation.

## Key Results

The report gives the following solar-corrected heliocentric speed gains:

| Spacecraft | Jupiter flyby | Corrected heliocentric speed gain |
|---|---|---:|
| Voyager 2 | 9 July 1979 | 10.60 ± 0.06 km/s |
| New Horizons | 28 February 2007 | 3.20 ± 0.03 km/s |

The reported observed velocity-change magnitudes are 11.95 ± 0.23 km/s for Voyager 2 and 5.14 ± 0.01 km/s for New Horizons. The patched-conic predictions agree with the measured magnitudes to within 4.3% and 0.6%, respectively. These results and uncertainties are those reported in the project document.

## Methods

1. Obtain state vectors from NASA JPL Horizons using Python's `astroquery` package.
2. Convert position and velocity values to kilometres and kilometres per second.
3. Compare the observed trajectory with a solar-gravity-only propagation to estimate Jupiter's contribution.
4. Calculate the expected flyby deflection and velocity change with the patched-conic approximation.
5. Numerically integrate representative flyby trajectories under Jupiter's gravity.
6. Apply the Tsiolkovsky rocket equation to estimate equivalent propellant mass.

## Technologies

- Python
- Jupyter Notebook
- Anaconda
- NumPy
- SciPy
- Matplotlib
- Astroquery
- NASA JPL Horizons

> The list above reflects the tools described or implied by the report. Check the notebook imports and environment before treating it as the exact dependency list.

## Data Source

- [NASA JPL Horizons System](https://ssd.jpl.nasa.gov/horizons/)

The report uses reconstructed ephemeris trajectories from JPL Horizons. These are model-based trajectory reconstructions, not raw spacecraft measurements.

## Getting Started

### Requirements

Install [Anaconda](https://www.anaconda.com/download) or another Python environment that supports Jupyter Notebook.

The report describes use of `astroquery`, `numpy`, `scipy`, and `matplotlib`. If these packages are required by the notebook and are not already installed, install them in your active environment:

```bash
python -m pip install astroquery numpy scipy matplotlib
```

### Run the notebook

1. Clone or download this repository.
2. Open Anaconda Navigator and launch Jupyter Notebook, or launch Jupyter from your terminal.
3. Navigate to the project folder.
4. Open the project's `.ipynb` notebook.
5. Run the cells from top to bottom.
6. Ensure that internet access is available if the notebook retrieves ephemeris data from JPL Horizons.

## Repository Structure

A suggested layout is:

```text
stellarproj-gravity-assists/
├── README.md
├── gravity_assists.ipynb
└── report/
    └── stellarproj_1_gravity assists.pdf
```

Rename the notebook and report paths in this section to match the actual files you upload. Include any additional data files or scripts that the notebook needs.

## Limitations

The report notes that the Horizons trajectories are reconstructed using dynamical models; the patched-conic model omits some perturbations, and the solar-only comparison is itself a model. The propellant estimate assumes a single impulsive burn and is a lower-bound comparison rather than a complete mission design.

## References

1. NASA Jet Propulsion Laboratory, [JPL Horizons System](https://ssd.jpl.nasa.gov/horizons/).
2. Ginsburg et al., “Astroquery: An Astronomical Web-querying Package in Python,” *The Astronomical Journal*, 157, 98 (2019).
3. NASA, [Basics of Space Flight](https://science.nasa.gov/learn/basics-of-space-flight/).
4. Curtis, H. D., *Orbital Mechanics for Engineering Students*, 4th ed., Butterworth-Heinemann, 2020.
5. Virtanen et al., “SciPy 1.0: Fundamental Algorithms for Scientific Computing in Python,” *Nature Methods*, 17, 261–272 (2020).

## Author

**Yatheeswar M.**

Update this section if you want to use a different author name or add collaborators.

## License

No license has been selected yet. If you want others to reuse or modify the code, choose an appropriate open-source license and add its license file. Without a license, normal copyright restrictions apply.
