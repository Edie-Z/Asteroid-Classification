# Asteroid Classification Project

## Overview

This project uses **Particle Swarm Optimization (PSO)** to tune a **Support Vector Classifier (SVC)** model, achieving high accuracy in asteroid classification and identifying potentially hazardous asteroids.

- **Dataset**: [Asteroid Dataset on Kaggle](https://www.kaggle.com/datasets/sakhawat18/asteroid-dataset/data)
- **Reference Notebook**: [Asteroid Prediction by Marissa Fernandes](https://www.kaggle.com/code/marissafernandes/asteroid-prediction)

## Project Structure

.
├── AsteroidClassification_PSO-SVR.ipynb   # Main notebook with analysis and model  
├── dataset.csv                            # Primary dataset  
├── Classification.csv                     # Classification results  
├── ObjectInfo.csv                         # Object-specific information  
├── OrbitParameters.csv                    # Orbital parameters  
├── PhysicalCharacteristics.csv            # Physical characteristics data  
└── README.md                              # Project documentation

### Key Files

- **`AsteroidClassification_PSO-SVR.ipynb`**: 
  - Notebook containing data exploration, cleaning, hypothesis, preprocessing, model training and evaluation.

- **`dataset.csv`**: 
  - Primary dataset used for model training and testing.
 
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

## Analysis and Methodology

### 1. Data Exploration and Cleaning
   - Detailed exploration of dataset features and handling of missing values.

### 2. Hypothesis
   - Analysis and visualization to explore five hypotheses, including:
     - **PHA Status and Absolute Magnitude (H)**: PHAs tend to have lower H values.
     - **NEO Status and Perihelion Distance (q)**: A smaller q increases Earth-encounter likelihood.
     - **Minimum Orbit Intersection Distance (moid_ld) and PHA Status**: Smaller moid_ld correlates with PHA classification.
     - **Eccentricity (e) and NEO Status**: Higher eccentricity correlates with NEO status.
     - **Orbital Inclination (i) and NEO Status**: NEOs tend to have lower orbital inclinations.

### 3. Data Preprocessing
   - Standardization of features and handling class imbalance via under-sampling.

### 4. Correlation Analysis
   - Performed feature correlation analysis using Maximal Information Coefficient (MIC), with interpretation of MIC ranges:
     - **0.0 - 0.1**: Almost no correlation.
     - **0.1 - 0.3**: Weak correlation.
     - **0.3 - 0.5**: Moderate correlation.
     - **0.5 - 0.7**: Strong correlation.
     - **0.7 - 1.0**: Very strong correlation.

### 5. Model Training and Evaluation

   - **Model**: Support Vector Classifier (SVC) with Radial Basis Function (RBF) kernel.
   - **Optimization**: Implemented Adaptive Discrete Quantum Particle Swarm Optimization (ADQPSO) to optimize `C` and `gamma` parameters, leveraging 5-fold cross-validation.
   - **Performance**: Model achieved high classification accuracy, with results indicating strong precision and recall for classification.

### 6. Evaluation and Visualization
   - **Metrics**: Accuracy, F1 Score, and detailed classification report.
   - **Visualizations**: Confusion matrix, ROC curve, and precision-recall curves to assess model performance.

## Results

Using PSO-optimized SVC, this project successfully classifies asteroids with high accuracy, achieving over 99% test accuracy. The model effectively differentiates PHAs, making it a valuable tool for asteroid risk assessment.
