# machine_learning_project-unsupervised-learning

## Project Outcomes
- Unsupervised Learning: perform unsupervised learning techniques on a wholesale data dataset. The project involves four main parts: exploratory data analysis and pre-processing, KMeans clustering, hierarchical clustering, and PCA.

### Project Description:
In this project, we will apply unsupervised learning techniques to a real-world data set and use data visualization tools to communicate the insights gained from the analysis.

The data set for this project is the "Wholesale Data" dataset containing information about various products sold by a grocery store.
The project will involve the following tasks:

-	Exploratory data analysis and pre-processing: We will import and clean the data sets, analyze and visualize the relationships between the different variables, handle missing values and outliers, and perform feature engineering as needed.
-	Unsupervised learning: We will use the Wholesale Data dataset to perform k-means clustering, hierarchical clustering, and principal component analysis (PCA) to identify patterns and group similar data points together. We will determine the optimal number of clusters and communicate the insights gained through data visualization.

## Process:
### EDA
- Imported dataset into dataframe
- Checked shape of dataframe, and for the presence of duplicates and null values; neither were present
- Printed decriptive stats for columns not related to location (third column onwards). The mean was significantly higher than the median in all cases, with a dramatically higher maximum value, and large differences between the mean and standard deviation, implying the presence of significant outliers. 
- Produced boxplots to show outliers (on two separate plots, as the smaller values were hard to see on a single plot). Testing showed that removing all or most of the outliers would result in significant data loss (up to 20% of the data set), so only the most extreme outliers were removed.
- Cleaned data still had higher means than medians, but the mean and standard deviations were much closer together, and redoing the box plot still shows outliers, but they are much closer to each other, as well as the whiskers. Trying to remove more results in a significant degrease in sample size, so I left the remaining outliers. 
- Plotted totals spent on each category of item, a pairplot to look for correlations, and the correlation coefficients for the pairings of features with a value above 0.5
- Used `StandardScaler` to scale data before feeding it to the models.

### KMeans Clustering
- Used elbow method to identify optimum number of clusters before applying KMeans clustering to the data
- Plotted clusters on scatterplots of previously found features with high correlation, as well as in a grouped bar graph breaking down the mean spending on each product category. 

### Hierarchical Clustering
- Used two types of dendrograms (ward and complete) to select cluster number to use for `AgglomerativeClustering`, and plotted the resulting clusters onto scatterplots of the same correlated features used in the KMeans scatter plots.
- Plotted grouped bar graph breakdowns for mean spending by product category for each clustering output

### PCA
- Plotted explained variance ratio vs number of principal components to recreate the elbow model and decide how many to create.
- Transformed the data using my chosen value of 3 components and messed around with which to show on the scatter plot to best capture the relationship. 

### Conclusion
- Put all of my grouped bar charts in one place so I could more easily draw additional conclusions by comparing them


## Results
The single most popular item type based on sales is 'Fresh'.

Between individual pairs of features, there is a significant positive correlation (>0.5) between
    > Milk and Grocery (0.76)
    > Milk and Detergents/Paper (0.70)
    > Grocery and Detergents/Paper (0.89)

I had three different cluster counts returned; 4 (Hierarchical, dendrogram type 'complete'), 5 (KMeans), and 6 (Hierarchical, dendrogram type 'ward'). When all of these are plotted together, it shows that even when more clusters are added by different models, the groupings stay quite consistent.

The PCA analysis showed that most of the data could be accounted for with 3 composite features, and in fact a very clean diagram came out. Unfortunately, that is all I knew how to do with that process in this context. 

## Challenges
Deciding where to place my outlier cutoffs to get a reasonable amount of cleaning done without losing too any samples was time consuming, although not exactly difficult. 

It was hard to figure out ways to display the data that would be meaningful, and then to format the graph grids neatly. I also misplaced a line of code at once point at the whole display broke; it took a while to fix that.

## Future Goals
Figure out how to do clustering using PCA features and repeat analyses. 