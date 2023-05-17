# Statistical Computing and Empirical Methods 
## Section A: Data wrangling 
In this part oyou will perform a data wrangling task with some business
analytics data from CORGIS (CORGIS Datasets Project (corgis-edu.github.io)).
You should also make sure your code is clean by making careful use of Tidyverse methods.
1.  Begin by downloading the csv file `business_dynamics.csv` from Blackboard.  
Next load the “business_dynamics.csv” file into R data frame called `business_dynamics_data_original`.
How many rows and how many columns does this data frame have?

2.  Generate a new data frame called `business_dynamics_data` which is a subset of the `business_dynamics_data_original` data frame with the same number of rows, but only five columns:

    a) The first column should be called `state` and correspond to the `State` column in the csv.  
    b) The second column should be called `year` and correspond to the `Year` column in the csv.  
    c) The third column should be called `num_firms` and should correspond to the `Data.Number of Firms` column in the csv.  
    d) The fourth column should be called `job_creation` and should correspond to the `Data.Job Creation.Count` column in the csv.  
    e) The fifth column should be called `job_destruction` and should correspond to the `Data.Job Destruction.Count` column in the csv.  
Display the first four rows of your data frame.

3.  Create a new column called `net_job_creation` which is equal to the difference between the number of jobs created and the number of jobs destroyed ie. net_job_creation is equal to job_creation minus job_destruction, for each row.
Your `business_analytics` data frame should now have six columns. Display the first three rows of your data frame.

4.  Which five states had the highest net job creation in the year 2000?  
   Use Tidyverse methods to generate a table called `top_five_net_creators` which demonstrates your answer. The `top_five_net_creators` table should have two columns `state` and `net_job_creation` and five rows showing states with the highest net job creation for the year 2000 in decreasing order (so that the state with the highest net job creation occupies the first row). You should use a combination of the pipe operator, the “arrange” function, the “filter” function, the “select” function and the “head” function. Display the “top_five_net_creators” table.

5.  Add a new column to the business_analytics data frame called “decade” which should give the decade corresponding to the year column. For example, the decade of the years 1980,1981,...,1988,1989 is 1980.  
   Add another new column to the business_analytics data frame called “job_creation_per_num_firms” which gives the net_job_creation divided by num_firms, for each row. Your “business_analytics” data frame should now have eight columns.    Check this without displaying the data frame itself. Display a subset of the “business_analytics” data frame containing the first six rows and the columns “state”, “decade” and “job_creation_per_num_firms” (so the displayed table should have six rows and three columns).

6.  Next generate a summary data frame from the “business_analytics” data frame called “california_summary” with the following properties.
Your summary data frame should correspond to rows associated with the state of California. Your summary data frame should have five rows each corresponding to a decade from 1970 through to 2010 inclusive. Your data frame should also have seven columns:
    1. “decade” – the decade (1970, 1980, etc)
    2. “njc_mn” – the mean average of the net jobs created in California for the
    corresponding decade
    3. “njc_md” – the median average of the net jobs created in California for the
    corresponding decade
    4. “njc_sd” – the standard deviation of the net jobs created in California for the
    corresponding decade
    5. “nf_mn” – the mean average of the number of firms in California for the
    corresponding decade
    6. “nf_md” – the median average of the number of firms in California for the
    corresponding decade
    7. “nf_sd” – the standard deviation of the number of firms in California for the
    corresponding decade  
You should use Tidyverse methods to create your “california_summary” table. Display the “california_summary” table.

## Section B: Statistical hypothesis testing    

In section B you should investigate a particular hypothesis test eg. a Binomial test, a paired Student’s t test, an unpaired Student’s t test, an F test for ANOVA, a Mann-Whitney U test, a Wilcoxon signed-rank test, a Kruskal Wallis test, or some other test you find interesting. The only hypothesis test you should not use is a one sample Student’s t-test for testing the value of the population mean.
Note that clarity of presentation is highly important. In addition, you should aim to demonstrate a depth of understanding.
For this hypothesis test you are asked to do the following:  
1. Give a clear description of the hypothesis test including the details of the test statistic, the underlying assumptions, the null hypothesis and the alternative hypothesis. Give an intuitive explanation for why the test statistic is useful in distinguishing between the null and the alternative.
   
2. Perform a simulation study to investigate the probability of type I error under the null hypothesis for your hypothesis test. Your simulation study should involve randomly generated data which conforms to the null hypothesis. Compare the proportion of rounds where a Type I error is made with the significance level of the test.
   
3. Apply this hypothesis test to a suitable real-world data set of your choice (some places to find data sets are described below). Ensure that your chosen data set is appropriate for your chosen hypothesis test. For example, if your chosen hypothesis test is an unpaired t-test then your chosen data set must have at least one continuous variable and contain at least two groups. It is recommended that your data set for this task not be too large. You should explain the source and the structure of your data set within your report.
   
4. Carefully discuss the appropriateness for your statistical test in this setting and how your hypotheses correspond to different aspects of the data set. You may want to use plots to demonstrate the validity of your underlying assumptions. Draw a statistical conclusion and report the value of your test statistic, the p-value and a suitable measure of effect size.
   
5. Discuss what scientific conclusions can you draw from your hypothesis test. Discuss how these would have differed if the result of your statistical test had differed. Discuss key experimental design considerations necessary for drawing any such scientific conclusion. For example, perhaps an alternative experimental design would have allowed one to draw a conclusion about cause and effect?


## Section C: Supervised learning 

In section C you should investigate a particular method for supervised learning. This could either be a method for regression or classification but should be a method with at least one tunable hyperparameter. You could choose one from ridge regression, k-nearest neighbour regression, a regression tree, regularized logistic regression, k-nearest neighbour classification, a decision tree, a random forest or another supervised learning technique you find interesting. The only supervised learning algorithm you should not use for this assessment is linear ridge regression (you could use kernel ridge regression, provided you can provide a sufficiently strong explanation of the relationship with linear ridge regression).
Note that clarity of presentation is highly important. In addition, you should aim to demonstrate a depth of understanding.
1. Give a clear description of the supervised learning technique you will use. Explain how the training algorithm works and how new predictions are made on test data. Discuss what type of problems this method is appropriate for.
   
2. Choose a suitable data set to apply this model to and perform a train, validation, test split (some places to find data sets are described below). Be careful to ensure that your data set is appropriate for your chosen algorithm. For example, if you have chosen to investigate a classification algorithm then your chosen data set must contain at least one categorical variable. Your data set for this task does not need to be large to obtain good results. The size of your data set should not exceed 100MB and you should aim to use a data set well within this limit. Your report should carefully give the source for your data. In addition describe your data set. How many features are there? How many examples? What type are each of the variables (eg. Categorical, ordinal, continuous, binary etc.?).
   
3. What is an appropriate metric for the performance of your model?
   
4. Explore how the performance of your model varies on both the train and the validation data change as you vary a hyperparameter.
   
5. Choose a hyper-parameter and report your performance based on the test data. Can you get a better understanding by using cross validation?
   
Note that you will be graded on your understanding of the key concepts. It is far better to choose a simple hypothesis test and supervised learning algorithm, and apply sound statistical reasoning than to choose complex methods without properly demonstrating your understanding.
Data sets
There are a vast number of freely available data sets across the internet. Below is a few example sources. You are also welcome to use data sets from other sources.
Any data you use should be freely available and accessible. The source of your data and the steps required to retrieve it should also be described within your main report.
  Explore how the performance of your model varies on both the train and the
 validation data change as you vary the amount of training data used.


>https://www.kdnuggets.com/datasets/index.html  
https://r-dir.com/reference/datasets.html  
http://archive.ics.uci.edu/ml/datasets.php  
http://lib.stat.cmu.edu/datasets/  
http://inforumweb.umd.edu/econdata/econdata.html   
https://lionbridge.ai/datasets/the-50-best-free-datasets-for-machine-learning/   
https://www.kaggle.com/  
https://www.ukdataservice.ac.uk/  
https://data.worldbank.org/  
https://www.imf.org/en/Data

           
Throughout your report you should emphasize:
Reproducible analysis (be careful with randomized procedures). Clear and informative visualizations of your results. Demonstrate a depth of understanding.
A clear writing style.


