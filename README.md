
# EquiP: Machine Learning Model for Predicting Equilibrium Plateau Pressure of Metal Composition

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Project Overview

Metal hydrides play a pivotal role in a wide range of technologies, including hydrogen storage, compression, heat management, and catalysis. Their performance is fundamentally governed by the thermodynamics of metal–hydrogen interactions, which determine key operational condition of these systems. One of the most critical thermodynamic parameters is the equilibrium plateau pressure (P<sub>eq</sub>), it defines the conditions under which hydrogen absorption and desorption occur, directly influencing the temperature and pressure ranges suitable for system operation. Traditionally, determining P<sub>eq</sub> requires extensive experimental measurements, creating a bottleneck in the pace of materials discovery and optimization.

🧠 Introducing EquiP

EquiP is a machine learning framework designed to predict the ln(P<sub>eq</sub>) (in MPa) of metal hydrides as a function of temperature. Rather than providing only single-point predictions, EquiP generates complete Van’t Hoff plots (P<sub>eq</sub> vs. 1/T), enabling rapid estimation of key thermodynamic parameters: ΔH (enthalpy of hydride formation) and ΔS (entropy of hydride formation)
```
EquiP/
│
├── data/
│   ├── EQUIP_Input.csv          # Main dataset (composition, features, target)
│   ├── EQUIP_Input_Mg.csv            # Optional Mg-based subset for focused tests
│
├── model/
│   ├── EquiP_Traning.ipynb        # Main ML workflow script (KRR training + Validation + SHAP + LOCO)
│   ├── EquiP_Mg_XRD_Model.ipynb   # Model trained only on Mg-based compositions with XRD information
│
├── output/
│   ├── parity_plot.png            # Predicted vs Experimental ln(Peq)
│   ├── shap_summary.png           # SHAP feature importance summary
│   ├── loco_results.csv           # Leave-One-Composition-Out (LOCO) validation
│   ├── results_summary.txt        # Model performance report
│
├── README.md                      # Project documentation (this file)
├── requirements.txt               # Python dependencies
└── LICENSE                        # License file (e.g., MIT or CC BY 4.0)
```
⚙️ Installation
1. Clone the repository

    git clone https://github.com/ashwinidverma/EquiP.git

    cd EquiP

2. Create a virtual environment

    python -m venv venv

    source venv/bin/activate      # (or venv\Scripts\activate on Windows)


3. Install dependencies

   pip install -r requirements.txt


🚀 Usage

Run the main model

To train and evaluate EquiP: python model/EquiP_Traning.ipynb

To train and evaluate Mg-EquiP with XRD: python model/EquiP_Mg_XRD_Model.ipynb 


This script:

Loads and preprocesses the dataset

Trains a Kernel Ridge Regression (KRR) model with RBF kernel

Generates parity and SHAP plots

Performs cross-validation and LOCO tests

Saves all outputs in the output/ folder

🧠 Key Features

  Experimental Dataset: consisting of 293 data points extracted from Van't Hoff plots of 77 compositions.
  
  Feature Set: Includes temperature, elemental, and hydriding features (e.g., Ehyd, ΔEN, ΔVol, etc.)

  Thermodynamic consistency: Model predictions can reproduce ΔH and ΔS from Van’t Hoff behavior.

  LOCO validation: Evaluate model reliability for unseen compositions.

  Interpretability: SHAP analysis provides insight into which features most strongly affect P<sub>eq</sub>.

📈 Results & Insights

Comparative analyses demonstrate that incorporating domain-informed features and structural descriptors significantly improves model performance. Even with limited data, intelligen feature design grounded in domain knowledge enables improved predictions of complex material properties.

🧩 Citation

If you use EquiP or its dataset in your research, please cite:
“What drives property prediction for solid-state hydrogen storage? Data or smart features?”
A. Verma and K. Joshi (2025)

## Contact / Collaboration

For questions, feedback, or collaboration, feel free to reach out:

- **Email:** ashwini.dverma@gmail.com  
- **LinkedIn:** [Ashwini Verma](https://www.linkedin.com/in/ashwinidverma/)  

You are also welcome to open issues or pull requests directly on this repository for feedback or improvements.



