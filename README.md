# Predictive-Model-for-Job-Salaries
The current options for finding an analytics job today are inefficient and scattered. A job seeker
must search for multiple job titles across several job websites in a process that is very manual and
time-consuming. The requirements for each job title also varies widely.

To solve this problem, our team built a unified job database that contains more than 25,000 highly relevant jobs that were focused on the needs of the business analytics and data science job seeker. We used natural language processing on the data to derive valuable insights about the skills required for each job. We also built a logistic regression model and classification tree to predict if the salary is above the median or not, based on the information available from the job posting. This makes the analytics job hunt much more efficient, by providing job seekers with valuable information that can help in negotiating starting terms even after securing a job offer.

# Description of the Dataset
We built our jobs dataset by scraping job information from Indeed and Monster. We decided to
look into the job postings for four titles: “Data Analyst”, “Business Analyst”, “Product Analyst”, and
“Data Scientist”. We restricted our search to the top 11 largest cities in the US. We searched for the jobs
based on these titles and locations. We then extracted the following pieces of information: the “Job
Title”, the “Company Name”, the location as “City”, “State”, and “Zip Code” (if available). Then we
consolidated the rest of the contents into a single text blob named as the “Job Description”. We then
parsed the description to extract the pay information as “Salary” if provided. The result was a dataset
that contained over 25,000 job opportunities for the four titles selected.

Although we captured over 25,000 job postings, only about 400 postings included salary information. We developed a regression model based on the 400 jobs that contained salary data, and then used that model to predict salary for the remaining jobs. We decided to use a logistic regression because even among the 400 salaries available, the salary range was still very wide. Also, as we only had 400 salary data points, we could not accurately predict salaries for the nearly 24,600 remaining jobs.

# Analysis of the Data
Our main objective was to utilize the data which we scraped from Indeed and Monster in order to extract information that would in turn help:
1. Understand better the job market demand
2. Have a high-level understanding of what each title is comprised
3. Identify key skills requested by recruiters across different job titles
4. Build a model to predict salaries based on job listing information

# Model results
We first produced a logistic regression model with 23 independent variables based on the features highlighted above. We obtained a decent 67% accuracy score using a 70%/30% training/testing dataset distribution. However, we noticed several redundant insignificant variables in the model. To resolve this, we applied backward regression to eliminate variables deemed insignificant (p-value > 0.1). The end result was a reduced model with 9 significant variables which included skills, locations, titles and seniority levels. The final reduced model had an accuracy of 63%.

Using the same features, we built a Classification Tree model to compare prediction results. The
end result was an accuracy of 52%.

# Key findings:
1. IBM, NTT Data, and Talent Bus seem to be the most active hirers in this space in the US.
2. California has the most analytics-related roles in the nation.
3. Data Science roles focus on more technical machine learning, whereas Data Analyst roles emphasize data analysis and reporting.
4. Product Analyst roles seek customer and product experience; Business Analyst jobs desire communication and understanding businesses.
5. Technology, Technical, and Soft Skills will vary based on the technical level of the role.
