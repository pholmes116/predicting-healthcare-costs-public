## Project proposal form

Please provide the information requested in the following form. Try to provide concise and informative answers.

## Candidate numbers: 37386, 

**1. What is your project title?**

Clustering or building recommender systems for procedure codes based on Electronic Health Record (EHR) data

**2. What is the problem that you want to solve?**

Compile patient data from various EHR data sources into a consolidated patient profile that captures the relevant information required to provide efficient care to patients. After operationalizing this process, we will run k-means clustering across the various CSV files to cluster patients based on their procedure codes. K-means clustering will highlight which variables are relevant in predicting the patient's procedure using their demographic and registration information. 

**3. What big data methodologies and tools do you plan to use?**

Recommender system, Spark dataframes, SparkML/DBSCAN on Spark (clustering algorithms), feature transformers to create the patient profile dataframes

<You may consider any methods and tools to acquire, preprocess, store, analyse, and present results - as a traditional big data science pipeline>

**4. What dataset will you use? You may assess the suitability of the dataset for distributed computing for big data. Provide information about the dataset (size, features and labels, if applicable) and a URL for the dataset if available. If you intend to generate synthetic data, provide a description of what features you will use, whether your dataset is labelled or not (supervised versus unsupervised learning problem), how will it be generated (any functions, seed values, data ranges etc) and the expected size. When choosing or generating data, please remember to consider any aspects related to data representativeness, quality, bias and other aspects relevant to your project**

<list of real datasets>
<characteristics of synthetic datasets> https://synthea.mitre.org/downloads 
The data download is provided by Synthea and contains realistic synthetic EHR data (RS-EHR). 

**5. List key references (e.g. research papers) that your project will be based on. Please cite them properly and provide URLs.**

Jason Walonoski, Mark Kramer, Joseph Nichols, Andre Quina, Chris Moesel, Dylan Hall, Carlton Duffett, Kudakwashe Dube, Thomas Gallagher, Scott McLachlan, Synthea: An approach, method, and software mechanism for generating synthetic patients and the synthetic electronic health care record, Journal of the American Medical Informatics Association, Volume 25, Issue 3, March 2018, Pages 230–238, https://doi.org/10.1093/jamia/ocx079

Clustering datasets with demographics and diagnosis codes (Zhong et al.,2020) - https://www.sciencedirect.com/science/article/pii/S1532046419302801

**Please indicate whether your project proposal is ready for review (Yes/No):**

Yes

## Feedback & approval (to be provided by the lecturer by Week 11)

[MB - 04/04/2025] The topic is relevant and adherent with a big data scenario, depending on the size and structure of the synthetic dataset. You must ensure a good distribution across procedure codes by selecting some domains, such as neurological diseases, cardiovascular diseases and mental health issues (among others). Also, ensure you have a good distribution of patients of varied characteristics (biomarkers). yhou may consider whether the dataset is labelled or not, for instance, by adding a disease code (so this would help you to associate procedure codes to diseases). As for analysis, clustering is fine and will allow you to stratify patients. Besides clustering, which other models would be feasible here? There's mention to recommender systems, but perhaps this is not the best use case. You can try to simulate patient journeys moving from simple to complex cases, based on their biomarkers and procedure codes. For instance, a patient with high blood pressure and/or BMI who progresses to a cardiovascular case. The idea of predicting procedures based on patient's characteristics is also fine. Make sure to include big data-related metrics, such as execution time and scalability (single vs multiple machines). Remember to emphasise any other aspects of your big data pipeline where you've put more work. 

**Conditionally approved.** There's no need to resubmit but make sure to include a few more models and explore a few more data features. You can also consider deploying an ensemble of models. **Please, add the remaining candidate numbers.**
 
