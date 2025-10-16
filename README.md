
# EquiP: Machine Learning Model for Predicting Equilibrium Plateau Pressure of Metal Composition

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Project Overview

EquiP: Machine Learning Model for Predicting Equilibrium Plateau Pressure in Metal Hydrides
EquiP is a machine learning framework developed to predict the equilibrium plateau pressure ($𝑃_{eq}$) as function of temperature metal composition.
The model is trained on experimental data and its leverages domain-informed descriptors, including elemental, compositional, and hydriding properties of constituent elements to learn the thermodynamics of metal–hydrogen systems.
Hydrogen storage materials are typically evaluated through experimental Pressure–Composition–Temperature (PCT) measurements, which are resource-intensive and time-consuming.
EquiP provides a data-driven alternative by learning from experimentally derived Van’t Hoff relationships to predict ln($𝑃_{eq}$) directly, enabling rapid estimation of thermodynamic parameters (ΔH and ΔS).
```
EquiP/
│
├── data/
│   ├── EQUIP_Input.csv          # Main dataset (composition, features, target)
│   ├── EquiP_Mg_Input.csv              # Optional Mg-based subset for focused tests
│
├── model/
│   ├── model.py                   # Main ML workflow script (KRR training + SHAP)
│   ├── utils.py                   # Helper functions (feature processing, metrics)
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

To train and evaluate the model: python model/model.py


This script:

    Loads and preprocesses the dataset

    Trains a Kernel Ridge Regression (KRR) model with RBF kernel

    Performs cross-validation and LOCO tests

    Generates parity and SHAP plots

    Saves all outputs in the output/ folder

🧠 Key Features

  Physically informed descriptors:

      Includes temperature, elemental, and hydriding features (e.g., Ehyd, ΔEN, ΔVol, etc.)

  Thermodynamic consistency:

       Model predictions can reproduce ΔH and ΔS from Van’t Hoff behavior.

  LOCO validation:

      Ensures model reliability for unseen compositions.

  Interpretability:

       SHAP analysis provides insight into which features most strongly affect 𝑃eqP

🧩 Citation

If you use EquiP or its dataset in your research, please cite:
“What drives property prediction for solid-state hydrogen storage? Data or smart features?”
A. Verma, K. Joshi et al., 2025.

## Contact / Collaboration

For questions, feedback, or collaboration, feel free to reach out:

- **Email:** ashwini.dverma@gmail.com  
- **LinkedIn:** [Ashwini Verma](https://www.linkedin.com/in/ashwinidverma/)  

You are also welcome to open issues or pull requests directly on this repository for feedback or improvements.



