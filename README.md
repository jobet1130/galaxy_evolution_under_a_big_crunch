# Galaxy Evolution Under a Big Crunch

[![Python 3.12+](https://img.shields.io/badge/python-3.12+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

A computational astrophysics project simulating and analyzing galaxy evolution in a hypothetical Big Crunch cosmological scenario using N-body simulations and data science techniques.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Example Visualizations](#example-visualizations)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Overview

The Big Crunch is a theoretical scenario for the ultimate fate of the universe, where the expansion of the universe eventually reverses, causing galaxies to merge and the universe to collapse. This project explores how galaxies might evolve under such conditions, focusing on:

- N-body simulations of galactic interactions
- Analysis of star formation rates and metallicity evolution
- Dark matter halo dynamics in collapsing universes
- Comparison with ΛCDM cosmology predictions

## Features

- **Cosmological Modeling**

   - Custom Friedmann equation solvers
   - Scale factor evolution in various cosmological models
   - Dark energy and matter density parameter analysis

- **N-body Simulations**

   - Gravitational interaction modeling
   - Star formation and feedback processes
   - Gas dynamics and cooling mechanisms

- **Data Analysis**

   - Halo finding and characterization
   - Merger tree construction
   - Kinematic and photometric analysis

- **Visualization**

   - 3D interactive galaxy visualization
   - Time evolution animations
   - Phase-space diagrams and radial profiles

## Project Structure

```ini
galaxy-bigcrunch/
├── data/                # Data storage
│   ├── raw/            # Raw simulation outputs
│   ├── processed/      # Cleaned and processed data
│   └── external/       # External datasets (Illustris, TNG, etc.)
├── docs/               # Documentation and research papers
├── notebooks/          # Jupyter notebooks for analysis
├── results/            # Outputs from analysis
│   ├── figures/        # Generated plots and visualizations
│   ├── videos/         # Simulation animations
│   └── reports/        # Generated reports
├── src/                # Source code
│   ├── simulations/    # N-body simulation code
│   ├── cosmology/      # Cosmological calculations
│   ├── analysis/       # Data processing and analysis
│   ├── visualization/  # Plotting and visualization tools
│   └── utils/          # Helper functions
├── tests/              # Unit and integration tests
├── configs/            # Configuration files
├── environment/        # Environment setup files
├── pyproject.toml      # Project metadata and dependencies
└── README.md           # This file
```

## Installation

### Prerequisites

- Python 3.12 or higher
- C/C++ compiler (for some numerical packages)
- Git

### Using pip

1. Clone the repository:

```bash
git clone https://github.com/jobet1130/galaxy_evolution_under_a_big_crunch.git
cd galaxy_evolution_under_a_big_crunch
```

2. Create and activate a virtual environment (recommended):

```bash
# On Windows
python -m venv .venv
.\venv\Scripts\activate

# On Unix/macOS
python3 -m venv venv
source venv/bin/activate
```

3. Install the package in development mode with all dependencies:

```bash
pip install -e ".[dev]"
```

### Using Poetry

1. Install Poetry if you haven't already:

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

2. Install dependencies:

```bash
poetry install --with dev
```

## Usage

### Running Simulations

```python
from src.simulations import BigCrunchSimulation

# Initialize simulation with custom parameters
sim = BigCrunchSimulation(
    n_particles=10000,
    box_size=100,  # Mpc/h
    omega_m=1.2,   # Matter density parameter
    h=0.7         # Hubble parameter
)

# Run the simulation
sim.run(steps=1000)
```

### Data Analysis

```python
from src.analysis import GalaxyAnalyzer
from src.visualization import plot_galaxy_evolution

# Load simulation data
analyzer = GalaxyAnalyzer("data/processed/simulation_001.h5")

# Analyze star formation history
sfr = analyzer.calculate_sfr()

# Visualize results
plot_galaxy_evolution(sfr, output="results/figures/sfr_evolution.png")
```

## Example Visualizations

### Galaxy Merger in a Collapsing Universe

![Galaxy Merger](results/figures/merger_simulation.png)
_Simulation of two galaxies merging during the Big Crunch collapse._

### Dark Matter Halo Evolution

![Halo Evolution](results/figures/halo_evolution.gif)
_Time evolution of dark matter halos in the collapsing phase._

## Roadmap

### Short-term Goals

- [ ] Implement basic N-body simulation with gravity
- [ ] Add gas dynamics and star formation recipes
- [ ] Create visualization tools for simulation outputs

### Medium-term Goals

- [ ] Implement parallel processing for larger simulations
- [ ] Add support for different dark energy models
- [ ] Develop machine learning models for galaxy classification

### Long-term Goals

- [ ] Full cosmological hydrodynamical simulations
- [ ] AI-based prediction of galaxy evolution paths
- [ ] Web-based interactive visualization platform

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup

1. Install development dependencies:

```bash
pip install -e ".[dev]"
```

2. Run tests:

```bash
pytest
```

3. Format code:

```bash
black .
isort .
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

### Data Sources

- [IllustrisTNG](https://www.tng-project.org/)
- [Millennium Simulation](https://wwwmpa.mpa-garching.mpg.de/millennium/)
- [Planck Legacy Archive](https://pla.esac.esa.int/)

### Software & Libraries

- [Astropy](https://www.astropy.org/)
- [Nbodykit](https://nbodykit.readthedocs.io/)
- [GADGET-2](https://wwwmpa.mpa-garching.mpg.de/gadget/)
- [PyTorch](https://pytorch.org/)
- [Matplotlib](https://matplotlib.org/)

### Research Papers

- Springel et al. (2005) - "Simulations of the formation, evolution and clustering of galaxies and quasars"
- Vogelsberger et al. (2014) - "Introducing the Illustris project"
- Planck Collaboration et al. (2020) - "Planck 2018 results. VI. Cosmological parameters"

---

Project created by [Jobet P. Casquejo](mailto:jobetcasquejo221@gmail.com)
