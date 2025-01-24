# Maritime Hackathon 2025: Reducing Subjectivity in PSC Severity Scores with AI

This repository contains the methodology and implementation details for the **Maritime Hackathon 2025** project, which focuses on reducing subjectivity in predicting severity scores of **Port State Control (PSC)** inspections using **Generative AI (GenAI)** and **AutoML**.

## Abstract

Port State Control (PSC) inspections are critical for maritime safety and compliance, but the evaluation process is often subjective, leading to operational inefficiencies and potential safety risks. This project outlines a structured methodology to evaluate severity levels from PSC inspection findings using **Generative AI** augmented through **prompt engineering** and **chain-of-thought reasoning**. The approach provides a second opinion to severity scores, balancing human subjectivity. The **AutoGluon** AutoML framework was used for predictive modeling, ensuring consistent, less biased, and scalable severity evaluations.

## Methodology

### 1. Data Preparation
- **Raw Data**: The dataset `psc_severity_train` was preprocessed by removing irrelevant columns (`annotation_id`, `username`, `InspectionDate`).
- **Feature Extraction**: Key features such as `PscInspectionId`, `Deficiency/Finding`, `Description Overview`, `Immediate Causes`, `Root Cause Analysis`, `Corrective Action`, `Preventive Action`, and `Deficiency Code` were extracted.
- **Encoding**: The `annotated_severity` column was encoded to numerical values: 0 (LOW), 1 (MED), and 2 (HIGH).

### 2. Augmenting Data with AI Evaluation
- **AI Model**: A **Large Language Model (LLM)** based on Google’s **FLAN-T5** was used to generate unbiased severity scores.
- **Prompt Engineering**: Zero-shot **chain-of-thought reasoning** was implemented to reduce AI hallucination and ensure rational outputs.
- **Synthetic Data**: The AI-generated severity scores added **4,364 synthetic samples** to the dataset, improving its diversity and representativeness.

### 3. Model Training
- **AutoGluon**: The feature-engineered data was fed into **AutoGluon**, an AutoML framework, which automated feature engineering, model selection, and hyperparameter tuning.
- **Best Model**: The **CatBoost** model achieved the best performance with a **roc_auc_ovo score of 0.768** and an **accuracy of 0.640**.

### 4. Test Set Prediction
- The best trained **CatBoost** model was used to predict severity scores on the test set.

## Rules and Assumptions
- **Mean Aggregation**: Severity levels were aggregated using the mean of **Subject Matter Expert (SME)** and AI-provided scores.
- **Synthetic Data Assumptions**: AI-generated severity scores were assumed to be equivalent to those provided by SMEs.
- **Inspector Expertise**: Inspectors were assumed to adhere to standard industry practices and guidelines.

## Results and Discussion
- **Model Performance**: The integration of generative AI and AutoGluon resulted in a robust model with an **overall roc_auc score of 0.768**.
- **Data Augmentation**: The addition of **4,364 synthetic samples** enhanced the model's reliability and demonstrated the importance of diverse data sources in vessel evaluations.

## Conclusion
This project developed a **dependable framework** for evaluating consensus severity in PSC inspections by leveraging **generative AI** for unbiased data synthesis and **AutoGluon** for automated machine learning. The approach has significant potential to improve objectivity and consistency in vessel surveys, supporting the maritime industry's operational and commercial objectives.

## Contributors
- **Curtcis Yang**
- **Dong Luanjie**
- **Ho Min Han**

