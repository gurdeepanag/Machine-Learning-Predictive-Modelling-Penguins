# Penguin Measurement Analyses and Prediction using Machine Learning

### Introduction

In the vast and dynamic ecosystem of Antarctica, penguins emerge not only as key species but also as fascinating subjects of scientific study. Understanding their life patterns, physical adaptations, and population dynamics is essential to unraveling the mysteries of these resilient beings and their interactions with the environment. This report focuses on exhaustive statistical analysis of a detailed dataset of penguins, encompassing multiple species and diverse physical and biological measurements. Through advanced statistical techniques, including various types of sampling and statistical techniques, we aim to unravel the complex interactions between the physical characteristics of the penguins, their environmental context, and species. This research not only seeks to contribute to the existing academic body on Antarctic wildlife but also to highlight the importance of applying rigorous statistical methods to better understand the animal. With meticulous analysis, our goal is to provide insights that are fundamental for the conservation and management of this animal, emphasizing how data science and statistical techniques can be powerful tools in understanding biodiversity and various animal species. This report is a step towards the profound exploration of the secrets that penguins have guarded for millennia, opening new avenues for research and appreciation of these emblematic creatures. Through some exploratory research, we have identified that the only categorical factors that would likely influence the physical and biological measurements of penguins would be the species (Animal Corner, 2023) and sex of the penguin (Horvath A., 2024). Through this research we have identified the best sampling method to choose would be stratified sampling based on the species of penguin, as we believe this has the largest impact on the measurements.

### Dataset

This dataset is from Kaggle and was sourced from the original public Github page (Amy, 2024). It can be used according to the MIT license which means we have the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the dataset without limitation (Amy, 2024).

<table border="1">
  <tr>
    <th>Column Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>Species</td>
    <td>Species of the penguin</td>
  </tr>
  <tr>
    <td>Island</td>
    <td>Island the penguin belongs to</td>
  </tr>
  <tr>
    <td>Culmen_length_mm</td>
    <td>Length of the penguin's culmen (bill)</td>
  </tr>
  <tr>
    <td>Culmen_depth_mm</td>
    <td>Depth of the penguin's culmen (bill)</td>
  </tr>
  <tr>
    <td>Flipper_length_mm</td>
    <td>Flipper length of the penguin</td>
  </tr>
  <tr>
    <td>Body_mass_g</td>
    <td>Body mass of the penguin</td>
  </tr>
  <tr>
    <td>Sex</td>
    <td>Sex of the penguin</td>
  </tr>
</table>

Table 1: Column Descriptions

### Objectives

Our first objective would be to check to see if stratified sampling, stratifying on penguin species (50 samples) is a good estimator of the actual population mean of the body mass of penguins. The sampling phase plays a crucial role in our analysis to provide a good estimator. This allows us to gain a deeper understanding of the penguin population and its characteristics. Our second objective in this project is to see if any physical and biological measurements of penguins are highly correlated with one another, and if so, are we able to use ratio estimation to obtain estimates of the other variable, in order to simplify the data gathering process for future measurements. Once robust correlations between variables are identified, we expand our exploration by implementing a ratio estimator. This estimator enables us to predict the values of different numerical features, and evaluate the accuracy and feasibility of our predictions. Our third goal is to run a bootstrapping simulation on a stratified sample of 50 penguins to determine the 95% confidence interval for estimating the average body mass of penguins. The point of bootstrapping simulations is to generate multiple resampled datasets from an existing dataset, allowing for the estimation of sampling variability and uncertainty in statistical analyses without additional data collection. Building on the previous investigations, we try to build a model that should be able to provide reasonable estimates using the rest of the features for the body mass (in g). In order to do so, we choose the Naive Bayes. In order to adhere to the conditions for its use, we train the model only considering the numerical & continuous variables. Our last objective would be to create an accurate Logistic Regression algorithm (supervised machine learning) in order to predict the species of a penguin given various physical and biological measurements. We rigorously assess the accuracy of the model to ensure its reliability and effectiveness.

### Discussion

After conducting our analysis, we have determined that organizing penguins by species is an effective method for collecting samples. This approach guarantees a diverse representation of various penguin types, enabling us to accurately reflect the entire penguin population. Our charts demonstrate a close alignment between the sample and the population, resulting in a reliable 95% confidence interval that captures the true average weight of the penguins.

In addition to species stratified sampling, we explored the use of ratio estimation to weigh penguins. We observed a strong correlation between a penguin's flipper length and body mass, providing an alternative method for estimating body mass. The confidence interval derived from this technique was slightly broader than that obtained from stratified sampling alone, indicating a lower level of precision.

By combining species stratified sampling with bootstrapping, our ability to predict body mass significantly improved. The distribution of averages obtained through bootstrapping was well-centered around the true average, with our confidence interval encompassing the actual average weight.

In terms of predicting penguin body mass, we developed a Gaussian Naive Bayes model focusing solely on numerical data. Unfortunately, the model's accuracy was subpar, resulting in a high root mean square error. This implies a considerable margin of error in predicted values, potentially reaching up to +/- 800, which is substantial given the typical range of penguin weights.

Conversely, our logistic regression model excelled in predicting penguin species based on physical and biological measurements. It exhibited an impressive 97.01% success rate, with coefficients revealing intriguing patterns such as the relationship between culmen length and penguin species. For instance, a longer culmen length may indicate a Chinstrap penguin, while a smaller culmen depth could suggest a Gentoo penguin.

### Conclusion

Our data science project utilized stratified sampling penguins by species as a powerful method for sample collection, ensuring a representative mix and yielding a reliable 95% confidence interval for average weight. We explored other methods as well such as ratio estimation, to obtain less restrictive confidence intervals. Gaussian Naive Bayes faced challenges in predicting body mass accurately, our logistic regression model excelled in species classification with a 97.01% success rate.

These findings emphasize the effectiveness of strategic sampling and the potential of machine learning models for accurate species identification, providing a foundation for further exploration and refinement in penguin population analysis.

### References

Amy. (2024). Penguin sizes dataset. Kaggle. https://www.kaggle.com/datasets/amulyas/penguin-size-dataset

Animal Corner. (2023). Penguin Size Comparison-How Big are Penguins? Animal Corner. https://animalcorner.org/blog/penguin-size-comparison/

Horvath A. (2024). How do Penguins find their mate in a sea of tuxedos? The University of Melbourne. https://pursuit.unimelb.edu.au/articles/how-do-penguins-find-their-mate-in-a-sea-of-tuxedos
