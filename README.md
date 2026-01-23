# Landfill PFAS Emissions Modeling and Spatial Analysis

Tools for simulating, analyzing, and mapping landfill **PFAS (Per- and Polyfluoroalkyl Substances)** emissions using synthetic receptor grids, Gaussian dispersion modeling, and geospatial convex hulls.

## Overview

This repository contains a Jupyter-based analytical workflow for the assessment of **PFAS emissions** from two landfill sites, **L19** and **L26**. The framework combines atmospheric dispersion modeling, synthetic monitoring networks, and geospatial analysis to evaluate spatial exposure patterns and potential environmental and public-health implications under varying meteorological conditions.

The codebase supports the full pipeline from source definition and dispersion modeling to spatial statistics and interactive geovisualization.

## Key Components

### 🎯 Objectives

- Estimate PFAS emission rates from landfill sources.
- Simulate atmospheric dispersion using Gaussian plume theory.
- Quantify PFAS concentrations at synthetic receptor locations.
- Analyze spatial and temporal exposure patterns.
- Produce publication-quality and interactive visualizations for technical and non-technical audiences.

### 📊 Data Sources

- **Convex hull geometries** for landfills L19 and L26 defining modeling domains.
- **Meteorological data**: wind speed, wind direction, and atmospheric stability.
- **Emission parameters**: PFAS source strengths and background concentrations.
- **Geographic landmarks**: schools, residential clusters, services, and other receptors of interest.

## Methodology

### 🔬 Core Modeling

- **Gaussian Plume Dispersion**  
  Computes PFAS ground-level concentrations using standard atmospheric dispersion formulations and site-specific meteorology.

- **Synthetic Receptor Grids**  
  Generates dense spatial sampling networks to approximate monitoring campaigns within landfill boundaries.

- **Source–Receptor Linking**  
  Supports multiple emission sources and evaluates their combined impact at receptor locations.

- **Coordinate Transformations**  
  Converts between local Cartesian coordinates (meters) and geographic coordinates (latitude/longitude) using landfill-specific centroids and linearized projections.

- **Exposure Screening**  
  Compares modeled concentrations against background levels to support qualitative and semi-quantitative exposure interpretation.

### 📈 Analysis Features

- Daily concentration fields under varying weather conditions.
- Wind-aligned reference frames for physically consistent dispersion.
- Quartile-based spatial statistics and hotspot identification.
- Maps including landfill hulls, emission sources, receptor grids, and community landmarks.
- Validation checks ensuring receptors remain within modeled hulls.

## Visualization Outputs

- PFAS concentration heatmaps for multiple meteorological scenarios.
- Interactive maps showing emission sources, receptor grids, landfill boundaries, and distance buffers.
- Receptor layout diagnostics and spatial summaries.
- Tabulated exposure metrics for screening-level assessment.

## Applications

- Environmental impact assessment for landfill operations.
- Public-health exposure screening and community communication.
- Regulatory reporting and emission monitoring design.
- Site management and mitigation planning.
- Research on PFAS fate and atmospheric transport.

## Repository Structure

- `data/`  
  Input datasets (convex hulls, meteorology, parameters, landmarks).

- `src/`  
  Python modules **and Jupyter notebooks** implementing dispersion modeling, receptor generation, coordinate transformations, and mapping utilities for L19 and L26.

- `img/`  
  Generated figures, maps, and visualization outputs.

- `README.md`  
  Project description, methodology, and usage notes.

---

## Quick Start

Follow these steps to get up and running with the PFAS Flux analysis workflow.

### 1. Clone the repository

```bash
git clone https://github.com/Puertarra/PFAS_Flux.git
cd PFAS_Flux
```

### 2. Set up the Python environment
pip install -r requirements.txt

### 3. Prepare input data

Place all required input datasets into the `data/` directory, including:

- Convex hull definitions for landfills **L19** and **L26** (CSV, Excel, or JSON).
- Meteorological data (wind speed, wind direction, stability class).
- PFAS emission parameters and background concentrations.
- Geographic landmarks and auxiliary reference tables.

Ensure that file names, column headers, and coordinate conventions match those expected by the scripts and notebooks located in `src/`.

---

### 4. Run the analyses

All analysis code and Jupyter notebooks are located in the `src/` directory.

To launch a notebook (example for landfill L19):

```bash
jupyter notebook src/PFAS_L19.ipynb
```
Within each notebook, the typical workflow includes:

- Loading and validating input data.
- Generating synthetic receptor grids inside landfill hulls.
- Configuring Gaussian dispersion parameters.
- Running PFAS dispersion simulations.
- Computing spatial statistics and exposure metrics.
- Producing static and interactive visualizations.

### 5. View outputs

Static figures (PNG) are saved in the img/ directory.