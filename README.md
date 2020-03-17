# Online Shoppers Purchasing Intention Dataset
----------

Online Shopping purchasing behaviour was collected from a website over a 1 year period, and marked whether the visit ended in generating revenue or not. 

A model was built using the given information to determine if the visit will end with an item being purchased.


## Assumptions

- Data is representative of the whole population
- The values of bounce rate and Page values provided is for the final page the customer views before exiting the site
- It is more important to capture visits that will generate revenue, rather than those that do not. For example – Target marketing campaigns, discount offers and other promotions etc.


The dataset can be found [here](https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset)

## Key Insights from modeling the data

1. <b>Pages with lower bounce rates were shown to be a strong indicator of whether the visit generates revenue</b>
	- A drop in bounce rates by as much as 0.04 increases the odds of a customer making a purchase by 55%
	- Analysing features of pages with lower bounce rates, can provide further insights
1. <b>Higher Page Value is a strong indicator of whether the visit generates revenue</b>
	- 43 percent of all visits generate revenue for pages whose Page Value score is greater than 0
	- An increase of 19 units in Page Value, increases the odds of a customer making a purchase by 8 times
1. <b>November generates most favorable traffic ratios, but months such as December have a large amount of traffic as well</b>
	- Odds of a purchase in November increase by 275% compared to the prior months
	- Traffic in December can be targeted for conversion to generate more Revenue
	


## Data

As mentioned above, the dataset can be found in the [UCI ML repository](https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset), along with the data dictionary.

 - The class distribution is unbalanced with a ratio of <b>5.6:1 (False:True)</b>
 - Data set was split into three categories of Training, validation and holdout of <b>70%:15%:15%</b>
 - Sampling strategy employed was <b>stratified sampling</b> to maintina the imbalance ratio.

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/class_imb.png)

## Key features that drove analysis 

This section contains information on key features that drove the analysis and subsequent modeling.

### Number of pages visited 

Visits which generated revenue had a marked increase in the number of informational pages and product related pages visited.

The higher the number of informational and product pages visited, the more likely the visit ended with a purchase

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/info_prod.png)

### Bounce rates and page values

Visitors entering sites with lower bounce rates, or higher page values, were more likely to generate revenue
 
![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/bounce_rates_page_val.PNG)

### Monthly distribution

While most sales happen in November, there is a large rise of traffic in the months of  March, May and December, but sales are not proportionately rising

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/month.png)


## Modeling Pipeline

The data was subject through to a standard processing pipeline.

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/preproc_pipeline.PNG)

### Feature selection - I

Numerical columns were subject to correlation analysis to filter out highly correlated variables

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/num_corr.png)


Categorical variables were subject to Chi Square tests against the Revenue variable

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/chisq.PNG)


### Clustering

To visualize potential clustering of the preprocessed data, it was projected into a low dimensional space using tSNE and plotted

Clustering algorithms like KMeans and DBSCAN could not form any significant groupings on the dataset

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/clustering.PNG)


### Feature selection - II

The preprocessed data was classified using Logistic regression to establish a baseline, and to find significant features

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/logreg1.PNG)

Upon evaluating multiple feature selection methods, it was found that using the significant features, combined with weighting the desired Revenue group gave the best result


### Classification 

In a similar fashion, multiple classifiers were evaluated, with metrics and trade offs analyzed for each algorithm

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/classifiers.PNG)


While F1 scores were comparable, Precision and Recall values were deviant between each algorithm.
The final choice of algorithm was Logistic Regression to also retain interpretability.
 
## Final model

The Logistic Regression model allowed us to retain comparable F1 scores, and study the effect of significant features on Revenue

![alt_text](https://github.com/Srihari231092/UCI_OnlineShoppers/blob/master/res/img/logreg_final.PNG)

- Page Values have the most positive effect on generating Revenue, increasing odds by upto 8 times for each 18 units.
Similarly, the most deleterious effect is from Bounce Rates, where an increase in 0.04 reduces the odds by nearly 45%.

- In November, the odds of a purchase can increase by 275% compared to the prior months. Whereas in December, the odds can drop by 12%


## Conclusions and focus points

1. <b>Pages with lower bounce rates were shown to be a strong indicator of whether the visit generates revenue</b>
	- A drop in bounce rates by as much as 0.04 increases the odds of a customer making a purchase by 55%
	- Analysing features of pages with lower bounce rates, can provide further insights
1. <b>Higher Page Value is a strong indicator of whether the visit generates revenue</b>
	- 43 percent of all visits generate revenue for pages whose Page Value score is greater than 0
	- An increase of 19 units in Page Value, increases the odds of a customer making a purchase by 8 times
1. <b>November generates most favorable traffic ratios, but months such as December have a large amount of traffic as well</b>
	- Odds of a purchase in November increase by 275% compared to the prior months
	- Traffic in December can be targeted for conversion to generate more Revenue
	

## Additional improvements

Further improvements can be made for model generalization and improving metrics

 - More complex feature engineering
 - Focus on non-linear classifiers 
 - Increase granularity of data collection (e.g. weekly level)
 - Collect more samples
 - Acquire different dimensions and features (for example, page level information)






