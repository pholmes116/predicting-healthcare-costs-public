## Project: Comparing Distributed Machine Learning Models for Patient Cost Prediction Using Synthetic Electronic Health Records

## Candidate numbers: 37386, 38682, 45285, 58293

Single line summary: use of distributed machine learning to predict patient-incurred healthcare costs using synthetic electronic health records.

### 1. Introduction: Problem Formulation and Summary of Results (10%) 5

The context of cost estimation in healthcare settings is discussed, along with the importance and contribution of distributed computing technologies. Usually, any introductory text will start by defining the cost variables here and how important is their estimation to healthcare administration (along with potential limitations). Then, it would move to practical aspects, including technologies. The report starts by framing the importance of big data tools to cope with the increasing amount of data that needs to be analysed in this context, which is properly done. Cost and its estimation are discussed from paragraph 3 onwards. The relevance of the problem is clear, as well the proposed methodology. The summary of results is also fine and gives the reader an overview of what to expect in terms of experimentation.

As improvement, you need to revise the emphasis on US healthcare data, as you haven't used any US data at the end. Perhaps the problem could be framed in a generic way, for instance, for any private healthcare provider. You may also better contextualise "cost" here, as it may differs from one scenario/country to another.

### 2. Solution Methodology (20%) 12

Good set of related works covering synthetic data generation, use of large-scale processing systems, and some analytical methods/tools. Here, it would be fine to cover two important aspects: i) any guidelines for generating synthetic data that could guide your process and lead to better quality data; ii) is usually useful to position your solution against the existing literature; 1-2 paragraphs where you can comment on how the proposed work extends the existing literature, or fill any gaps etc. This helps in identifying contributions.

The overall solution is explained in section 3.1. Here, instead of PySpark Architecture, you should frame as proposed pipeline (or similar), as you are not discussing PySpark architecture but your proposed solution. Most of the chosen hyperparameters are discussed. One point to reconsider is the use of insurance coverage vs insurance claims (stated as removed in section 6.2). Which of these two types of data would be more useful to your model? If you are trying to predict "out of pocket" patient cost, wouldn't insurance claims be a reliable source of information here?

Data acquisition and preparation is overall fine, with a good pipeline to generate synthetic data and make necessary adjustments. You may consider other comments related to data across this report. Data modelling is based on LR, RF, and GBT models, tested individually and then as an ensemble. There's good but short discussion on isolated models' performance vs ensemble performance. Here, it would be nice to clearly state the expectations around the ensemble compared to isolated models, so any user could assess whether using isolated models only would be enough - you may link this discussion to any GCP metrics/costs, so it's easier to justify your choices.

I'm not sure LDA is the best approach for patient segmentation. I understand your attempt to identify patterns in clinical notes, but most diseases are influenced by other factors, such as age, gender etc; and this can lead to different costs. For instance, you have 10 topics, but what each of these topics is really mapping? This information only appears late in the numerical evaluation part. Perhaps a decision tree or any phenotyping technique would work better here.

Some aspects of the solution pipeline were assessed as part of the implementation.

### 3. Implementation (30%) 22

Code is comprised of 7 files, 3 of them for data acquisition and EDA; with some content overlapping for 100 and 1000 patients. In a real scenario, this is likely to converge to a single, fully parameterizable code. It is noticeable the effort in generating the fake data here and get it organised in a single file. You may consider improving the code structure (clear headers, sections and comments) and promoting the final dataset as a contribution from your work.

The other code files are devoted to model training and analysis. Again, you may consider a better code structure and organisation to avoid overlapping content and make your code more reproducible. One important aspect is to explain any data preparation steps taken inside these code files and how they depend on the data acquisition code.

Overall, the implementation is coherent with the proposed pipeline. You may consider adding some justification for your models, perhaps linking back to the existing literature and pointing to gaps.

### 4. Choice and Description of Data (10%) 5

Data was generated in Synthea, as described in section 3.2. There's a good set of resulting datasets, most of them of compatible size for a big data project. The final dataset, built through data linkage/join, is also described. If this is a reliable and good quality dataset, you could frame it as one contribution from your project.

Section 3.3 comments on EDA results. The idea is overall fine - this is a mandatory step for any real application. However, as you generated synthetic data, it would be necessary to comment on any parameters used during the generation process that could influence data quality and distribution; or to what extent the generation process can be explicitly controlled by the user, so the resulting data has more/less randomness.

Another important issue with your data is linked to the Introduction. Most of the time, the US healthcare system is used as reference. Why? If you are generating data, how any specificities from the US healthcare system were taken into account here? Would the dataset be useful to mimic healthcare systems from other countries?

You may also revise some statements in section 6.2 and how they reflect in the final dataset. Would it be possible to better control for important variables vs dataset size, so as to ensure the best set of fake variables are present in your dataset? Framing in another way, it's a bit trick to discuss data limitations when you are generating the data. Unless the tool doesn't allow to generate a specific type of data, all other aspects are presumably controllable by the user. It would nice to also discuss how the data limitations have affected your models.

### 5. Numerical Evaluation (20%) 13

Numerical evaluation is based on 11,500+ records, as stated. It would be nice to comment on class distribution and any sampling technique you used to ensure good distribution of patient population across your training batches.

Results for the 3 models are presented and discussed. Good point about LR and its negative cost predictions. You may consider revising its use as a baseline model due to this fact though. Good point about RF as well. You may note that `depth=10` is not necessarily a "limited tree depth" as stated. To improve performance, you may consider some improvements to the data generation/feature engineering, or perhaps some pruning technique.

Regarding LDA for patient stratification and cost estimation: this is a good attempt but the results are inconclusive, as reported. It is not clear how each topic differs from others, or whether specific words can effectively influence costs. The idea around Table 4 is fine but the results are not easily comparable and interpretable, as reported.

Section 4.2 brings an interesting scalability analysis of the proposed solution. The idea of testing with 100 and 1000 patients is fine - you had to choose some figures at the end :) - and there's good understanding of factors potentially influencing results.

### 6. Conclusion (5%) 3

Good summary of the proposed solution in terms of tools and models, along with recap on evaluation settings. Good coverage of limitations - but you need to revise some statements about data limitations as written here. Regarding future works, good point about data augmentation - again, you need to check this against the data limitations sections - using data claims and medication would perhaps improve your models. Clustering is also mentioned, which would be a feasible alternative to LDA.

### 7. Presentation Quality (5%) 3

Report is well-written and organised. There's room for improvement as mentioned here. You may revise some key information/definitions that need to appear early in the text, for instance. Code needs a better organisation and documentation, especially for reproducibility purposes.

**Final marks: 63**
