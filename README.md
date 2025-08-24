## Repository name
Your repostiory should be named something like `async-final-project-color-name`
Example: `async-final-project-teal-Anas`

## Dataset
[Dataset Name](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)

## Why did I chose this dataset?

This semester at Berkeley City College I’m taking biotech classes, which got me thinking about health issues that have existed for a long time and that biotechnology is currently attempting to alleviate. I figured that since we learned about data science and machine learning, we can apply those as well to see how they can complement existing and developing treatments that are more medicine/biology-focused.

## Progress
- [ ] Picked dataset
- [ ] Defined 10 questions
- [ ] Answered 10 questions using Pandas
- [ ] Added at least one data visualization (using Matplotlib and/or Seaborn) to each single question
- [ ] Prepared presentation slides to present at graduation

## Questions
- [ ] Question 1: What percentage of tumors in the data set are cancerous? And how does that compare to real-world statistics of malignant vs. benign breast tumors?
  - Answer: About 37% of tumors in the dataset are cancerous. This is more than the 20% average of malignant breast tumors (from Stony Brook University)
  - Visualization: ![Q1 Visualization](https://example.com/path-to-image-1.png)

- [ ] Question 2: How does mean tumor cell nucleus radius correlate with diagnosis?
  - Answer: Malignant tumor cell nuclei had an average mean radius more than 5 micrometers larger than benign tumor cell nuclei. (17 vs 12)
  - Visualization: ![Q2 Visualization](https://example.com/path-to-image-2.png)

- [ ] Question 3: Are malignant tumor cell nuclei more asymmetrical?
  - Answer: Yes, slightly more asymmetrical on average
  - Visualization: ![Q3 Visualization](https://example.com/path-to-image-3.png)

- [ ] Question 4: How do "smoothness" and "symmetry" in the data set relate to each other? Consider in the context of malignant vs benign
  - Answer: They aren't exactly proportional (comparing differences between malignant/benign in smoothness and symmetry) but both values are "higher" in malignant tumors. Reason why I quote "higher" is because the way these are measured, I assume a higher value means more variation in measurements, so a lower value should be more smooth/symmetrical, therefore a malignant tumor would be rougher and asymmetrical.
  - Visualization: ![Q4 Visualization](https://example.com/path-to-image-4.png)

- [ ] Question 5: How do texture and smoothness relate? Again, in the context of malignant/benign can be helpful
  - Answer: As expected malignant tumors are both more rough and more textured. The difference between malignant and benign is more dramatic with texture than with smoothness, but looking at the definitions of each metric on the kaggle page they're likely related.
  - Visualization: ![Q5 Visualization](https://example.com/path-to-image-5.png)

- [ ] Question 6: WE haven't looked at the "worst" values yet, mostly just used the mean values. How do the worst radius values compare between the malignant and benign tumors?
  - Answer: Worst is defined as the mean of the three largest recorded values. So it makes sense that the average worst radius for malignant tumors is dramatically higher, but barely higher for the benign tumors. 
  - Visualization: ![Q6 Visualization](https://example.com/path-to-image-6.png)

- [ ] Question 7: Do malignant tumors generally have more points of concavity?
  - Answer: Yes, significantly more, additionally those points of concavity are much deeper on average in malignant tumors
  - Visualization: ![Q7 Visualization](https://example.com/path-to-image-7.png)

- [ ] Question 8: The description for "fractal dimension" is a bit unclear. "Fractal" sounds like "jagged." Is it correct to assume fractal dimension measures will be higher for malignant tumors as well?
  - Answer: Maybe, but interestingly, only to a small extent. The worst fractal dimension values were higher for malignant than benign, but the mean values were almost identical, and additionally the standard error was higher for malignant, meaning there was more variation in malignant than benign tumors, even though the mean ended up being about the same.

  So if fractal dimension values are very high, it might lean towards malignant, but if they aren't unusually high fractal dimension values aren't a great predictor.
  - Visualization: ![Q8 Visualization](https://example.com/path-to-image-8.png)

- [ ] Question 9: Speaking of standard error, was there more error in texture measurements for malignant tumors? I'd predict so, since catching malignant tumors at different stages, they would be less textured at early stages but much more at later stages.
  - Answer: I predicted wrong, the standard error for malignant/benign was actually about the same (infact slightly lower for malignant).
  - Visualization: ![Q9 Visualization](https://example.com/path-to-image-9.png)

- [ ] Question 10: What about for area? I'd predict that the area has greater standard error for malignant, for the same reason as above, but if my assumption is true there should be a great enough difference between early- and late-stage for it to reflect in the standard error values.
  - Answer: I predicted right this time, the standard error for area is dramatically higher for malignant vs benign (3.5x as much).
  - Visualization: ![Q10 Visualization](https://example.com/path-to-image-10.png)
