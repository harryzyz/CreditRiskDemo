# Credit Risk Model -- Construction, Calibration, and Utilization

## 1. Business Understanding

It is normal for lenders to incur credit losses from every portfolio over a given a period of time. In a another word, there is a certain amount of credit risk associated with every borrower. It is crucial to correctly estimate the expected loss (EL) associated with credit risk. The expected loss is defined as product of three components: probability of default (PD), loss given default (LGD), and exposure at default (EAD).

$$ \text{EL} = \text{PD} * \text{LGD} * \text{EAD} $$

This project demontrates one way of estimating the three aforementioned components respectively, and using them to calculate the expected loss.

At last, the estimated EL will be calculated. A scorecard, which can simply computes the credit score of an applicant, will be created. The scorecard can be easily used by non-tech staff such as front office workers or on-site representatives.

## 2. Data Understanding

Due to confidentiality, The real customer information cannot be used as data. Instead, a classic, lending club loan data available one kaggle.com will be used as a sample. However, the essence of this project remains unchanged. Similar procedure of data processing and modeling will be used. 

Here is the schema and explanation of each variable in the file:

* person_age (int) - applicant's age
* person_income	(int) - applicant's annual income
* person_home_ownership (str) - applicant's home ownership status
* person_emp_length (float) - applicant's employment length in month
* loan_intent (str) - purpose of the loan	
* loan_grade (str) - rating of the loan	
* loan_amnt	(int)	- total loan amount in US dollar
* loan_int_rate (float)	- loan interest rate in percentage
* loan_status (int) - loan status: 0 = non default, 1 = default
* loan_percent_income (float) - loan/income ratio
* cb_person_default_on_file (str) - applicant's credit history: 0 = no previous default, 1 = default previously
* cb_person_cred_hist_length (int) - applicant's credit history length in year

The data set is a simplified version of real-time situations. However, all the techniques performed in real life are shown. If ran into more complicated situations, the same techniques can be applied to other input variables.

To estimate and calculate the LGD and EAD, the information of 'recovery amount if default' and 'total recovery principal' is needed. However, those informations are missing in this data set. In later part of this project, we will manually assign reasonable values to those features, and demonstrate how to use them to model and test LGD and EAD model, respectively. Please note that the result maybe differ/worse than real-life situations.

## Part 3. Data Processing

This step is shown in the 'Data_processing.ipynb' file.

## Part 4. Modeling, Part 5. Evaluation, and Part 6. Deployment 

Those steps are written in separate files. File 'PD_Model.ipynb' contains the PD modeling and evaluation. File 'LGD_Model_and_EAD_Model.ipynb' contains LGD and EAD modeling and evaluation. Finally, Part 6. Deployment will be shown in the latter file. Moreover, a file 'PD_Model_Monitoring.ipynb' will illustrate how to calibrate the PD model with newer coming in inputs.
