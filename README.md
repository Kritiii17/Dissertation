# Hybrid DSM–DTM Pipeline for Volcanic Hazard Modelling
This repository accompanies the MSc dissertation submitted to the University of Bristol (2025).
 
**"Automating pre-processing of digital elevation maps for volcanic hazard modelling"**  
by Kriti Garg


## Overview
Volcanic flows such as lahars, debris flows, and pyroclastic density currents are strongly controlled by surface topography.  
Accurate terrain models are therefore essential for hazard simulation.  

UAV-derived Digital Surface Models (DSMs) capture vegetation, buildings, and vehicles that distort terrain and create artificial barriers to flow.  
This project develops an automated **hybrid DSM–DTM pipeline** that combines deep learning (lightweight U-Net segmentation) and GIS-based filtering (VegBoost SAFE Hybrid method) to remove canopy artefacts and reconstruct bare-earth terrain.  

The workflow was tested on **La Gasca (Ecuador)** and **Chosica (Peru)**, demonstrating improved drainage representation, corrected artefact-driven ponding, and better hazard simulation outcomes.


## Features
- **Preprocessing**: raster alignment, tiling, vegetation indices  
- **Training**: lightweight U-Net segmentation (RGB + DSM input)  
- **Inference**: tile predictions, stitching, hybrid filtering  
- **Postprocessing**: artefact removal, interpolation, VegBoost refinement  
- **Validation**: hillshades, elevation profiles, difference maps, hazard simulations (Kestrel)  


## Data Access
Due to GitHub storage limits, full datasets and outputs are hosted on Google Drive:  

[Google Drive Folder](https://drive.google.com/drive/u/1/my-drive)  

### Contents
- **Folder Project - Contains data for La Gasca (Ecuador)**  
  - DEM, Orthoimagery (raw & aligned), Woodland shapefile (raw & aligned) 
  - Outputs folder - Training previews & Hybrid DSM–DTM outputs  
  - Tiles folder - inputs, masks & prediction tiles
  - Checkpoints - model's best trained path
- **Folder Chosica - Contains data for Chosica (Peru)**  
  - DEM, Orthoimagery (raw & aligned), Prediction Mask (raw & cleaned)
  - Tiles folder - inputs & prediction tiles 
  - Outputs folder - Hybrid DSM-DTM outputs
    
- **Folder Colab Notebooks**  
  - Lagasca.ipynb - python notebook with complete code used for creating this pipeline.
  - Chosica.ipynb - python notebook to test the generalization of model at Chosica site.


## Installation

### PIP
pip install -r requirements.txt

### Conda
```bash
conda env create -f environment.yml
conda activate hybrid-dtm

