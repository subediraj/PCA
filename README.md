BRFSS Health Data Analysis

Overview

This repository contains the analysis of health-related variables from the Behavioral Risk Factor Surveillance System (BRFSS) 2023 dataset. The BRFSS employs a complex sampling design to ensure state-level representativeness. From the available 350 variables, we selected 26 health-related variables based on specific criteria.

Selected Variables

The selected variables were categorized into five groups, ensuring that each had less than 10% missing data:

1. Health Status (3 variables):

• General health (GENHLTH)

• Physical health days (PHYSHLTH)

• Mental health days (MENTHLTH)

2. Chronic Conditions (11 variables):

• High blood pressure

• Cholesterol check

• Heart attack

• Coronary heart disease

• Stroke

• Asthma

• COPD

• Depression

• Kidney disease

• Arthritis

• Diabetes

3. Health Behaviors (3 variables):

• Exercise

• Smoking history

• E-cigarette use

4. Healthcare Access (3 variables):

• Personal doctor

• Cost barriers to care

• Routine checkup

5. Disability/Function (6 variables):

• Hearing difficulties

• Vision difficulties

• Cognitive difficulties

• Mobility difficulties

• Self-care difficulties

• Independent living difficulties

All variables were standardized to have a mean of 0 and a standard deviation of 1.

Principal Component Analysis (PCA)

PCA was performed on the correlation matrix of standardized variables using the following formula:

[ PC_k = a_{k1} Z_1 + a_{k2} Z_2 + ... + a_{kp} Z_p ]

Where:

• ( PC_k ) is the k-th principal component,

• ( Z_i ) are the standardized variables,

• ( a_{ki} ) are the loadings (eigenvectors) that maximize the variance of ( PC_k ) subject to the constraint ( \sum_{i=1}^{p} a_{ki}^2 = 1 ).

The eigenvalue decomposition of the correlation matrix ( R ) yields:

[ R = V \Lambda V^T ]

Where:

• ( \Lambda ) is a diagonal matrix of eigenvalues (( \lambda_1 \geq \lambda_2 \geq ... \geq \lambda_p )),

• ( V ) contains the corresponding eigenvectors.

The proportion of variance explained by the k-th component is calculated as:

[ PVE_k = \frac{\lambda_k}{\sum_{i=1}^{p} \lambda_i} ]

Component Interpretation

Components were interpreted based on variable loadings, with loadings greater than |0.30| considered meaningful. All analyses were conducted in R version 4.4.2.

Getting Started

To replicate the analysis, clone this repository and ensure you have R 4.4.2 installed along with the necessary packages for PCA.

License

 see the LICENSE file for details.
