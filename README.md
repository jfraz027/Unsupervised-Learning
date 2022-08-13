# Unsupervised-Learning
![image](https://user-images.githubusercontent.com/99145651/184465015-746435f6-9c3d-4985-bf12-a52af1ca478e.png)

# Myopia Clusters


## Background

As a key member on the data science team for a medical research company which is interested in finding better ways to predict myopia, or nearsightedness. My team has tried—and failed—to improve the classification model when training on the whole dataset. However, it is believed that there might be distinct groups of patients that would be better to analyze separately. Theh supervisor has asked for the team to explore this possibility by using unsupervised learning.

The raw data has been provided, first it must be processed to fit the machine learning models. One objectiveuse is to use several clustering algorithms to explore whether the patients can be placed into distinct groups. After which, create a visualization to share findings with the team and other key stakeholders.

## Instructions

During the analysis, break down the process into four parts: 

* Part 1: Prepare the Data

* Part 2: Apply Dimensionality Reduction 

* Part 3: Perform a Cluster Analysis with K-means

* Part 4: Make a Recommendation 

### Part 1: Prepare the Data

1. Read `myopia.csv` into a Pandas DataFrame.
![image](https://user-images.githubusercontent.com/99145651/184465370-29047ab4-3099-459f-8a34-5fd495696be1.png)


2. Remove the "MYOPIC" column from the dataset.
![image](https://user-images.githubusercontent.com/99145651/184465382-a439770c-d34d-43f1-9266-77b96e286bd9.png)


    * **Note:** The target column is needed for supervised machine learning, but it will make an unsupervised model biased. After all, the target column is effectively providing clusters already! 

3. Standardize the dataset so that columns that contain larger values do not influence the outcome more than columns with smaller values.
![image](https://user-images.githubusercontent.com/99145651/184465406-5583a733-e3bc-4310-8ff9-963fe3a3f605.png)

### Part 2: Apply Dimensionality Reduction

1. Perform dimensionality reduction with PCA. How did the number of the features change?
![image](https://user-images.githubusercontent.com/99145651/184465500-c34d6145-a0ed-441b-9f90-7fb5f58b2692.png)


  * **Hint:** Rather than specify the number of principal components when you instantiate the PCA model, state the desired **explained variance**. For example, say that a dataset has 100 features. Using `PCA(n_components=0.99)` creates a model that will preserve approximately 99% of the explained variance, whether that means reducing the dataset to 80 principal components or 3. For this assignment, preserve 90% of the explained variance in dimensionality reduction.

2. Further reduce the dataset dimensions with t-SNE and visually inspect the results. To do this, run t-SNE on the principal components, which is the output of the PCA transformation. 

![image](https://user-images.githubusercontent.com/99145651/184465529-910cbeb3-83b7-47c5-997e-fde6e2114305.png)

3. Create a scatter plot of the t-SNE output. Are there distinct clusters?

![image](https://user-images.githubusercontent.com/99145651/184465562-2c5b0a2d-bb9a-412a-a14e-f9031b8efc7c.png)


### Part 3: Perform a Cluster Analysis with K-means

Create an elbow plot to identify the best number of clusters. Make sure to do the following:

* Use a `for` loop to determine the inertia for each `k` between 1 through 10. 

* If possible, determine where the elbow of the plot is, and at which value of `k` it appears.

![image](https://user-images.githubusercontent.com/99145651/184465583-b326353c-e6eb-4d88-b2d7-22768c9449f2.png)

![image](https://user-images.githubusercontent.com/99145651/184465606-5c890be6-d6ff-46bf-8c59-c80553df5f98.png)

### Part 4: Make a Recommendation

Based on your findings, write up a brief (one or two sentences) recommendation. Can the patients be clustered? If so, into how many clusters? 

Clustering can be defined as the task of dividing the population or data points into a number of groups such that data points in the same groups are more similar to other data points in the same group than those in other groups. In simple words, the aim is to segregate groups with similar traits and assign them into clusters. Sometimes the data points in a scatter plot form distinct groups.  From the evaluation, the K-means method and Elbow curve plot indicates that clustering takes place between five and six. I would agree that clustering is possible with the most distinction existing in 6 clusters.
