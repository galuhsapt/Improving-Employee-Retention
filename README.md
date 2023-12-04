

# Improving Employee Retention by Predicting Employee Attrition Using Machine Learning
by Mochamad Galuh Saputra

## Problem
"Human resources (HR) are the key assets that need to be effectively managed by companies to achieve business goals efficiently. In this instance, we will be addressing an issue related to human resources within the company. Our focus is to understand how to retain employees in the current company, thus avoiding the inflation of costs associated with recruiting and training new personnel. By identifying the primary factors that lead to employee dissatisfaction, the company can promptly address these issues by implementing relevant programs tailored to the employees' concerns."

## Objective
Streamline the process and analysis to automate and enhance the accuracy of employee eligibility assessments.

## Data Understanding
**![](https://lh7-us.googleusercontent.com/EFrzMBUXmeS4Gbm9XGX7hgnBACZGCb_MvfqBn8uxEbwAoHg7-JYjzdOcYewUtmNjoUS1cywS4Z5C1Guiu3GdFIzYtqtHu4n97EUEyNK13aAxRM4cpItzqY_F81LjSLsAv3va6h0RGtLdqQBwsS6UWa8mhg=s2048)**

 - There are 287 rows of data.  
 - There are 25 columns.  
 - There are 18 categorical columns and 7 numerical columns.  
 - No label data is
   available yet.

## Data PreProcessing

 - There are no duplicate data. 
 - There are some null values in the dataset. 
 >The columns below will be filled with:
 SkorKepuasanPegawai = 3
JumlahKeikutsertaanProject= 0
JumlahKeterlambatanSebulanTerakhir = 0
JumlahKetidakhadiran = 0
IkutProgramLOP = drop
AlasanResign = masih_bekerja

 - Dropping unnecessary data. 
 > The columns below will be dropped:
 PernahBekerja, 
 Username, 
 EnterpriseID, 
 Email, 
 NomorHP.

 - Changing the datatype of columns that are not appropriate.
 > The datatypes below will be adjusted.
 > TanggalLahir,
 > TanggalHiring, 
 > TanggalPenilaianKaryawan, 
 > TanggalResign.

## Exploratory Data Analysis
**![](https://lh7-us.googleusercontent.com/pWoS1KT5xjT0iECgdkwJ7tTIdsCAnGX1TOW-uDvvRUz6FSdL_1uCR0Xyxmfo6dpVdQT5EGLaKRDyutTanbyLSser4JrZ7o952Mk87J-6rbsl5LRIqw4g-bC6nuyIJK1b4xyF6CkuB02f36dZjv3wI_V_Zg=s2048)**

In the chart above, it can be observed that from 2006 to 2016, over the course of 10 years, the number of employees consistently increased, reaching its peak at 248 individuals. However, from 2016 to 2020, there has been a continuous reduction in the number of employees. This certainly requires further analysis to ensure it does not disrupt the workflow and the efficiency of the company's performance.

**![](https://lh7-us.googleusercontent.com/_0WJ681WJF6fPoRbu2lnw4LT_aciKhVrYcFWAVsAdtQk3_PwA-oZ9V1rakUz3zySBG_-KtPrzguJxMZPbQGk7eR2zwzucVdFis8a2gQLIf79e7MuZsJ_z6-AZ-42BPUqSSc4W_lhBYuNtzwNXeDwVS_rTw=s2048)**

The field of work with the highest attrition rate turns out to be in the Data Analyst domain. The attrition among employees in this field is significant, reaching up to 50% of the total employees in the Data Analyst job category.

**![](https://lh7-us.googleusercontent.com/tuuUhdYI7n5HHw_vHTem0uxOiaajwAUjqhR5KA8duIuL5suVUZSy6veRVEYwN0_g364w23SaYZNF8YJmriiGVJSXO0RukkQ9_1GbjbKhoqCuM7sfJ6GSw3aChGwSFZCDZmqIcTZKTYer-kMyp9COqFnn5Q=s2048)**

From the analysis of the previous graph, it is evident that the highest resignation rate occurs in the Data Analyst field. All resigning employees belong to the Fresh Graduate Program category, citing the primary reasons as a toxic work culture and internal conflicts. Interestingly, a significant portion of resigning employees has demonstrated excellent performance, indicating a potential loss of efficiency. The company needs to address the issue of a toxic work culture to retain high-potential employees and ensure smooth operational continuity.

## Modeling & Evaluation
**![](https://lh7-us.googleusercontent.com/egDigklDI_hVslXkIUNJAhfUr4F7JSnYVcyU6vCrD6_MHENHItm_yoVxDtYhMY9tmd4pNju6QRaK3fyQfmlFzRS8uozgidzdxy8WVswqEsoIXEnYUjv_WTLbsSRk4m55StaYxXrqdBkFANrIW2yU0iorTg=s2048)**

It appears that several machine learning models were initially tested, including 
 - RandomForest, 
 - LogisticRegression, 
 - ExtraTrees, 
 - DecisionTree, 
 - GradientBoost, and 
 - XGBoost. 

However, after hyperparameter tuning, the final model retained for testing is DecisionTree.

**![](https://lh7-us.googleusercontent.com/n53hXVLwBe24pAp2_zOWt8hVzSQGrcHyIhs0-nJyMREpBpe21wFW5J5POq7svHG6fnvTHoaN9zrRgxBI31h9t3X40c0z36AkfYo8Skz1yVwo8wMFCY0CjWpGdEZ4UlS7lxyr1iEnnEEUcpdF5NZpgKc8bg=s2048)**

From the results of the initial modeling, it appears that all models achieved a perfect score of 1.0. Therefore, it is necessary to perform HYPERPARAMETER TUNING to prevent overfitting.

The model chosen for hyperparameter tuning is DecisionTree, with the primary metric being Recall. After tuning, the model has been improved.

**![](https://lh7-us.googleusercontent.com/Yl4Len27UguomR4k9kn_009xwvUwpFRo5ExNrNwYKNUDAJL0C0bKp0wCf_Hr56mZnQBH2br1_xEshcWYFa2k_NUT6mH0C0Zqlt3DiiCC11iR8AXZv84z0BYm6le7xgxtAfu6w03lj37FEBQBkFCI9JQ60Q=s2048)**

From the Confusion Matrix results provided, it is evident that before tuning, the model was overly perfect in learning from the training data. However, after tuning, the model's performance has improved.

**![](https://lh7-us.googleusercontent.com/cyfWkaMof_-qfU4dBV5TjoqqzNGPOxqjb_1ytZT0IMGKoMoCNBh509HK4o3TVR8GijbJdxP187vfwSRAQLdCdHr6gYaD3VE8sLuVtqVDSy9gKvM31rIsmYAk9JVTNt-ihv3qHseCy8UgWFEKc2UiQpWlsA=s2048)**  

Here are the results of the ROC-AUC curve. It can be observed that the model was overly perfect in learning from the training data before tuning, while after tuning, it has become more balanced and improved.

**![](https://lh7-us.googleusercontent.com/pZsHQbNTwaU89L_Cye7nNYKHtc-NDauSxzM8chY5oDulnhwHj4nF0FPby29WkCGV8XRVmAhpCbHdMMZXSkZahIYFDSOe7NC6P3_ps5wvljEysDtzqI_RELh1JlHZH3zYD7ramUJDGcIjO4cweJ5q6Ofifw=s2048)**
  
The three most influential features are:
1.  AlasanResign_ganti_karir 
2.  LamaBekerja_Bulan 
3.  JumlahKeikutsertaanProjek

## Summary
Project focuses on employee retention using machine learning.
Dataset: 287 rows, 25 columns (18 categorical, 7 numerical).
Preprocessing: Handled duplicates, nulls, dropped unnecessary columns, adjusted data types.
EDA: Employee count increased till 2016, then declined. Data Analysts field have highest attrition rate.
Modeling: DecisionTree chosen after tuning, demonstrated improved performance.
Key Features: AlasanResign_ganti_karir, LamaBekerja_Bulan, JumlahKeikutsertaanProjek.

## Business Recommendation

 1. It is crucial for the company to pay attention to the needs of employees and provide opportunities for their development. By offering clear career paths and engaging development opportunities, the company can prevent employees from seeking jobs elsewhere.
 2. Implementing fair and transparent performance management is also essential. By providing constructive feedback and relevant training, the company can maintain employee motivation and help them develop their skills.
 3. It is also important to ensure a balanced workload for employees. Wise management of the number of projects handled by employees can prevent them from feeling overly burdened, thereby enhancing their well-being and performance.
