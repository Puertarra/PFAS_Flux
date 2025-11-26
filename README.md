# PFAS Landfill Emissions Analysis (Sites L19 and L26)

Tools for simulating, analyzing, and mapping landfill methane (CH₄) and PFAS emissions using synthetic receptor grids, Gaussian dispersion, and geospatial hulls.

## Overview

This repository contains a Jupyter-based workflow for a comprehensive analysis of **Per- and Polyfluoroalkyl Substances (PFAS)** emissions from two landfill sites, referred to as **L19** and **L26**, and evaluates the associated environmental and public health risks. The analysis uses atmospheric dispersion modeling to simulate how PFAS compounds spread through the environment under various meteorological conditions.

The codebase also includes utilities to generate synthetic receptor measurements, compute fluxes and emission rates, apply quartile-based spatial analysis, convert model coordinates to geographic latitude/longitude, and visualize results on interactive web maps.

## Key Components

### 🎯 Objectives

- Estimate PFAS emission rates from landfill sources.
- Model atmospheric dispersion patterns using Gaussian plume theory.
- Assess concentration levels at receptor points within surrounding communities.
- Evaluate public health risks through spatial and temporal analysis.
- Generate interactive visualizations and maps for stakeholder communication.

### 📊 Data Sources

- **Convex hull coordinates** for L19 and L26: Define landfill boundaries and study areas.
- **Weather data**: Wind speed, direction, and atmospheric stability classes.
- **Emission parameters**: PFAS and methane concentrations, background levels.
- **Geographic landmarks**: Schools, hospitals, shopping centers, and other points of interest.

## Methodology

### 🔬 Core Modeling

- **Gaussian Plume Modeling**  
  Calculates pollutant concentrations using meteorological data and standard dispersion formulations.

- **Receptor Grid Generation**  
  Creates synthetic monitoring points across each study area to approximate a dense sensor network.

- **Source–Receptor Analysis**  
  Models emissions from multiple point sources within each landfill and links them to receptor concentrations.

- **Coordinate Transformations**  
  Converts between local Cartesian coordinates (x, y in meters) and geographic coordinates (lat, lon) using site-specific centroids and linearized metric–degree factors.

- **Risk Assessment**  
  Evaluates exposure levels relative to background concentrations, supporting qualitative and semi-quantitative risk characterization.

### 📈 Analysis Features

- Daily concentration mapping under varying weather conditions.
- Wind-aligned coordinate system for accurate dispersion modeling.
- Statistical analysis of concentration distributions (quartiles, spatial patterns).
- Interactive **Folium** maps with overlays for:
  - Convex hulls of L19 and L26.
  - Emission sources and receptor points.
  - Community landmarks and other features of interest.
- Time-series visualization of atmospheric conditions.
- Convex hull boundary validation to ensure receptors lie within the modeled domain.

## Geospatial and Hull Utilities

The repository includes tools to:

- Read convex hull coordinates for **L19** and **L26** from spreadsheet files.
- Export hulls as `numpy` arrays for use in modeling and plotting.
- Overlay hulls on:
  - Matplotlib figures (concentration fields, source locations).
  - Folium web maps for interactive inspection.
- Compare model-derived hulls with externally defined polygons (e.g., from GIS/KML/GeoJSON sources).

## Visualization Outputs

### 🗺️ Maps and Plots

- Concentration contour maps for different meteorological scenarios.
- Interactive web maps (Folium) with:
  - Emission sources.
  - Receptor grids.
  - Landfill hulls (L19 and L26).
  - Community landmarks and distance rings (e.g., 1 km, 2 km, 3 km).
- Receptor grid layouts showing spatial sampling distribution.
- Wind roses and basic atmospheric stability diagnostics.
- Statistical summaries and exposure risk assessments.

## Applications

### 💡 Use Cases

- Environmental impact assessment for landfill operations.
- Public health risk communication and community engagement.
- Regulatory compliance and emission monitoring planning.
- Site management and mitigation strategy development.
- Scientific research on PFAS fate, transport, and co-emitted methane.

## Repository Structure (Indicative)

- `notebooks/`  
  Jupyter notebooks implementing the main PFAS and methane analysis for L19 and L26.

- `data/`  
  Input data files (convex hull tables, weather data, parameter JSON, landmarks).

- `src/`  
  Python modules for:
  - Gaussian dispersion calculations.
  - Synthetic receptor grid generation.
  - Coordinate transformations (`xy_to_latlon`, etc.).
  - JSON export of parameters and results.
  - Mapping utilities with Matplotlib and Folium.

- `README.md`  
  Project overview, methodology, and usage notes.

---


**Note**: This analysis integrates atmospheric science, environmental chemistry, and public health methodologies to provide a comprehensive assessment of PFAS and methane emissions from landfills L19 and L26, and their potential impact on surrounding communities.
