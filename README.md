## Repository name
`async-final-project-teal-nicholas`

## Dataset
[Breast Cancer Wisconsin Data](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)

## Why did I chose this dataset?

This semester at Berkeley City College I’m taking biotech classes, which got me thinking about health issues that have existed for a long time and that biotechnology is currently attempting to alleviate. I figured that since we learned about data science and machine learning, we can apply those as well to see how they can complement existing and developing treatments that are more medicine/biology-focused.

My project involves analyzing the data set to find trends, then using the data to train a machine learning model (scikit-learn's RandomForestClassifier) to predict tumor cell malignant status given its measurements. The questions only cover the trend analysis, so for the ML model training and testing you will need to read the jupyter notebook. I included with it a lot of other visuals and commentary to illustrate what I was doing with the model.

## Progress
- [x] Picked dataset
- [x] Defined 10 questions
- [x] Answered 10 questions using Pandas
- [x] Added at least one data visualization (using Matplotlib and/or Seaborn) to each single question
- [ ] Prepared presentation slides to present at graduation

## Questions
- [x] Question 1: What percentage of tumors in the data set are cancerous? And how does that compare to real-world statistics of malignant vs. benign breast tumors?
  - Answer: About 37% of tumors in the dataset are cancerous. This is more than the 20% average of malignant breast tumors (from Stony Brook University)
  - Visualization: ![Q1 Visualization](img/q1.png)

- [x] Question 2: How does mean tumor cell nucleus radius correlate with diagnosis?
  - Answer: Malignant tumor cell nuclei had an average mean radius more than 5 micrometers larger than benign tumor cell nuclei. (17 vs 12)
  - Visualization: ![Q2 Visualization](img/q2.png)

- [x] Question 3: Are malignant tumor cell nuclei more asymmetrical?
  - Answer: Yes, slightly more asymmetrical on average
  - Visualization: ![Q3 Visualization](img/q3.png)

- [x] Question 4: How do "smoothness" and "symmetry" in the data set relate to each other? Consider in the context of malignant vs benign
  - Answer: They aren't exactly proportional (comparing differences between malignant/benign in smoothness and symmetry) but both values are "higher" in malignant tumors. Reason why I quote "higher" is because the way these are measured, I assume a higher value means more variation in measurements, so a lower value should be more smooth/symmetrical, therefore a malignant tumor would be rougher and asymmetrical.
  - Visualization: ![Q4 Visualization](img/q4.png)

- [x] Question 5: How do texture and smoothness relate? Again, in the context of malignant/benign can be helpful
  - Answer: As expected malignant tumors are both more rough and more textured. The difference between malignant and benign is more dramatic with texture than with smoothness, but looking at the definitions of each metric on the kaggle page they're likely related.

  However weirdly, texture decreased as roughness increased. I have no idea why. I spent maybe 10 minutes staring at the jupyter cell looking for problems but couldn't find anything wrong.
  - Visualization: ![Q5 Visualization](img/q5.png)

- [x] Question 6: WE haven't looked at the "worst" values yet, mostly just used the mean values. How do the worst radius values compare between the malignant and benign tumors?
  - Answer: Worst is defined as the mean of the three largest recorded values. So it makes sense that the average worst radius for malignant tumors is dramatically higher, but barely higher for the benign tumors. 

  I know the visual is the same as for q2 but it answers the same question. I just put the worst values for q2 as well to put things into perspective.
  - Visualization: ![Q6 Visualization](img/q2.png)

- [x] Question 7: Do malignant tumors generally have more points of concavity?
  - Answer: Yes, significantly more, additionally those points of concavity are much deeper on average in malignant tumors
  - Visualization: ![Q7 Visualization](img/q7.png) ![Q7 Visualization](img/q7-2.png) ![Q7 Visualization](img/drawing.png)

- [x] Question 8: The description for "fractal dimension" is a bit unclear. "Fractal" sounds like "jagged." Is it correct to assume fractal dimension measures will be higher for malignant tumors as well?
  - Answer: Maybe, but interestingly, only to a small extent. The worst fractal dimension values were higher for malignant than benign, but the mean values were almost identical, and additionally the standard error was higher for malignant, meaning there was more variation in malignant than benign tumors, even though the mean ended up being about the same.

  So if fractal dimension values are very high, it might lean towards malignant, but if they aren't unusually high fractal dimension values aren't a great predictor.
  - Visualization: ![Q8 Visualization](img/q8.png)

- [x] Question 9: Speaking of standard error, was there more error in texture measurements for malignant tumors? I'd predict so, since catching malignant tumors at different stages, they would be less textured at early stages but much more at later stages.
  - Answer: I predicted wrong, the standard error for malignant/benign was actually about the same at lower texture levels, the difference was really only visible with the outliers on the higher end of the texture column. And even then, standard error seemed to be lower for malignant than benign, which was interesting to me.
  - Visualization: ![Q9 Visualization](img/q9.png)

- [x] Question 10: What about for area? I'd predict that the area has greater standard error for malignant, for the same reason as above, but if my assumption is true there should be a great enough difference between early- and late-stage for it to reflect in the standard error values.
  - Answer: It's hard to compare area SE for malignant and benign because the area ranges for malignant and benign barely overlapped (max area was MUCH higher in malignant vs benign). But even then on the area of overlap, the lower end was actually more accurate with malignant, but the higher end was less accurate with malignant. And interestingly, from the lower to higher end of the benign area range, the SE was barely different at all. 

  As expected, at the higher end of the malignant area range, SE was much higher, indicating less accuracy. But if the area is that much higher, I don't think a great degree of accuracy is needed, the difference is probablyreally easy to spot visually as well.

  -----------

  Looking back this is a misinterpretation of the meaning of standard error in this scenario. Variability of measurements in this set is expected, since a nucleus won't always be a perfect circle for example, so measuring it from different angles gives different measurements, and high standard error indicates that some measurements were much higher/lower than others, suggesting that something is an irregular shape (for example, an elongated oval, which would be short one way but long the other way).

  In the case of area, it was probably approximated using a few measurements and the general shape of the nucleus. It would be pretty hard to get the exact area of the nucleus cross-section, and if that was even an option, there would be just one area reading instead of area mean and worst.

  Standard error being virtually the same from the low to high ends of the benign area range implies that benign tumor cell nuclei are often a more uniform shape (i.e. closerto a circle) than malignant tumor cell nuclei, even with slightly larger or smaller ones. However, shape alone wouldn't suggest a diagnosis, since lower-end malignant cell nuclei were also more uniform in shape.

  For question 9, texture standard error being slightly lower in malignant than benign cells is interesting, but remember from question 5 that malignant cells still had a higher mean texture rating, so SE being lower doesn't imply greater smoothness of malignant than benign. It just means the texture is more uniform in different areas of the nucleus. This is pretty interesting since you would expect an irregularly-shaped, fast-growing cell to have more variance in its nucleus surface texture, but when cells replicate (in mitosis), their nuclei completely disintegrate to let out the DNA for replication and splitting, so the texture variance of the nucleus would likely be unaffected by fast replication. Besides, the SE difference between malignant and benign is small enough to attribute to random chance.

  Trends like these are why machine learning is so important. If I really wanted, I could sit here and analyze every single row to understand what makes the diagnosis what it is, but that's inefficient, so why not just make the computer do it for me? 

  - Visualization: ![Q10 Visualization](img/q10.png)
