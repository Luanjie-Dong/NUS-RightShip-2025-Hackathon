# Maritime Hackathon 2025: Reducing Subjectivity in PSC Severity Scores with AI


## Overview
This repository contains the methodology and implementation details for the Maritime Hackathon 2025 project, which focuses on reducing subjectivity in classification of severity level of Port State Control (PSC) ship inspections using Generative AI (GenAI) and AutoML.

## Features
| Feature | Description | Status |
|---------|-------------|--------|
| **Ship condition classification** | Classifies the condition of the ship based on engineer's comment | ✅ Implemented |
| **AI-Augmented Severity data** | Uses Generative AI with prompt engineering and chain-of-thought reasoning to provide a second opinion on PSC inspection severity scores. | ✅ Implemented |


## Technical Implementations
- **Data Preparation and Feature Extraction** - [View Code](https://github.com/Luanjie-Dong/NUS-RightShip-2025-Hackathon/blob/main/MaritimeHackathon2025_Script%3ANotebook.ipynb)
  - Preprocesses the raw data by removing irrelevant columns and extracts key features such as PscInspectionId, Deficiency/Finding, and others for model training.

- **AI-Driven Severity Score Generation** - [View Code](https://github.com/Luanjie-Dong/NUS-RightShip-2025-Hackathon/blob/main/MaritimeHackathon2025_Script%3ANotebook.ipynb)
  - implements a Large Language Model (LLM) based on Google’s FLAN-T5 to generate unbiased severity scores using zero-shot chain-of-thought reasoning.

- **Classification Mode Training and Prediction** - [View Code](https://github.com/Luanjie-Dong/NUS-RightShip-2025-Hackathon/blob/main/MaritimeHackathon2025_Script%3ANotebook.ipynb)
  - Utilizes AutoGluon AutoML framework to train and optimize the best model (CatBoost) for predicting severity scores on the test set.



## Running the Application
Follow these steps to run the application:

1. **Data Preparation**
    - Preprocess the psc_severity_train dataset by removing irrelevant columns. Extract features like PscInspectionId, Deficiency/Finding, etc. Encode the annotated_severity column to numerical values (0, 1, 2).

2. **AI Evaluation and Augmentation**
    - Use the FLAN-T5 based LLM to generate severity scores. Implement prompt engineering and chain-of-thought reasoning. Add the synthetic data to the existing dataset.

3. **AI Evaluation and Augmentation**
    - Feed the feature-engineered data into AutoGluon. Train the CatBoost model, and use it to predict severity level on the test set.
      
## Contributors
- **Curteis Yang**
- **Dong Luanjie**
- **Ho Min Han**


