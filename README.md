# Shear-Wave-Velocity-Prediction

Physics-Informed Machine Learning for Shear Wave Velocity Prediction
This repository contains the code and workflow for predicting shear wave velocity (Vs) from conventional well log data using a physics-informed machine learning approach. The project's main goal is to build a model that is not only accurate but also geologically consistent, leveraging rock physics principles to guide the machine learning process.

📖 Project Overview
Predicting shear wave velocity (Vs) is essential for seismic interpretation, reservoir characterization, and geomechanical studies. However, Vs logs are often unavailable due to the cost and difficulty of acquisition. This project addresses this challenge by training a machine learning model to predict Vs using more common well logs (e.g., compressional velocity, density, gamma-ray, neutron porosity).

The key innovation here is the physics-informed methodology. Instead of treating the problem as a purely statistical "black-box" exercise, we integrate domain knowledge from rock physics. This ensures the model's predictions adhere to known physical laws and geological constraints, making the results more robust and reliable.

Furthermore, we use SHAP (SHapley Additive exPlanations) to interpret the final model. This allows us to verify that the model is learning physically meaningful relationships between the input logs and the predicted shear wave velocity.

🔬 Methodology
The workflow is designed to ensure the final model is both accurate and geologically sound. It follows these key steps:

Data Ingestion & QC: Well log data from multiple wells (Bangora-1 and Bangora-4) in Log ASCII Standard (LAS) format is loaded, merged, and quality-controlled to handle missing values and outliers.

Rock Physics Analysis: Before machine learning, a preliminary analysis based on rock physics is performed. This may involve cross-plotting logs to identify trends and applying empirical relationships (e.g., Castagna's mudrock line) to establish a baseline understanding of the data.

Machine Learning Modeling: A robust machine learning model (such as a Gradient Boosting Regressor) is trained on a set of input logs to predict the target shear wave velocity.

Physics-Informed Interpretation with SHAP: This is the critical step. After training, SHAP is used to explain the model's predictions. We analyze the SHAP plots to confirm the model has learned correct physical relationships, for example:

Does an increase in density (RHOB) and compressional velocity (Vp) lead to an increase in the predicted shear velocity (Vs)?

How does the model treat changes in clay content (indicated by Gamma Ray)?
This step validates that the model is not just fitting noise but has captured the underlying petrophysical drivers of shear wave velocity.

✨ Key Features
Shear Wave Velocity Prediction: The primary focus is on accurately estimating a critical elastic parameter.

Physics-Informed Approach: Integrates rock physics principles to guide model development and ensure geologically plausible results.

Explainable AI (XAI): Uses the shap library to provide transparent, physically-meaningful insights into the model's behavior.

Multi-Well Analysis: Aggregates data from multiple wells to build a more generalized and robust predictive model.

Comprehensive Visuals: Combines traditional log plots with advanced SHAP visualizations for a complete analysis.

🛠️ Technologies & Libraries Used
lasio: For reading and writing Log ASCII Standard (LAS) files.

pandas & numpy: For data manipulation and numerical computation.

matplotlib: For creating high-quality data visualizations.

scikit-learn: For machine learning model training and data preprocessing.

shap: For explaining the output of the machine learning model.
