# Measuring the Supermassive Black Hole at the Galactic Center

**Authors:** Jacob Parzych & Niko Jamison
**Course:** Astronomy 1221 - Project 3  
**Institution:** The Ohio State University  
**Date:** December 2025

## Overview

This project analyzes the orbit of star **S2** around the supermassive black hole **Sagittarius A*** (Sgr A*) at the center of our Milky Way galaxy. By tracking S2's motion over ~13 years using high-precision astrometry from the Keck telescopes, we measure the black hole's mass using Kepler's Third Law.

This analysis replicates **Nobel Prize-winning science** by Andrea Ghez and Reinhard Genzel (2020 Nobel Prize in Physics), who proved that Sgr A* is a supermassive black hole.

## Key Results

- **Black Hole Mass:** M_BH ≈ (4.0 ± 0.4) × 10⁶ M☉
- **Reduced χ²:** ~0.8 (excellent fit for Keck-only data)
- **Orbital Period:** ~16 years (highly eccentric orbit, e ≈ 0.88)
- **Distance to Galactic Center:** R₀ ≈ 8.0 kpc (assumed in standard analysis)

## Scientific Background

The Galactic Center hosts a supermassive black hole with a mass of approximately 4 million solar masses. By tracking the orbits of stars near Sgr A*, astronomers can:

1. Measure the black hole's mass using Keplerian dynamics
2. Test Einstein's General Relativity in strong gravitational fields
3. Prove the existence of supermassive black holes at galaxy centers

This project demonstrates both the **power** of ground-based observations and their **limitations** compared to modern interferometric techniques (GRAVITY collaboration).

## Project Structure

```
Astron_1221_Project_3/
├── Project3_Parzych_Jamison.ipynb  # Main analysis notebook
├── README.md                         # This file
├── requirements.txt                  # Python dependencies
├── data/
   ├── orbital_data.dat             # S2 astrometry (VLT, NTT, Keck)
   ├── radial_velocity_data.dat     # S2 radial velocities
   └── ReadMe.txt                   # Data format documentation

```

## Installation & Setup

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook or JupyterLab
- Anaconda (recommended)

### Install Dependencies

```bash
pip install -r requirements.txt
```

Or with conda:

```bash
conda install numpy matplotlib scipy astropy
conda install jupyter
```

### Required Packages

- `numpy` - Numerical computations
- `matplotlib` - Plotting and visualization
- `scipy` - Optimization (`curve_fit` for non-linear least squares)
- `astropy` - Astronomical data handling, units, and constants

## Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/JacobParzych/Astron_1221_Project_3.git
   cd Astron_1221_Project_3
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook Project3_Parzych_Jamison.ipynb
   ```

4. Run all cells sequentially (Kernel → Restart & Run All)

## Analysis Workflow

### Standard Analysis (Sections 1-8)

1. **Data Loading:** Import S2 astrometric data from Keck telescope
2. **Orbit Modeling:** Implement Keplerian orbit equations from scratch
3. **Parameter Fitting:** Use `scipy.optimize.curve_fit` to fit 7 orbital parameters
4. **Mass Calculation:** Apply Kepler's Third Law to determine M_BH
5. **Visualization:** Plot best-fit orbit, data, and residuals

### Advanced Analysis (Section 9)

6. **Radial Velocity:** Load spectroscopic velocity data
7. **Combined Fitting:** Simultaneously fit astrometry + RV with 8 parameters
8. **Distance Measurement:** Break mass-distance degeneracy by including R₀
9. **Limitations:** Discuss systematic errors and data quality issues

## Data Sources

- **Astrometry:** VizieR catalog (Gillessen et al. 2009, ApJ, 692, 1075)
  - 3 telescopes: VLT, NTT, Keck
  - This analysis uses Keck-only data (26 epochs, 1995-2008)
  
- **Radial Velocity:** Same source (13 epochs, 2000-2007)

Data was manually downloaded from VizieR and formatted for this project.

## Technical Implementation

### Custom Model Functions

All model functions were implemented from scratch using `scipy.optimize`:

- `solve_kepler(M, e)` - Newton-Raphson solver for Kepler's equation
- `keplerian_orbit_2d(t, ...)` - 6-step orbital calculation
- `orbit_model_xy(t, ...)` - Wrapper for curve_fit
- `radial_velocity_model(t, ...)` - RV prediction from orbital elements
- `combined_model(t, ...)` - Simultaneous astrometry + RV fitting

### Statistical Analysis

- **Chi-squared minimization** via non-linear least squares
- **Covariance matrix** for parameter uncertainties
- **Reduced χ²** for goodness-of-fit assessment
- **Residual analysis** to identify systematic errors

## Key Features

 **Custom fitting implementation** - No pre-built orbit fitting packages  
 **Real astronomical data** - Keck telescope observations  
 **Physical interpretation** - Connects fitted parameters to astrophysics  
 **Error propagation** - Proper uncertainty estimation  
 **Professional visualization** - Publication-quality plots  
 **Pedagogical documentation** - Clear explanations throughout  

## Limitations & Future Work

This educational analysis has several limitations compared to professional measurements:

1. **Ground-based astrometry** - Limited precision (~1 mas)
2. **Incomplete phase coverage** - Only 13 years of 16-year orbit
3. **Simplified model** - No relativistic corrections
4. **Single star analysis** - Professional work uses multiple S-stars

Modern measurements (GRAVITY collaboration) achieve ~10 μas precision using infrared interferometry, enabling tests of General Relativity.

## References

- Ghez et al. (2008) - "Measuring Distance and Properties of the Milky Way's Central Supermassive Black Hole with Stellar Orbits"
- Gillessen et al. (2009) - "Monitoring Stellar Orbits Around the Massive Black Hole in the Galactic Center" (ApJ, 692, 1075)
- GRAVITY Collaboration (2018) - "Detection of the gravitational redshift in the orbit of the star S2 near the Galactic centre massive black hole"
- Nobel Prize (2020) - Andrea Ghez & Reinhard Genzel

## License

This project was created for educational purposes as part of Astronomy 1221 at The Ohio State University.

## Acknowledgments

- **Instructor:** Yuan-Sen Ting
- **Data Source:** VizieR Astronomical Database
- **Nobel Laureates:** Andrea Ghez & Reinhard Genzel for inspiring this work

---

**GitHub Repository:** https://github.com/JacobParzych/Astron_1221_Project_3