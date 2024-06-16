# DataHack-by-IIT-Guwahati

------------------------

## Notebook 1 - SVM: Predicting Vaccine Likelihood

### Objective
In this notebook, we aim to predict the likelihood of individuals receiving two types of vaccines: the xyz flu vaccine and the seasonal flu vaccine. We will utilize the Support Vector Machine (SVM) algorithm for this multilabel classification problem.

### Dataset Overview
The dataset consists of responses from individuals regarding their vaccine status along with several features including demographic information, behavioral patterns, opinions, and medical history. The features and target variables are as follows:

- **Target Variables:**
  - `xyz_vaccine`: Whether the respondent received the xyz flu vaccine (binary: 0 = No, 1 = Yes)
  - `seasonal_vaccine`: Whether the respondent received the seasonal flu vaccine (binary: 0 = No, 1 = Yes)

- **Features:**
  - `xyz_concern`, `xyz_knowledge`, `behavioral_antiviral_meds`, `behavioral_avoidance`, `behavioral_face_mask`, `behavioral_wash_hands`, `behavioral_large_gatherings`, `behavioral_outside_home`, `behavioral_touch_face`
  - `doctor_recc_xyz`, `doctor_recc_seasonal`, `chronic_med_condition`, `child_under_6_months`, `health_worker`, `health_insurance`
  - `opinion_xyz_vacc_effective`, `opinion_xyz_risk`, `opinion_xyz_sick_from_vacc`, `opinion_seas_vacc_effective`, `opinion_seas_risk`, `opinion_seas_sick_from_vacc`
  - `age_group`, `education`, `race`, `sex`, `income_poverty`, `marital_status`, `rent_or_own`, `employment_status`, `hhs_geo_region`, `census_msa`, `household_adults`, `household_children`, `employment_industry`, `employment_occupation`

### Steps Involved
1. **Data Loading**: We start by loading the training and test datasets.
2. **Data Preprocessing**:
   - Handle missing values.
   - Encode categorical variables using OneHotEncoder.
   - Standardize numerical features.
3. **Model Definition**:
   - Create a pipeline that includes preprocessing steps and the SVM classifier.
   - Use `SVC` from `sklearn.svm` with probability estimates enabled.
4. **Model Training and Evaluation**:
   - Split the data into training and validation sets.
   - Train the SVM model on the training set.
   - Evaluate the model using ROC AUC score on the validation set for both target variables.
5. **ROC Curve Plotting**:
   - Generate and plot the ROC curves for visual performance analysis.
6. **Prediction and Submission**:
   - Train the final model on the full training dataset.
   - Generate predictions for the test set.
   - Prepare the submission file in the required format.

### Evaluation Metric
The performance of the model is evaluated using the area under the receiver operating characteristic curve (ROC AUC) for both target variables. The final score is the average of the ROC AUC scores for `xyz_vaccine` and `seasonal_vaccine`.

### Results
The SVM model's performance is assessed based on the ROC AUC scores and the corresponding ROC curves are plotted for better visualization of the model's discriminatory power.

### Conclusion
In this notebook, we successfully applied the SVM algorithm to predict the likelihood of individuals receiving the xyz and seasonal flu vaccines. We also visualized the model's performance using ROC curves and prepared the predictions for submission.
