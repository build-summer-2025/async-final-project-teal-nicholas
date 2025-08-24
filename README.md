## Repository name
Your repostiory should be named something like `async-final-project-color-name`
Example: `async-final-project-teal-Anas`

## Dataset
[Dataset Name](https://www.kaggle.com/datasets/rabieelkharoua/diabetes-health-dataset-analysis)

## Why did I chose this dataset?

THe most commonly used test to diagnose diabetes is the HbA1c test, which measures glucose attached to hemoglobin molecules in the blood as a way to estimate average blood glucose levels in the past few months. It is established that a reading of 6.5% or more on two different HbA1c test occurences indicates diabetes. However, this threshold was determined using data that was not representative of all ethnic groups, and because there are differences between ethnic groups that can influence HbA1c levels (for example, abnormal hemoglobin, as found in sickle cell anemia and other blood diseases more common in some ethnic groups) the test should not be used as a sole factor in diagnosis. (It is currently used along with other test like the FPG test, but these tests can have inaccuracies between groups as well.)

I chose this data set because I wanted to make a machine learning model that takes as many statistics as possible (including not only test results but also ethnicity) to predict a diabetes diagnosis accurately. Since the data set includes each patient's confirmed diabetes status along with the statistics, the model can learn what factors/levels point towards a positive result.

## Progress
- [ ] Picked dataset
- [ ] Defined 10 questions
- [ ] Answered 10 questions using Pandas
- [ ] Added at least one data visualization (using Matplotlib and/or Seaborn) to each single question
- [ ] Prepared presentation slides to present at graduation

## Questions
- [ ] Question 1: Training a machine learning model requires sufficient data for as many outcomes as possible, otherwise the model does not know what factors are needed to predict an outcome that was missing from the training data. Does every ethnic group have an adequate amount of both confirmed diabetes positive or negative cases?
  - Answer: Each ethnicity (numbered 0 to 3 in the data) does have at least an adequate amount of both positive and negative cases, however the Caucasian (white) group has the most data. But the data for other ethnic groups should be enough to train a ML model to reasonable accuracy.
  print(df.groupby(['Ethnicity', 'Diagnosis']).size())
  - Visualization: ![Q1 Visualization](https://example.com/path-to-image-1.png)

- [ ] Question 2: Does the data also represent all age groups? Does it represent them equally?
  - Answer: Each decade from 20-29 to 80-90 has between 250 and 300 rows, so representation is mostly equal. However, there are no cases from teenagers or children.
  bins = [19, 29, 39, 49, 59, 69, 79, 90]
labels = ['20-29', '30-39', '40-49', '50-59', '60-69', '70-79', '80-90']
print(pd.cut(df['Age'], bins=bins, labels=labels).value_counts().sort_index())
  - Visualization: ![Q2 Visualization](https://example.com/path-to-image-2.png)

- [ ] Question 3: Does the rate of diabetes correlate with socioeconomic status?
  - Answer: Interestingly, the ratio of positive to negative cases was highest with the middle socioecnomic status group. This doesn't really suggest anything on its own though.
  print(df.groupby(['SocioeconomicStatus', 'Diagnosis']).size())
print(f'{210/347}, {320/460}, {222/320}')
  - Visualization: ![Q3 Visualization](https://example.com/path-to-image-3.png)

- [ ] Question 4: Does the rate of diabetes correlate with education level?
  - Answer: Also interestingly, the ratio of positive to negative was higher in patients with a highest level of education of high school or bachelor's degree, and lower with a post-bachelor's degree or no high school diploma at all. Again though, this might not suggest anything on its own.
print(df.groupby(['EducationLevel', 'Diagnosis']).size())
print(f'{60/103}, {252/363}, {296/429}, {144/232}')
  - Visualization: ![Q4 Visualization](https://example.com/path-to-image-4.png)

- [ ] Question 5: Does the rate of diabetes correlate with health literacy? (This can be independent from education level, which is why it deserved its own question.)
  - Answer: Not here - again, very interestingly, the ratio of positive to negative was actually higher with a higher health literacy range.
  bins = range(1,11)
df['HealthLiteracyInterval'] = pd.cut(df['HealthLiteracy'], bins=bins, right=False)
print(df.groupby(['HealthLiteracyInterval', 'Diagnosis']).size())
  - Visualization: ![Q5 Visualization](https://example.com/path-to-image-5.png)

- [ ] Question 6: How does health literacy correlate with education level?
  - Answer: Strangely, it really didn't. I have no idea how they measured health literacy.
  print(df.groupby(['HealthLiteracyInterval', 'EducationLevel']).size())
  - Visualization: ![Q6 Visualization](https://example.com/path-to-image-6.png)

- [ ] Question 7: [Brief description of the task]
  - Answer: [Placeholder for answer]
  - Visualization: ![Q7 Visualization](https://example.com/path-to-image-7.png)

- [ ] Question 8: [Brief description of the task]
  - Answer: [Placeholder for answer]
  - Visualization: ![Q8 Visualization](https://example.com/path-to-image-8.png)

- [ ] Question 9: [Brief description of the task]
  - Answer: [Placeholder for answer]
  - Visualization: ![Q9 Visualization](https://example.com/path-to-image-9.png)

- [ ] Question 10: [Brief description of the task]
  - Answer: [Placeholder for answer]
  - Visualization: ![Q10 Visualization](https://example.com/path-to-image-10.png)
