# Asteroid Classification Project

## Overview

This project focuses on classifying asteroids using PSO-SVR machine learning technique.

Dataset: https://www.kaggle.com/datasets/sakhawat18/asteroid-dataset/data  
Reference: https://www.kaggle.com/code/marissafernandes/asteroid-prediction

## File Structure

The project is organized into the following files and directories:  
.  
├── AsteroidClassification_PSO-SVR.ipynb  
├── dataset.csv  
├── Classification.csv  
├── ObjectInfo.csv  
├── OrbitParameters.csv  
├── PhysicalCharacteristics.csv  
└── README.md  

### Files and Directories

- **`AsteroidClassification_PSO-SVR.ipynb`**: 
  - The main Jupyter Notebook for the project. It includes data exploration, cleaning, hypothesis, preprocessing, and machine learning classification and evaluation.

- **`dataset.csv`**: 
  - The primary dataset used for training and testing machine learning models.
 
## Dataset Details

### Identification Parameters

- **SPK-ID**: Unique identifier used within the NASA/JPL Small-Body Database to identify celestial objects.
- **Object ID**: Internal identifier within the database for the celestial object.
- **Object fullname**: Full name/designation of the object.
- **pdes**: Official primary designation.
- **name**: Official name given by the International Astronomical Union (IAU).

### Classification Flags

- **NEO**: Near-Earth Object (NEO) flag.
- **PHA**: Potentially Hazardous Asteroid (PHA) flag. PHAs are a subset of NEOs with:
  - MOID of less than 0.05 AU.
  - Absolute Magnitude (H) of 22 or less.

### Physical Characteristics

- **H**: Absolute magnitude parameter, a measure of the intrinsic brightness of the object.
- **Diameter**: Estimated diameter of the object (in kilometers).
- **Albedo**: Geometric albedo representing the reflectivity of the object’s surface.
- **Diameter_sigma**: Standard deviation of the diameter, representing the possible range based on observational data.

### Orbital Information

- **Orbit_id**: Identifier for the specific orbital solution.
- **Epoch**: Specific date and time at which the orbital elements are defined.
- **Equinox**: Reference frame used for the orbital elements.
- **e**: Eccentricity, describing the deviation of the orbit from a perfect circle.
- **a**: Semi-major axis, the average distance from the object to the Sun (in AU).
- **q**: Perihelion distance, the closest distance from the object to the Sun (in AU).
- **i**: Inclination, the angle of the orbit's plane relative to the ecliptic plane (in degrees).
- **tp**: Time of perihelion passage, when the object is closest to the Sun.
- **moid_ld**: Minimum Orbit Intersection Distance with Earth, representing the minimum distance between the object's orbit and Earth's orbit (in Earth radii).

## Usage Instructions

**Setup**:
- Clone the repository:
  ```bash
  git clone https://github.com/Edie-Z/Asteroid-Classification.git
  cd Asteroid-Classification
  ```
     
## Contact
For any questions or inquiries, please contact:

Maintainer: YIDI ZHAO  
Email: yidi.zhao@ue-germany.de
