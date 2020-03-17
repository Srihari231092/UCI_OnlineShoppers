# Online Shoppers Purchasing Intention Dataset
----------

Online Shopping purchasing behaviour was collected from a website over a 1 year period, and marked whether the visit ended in generating revenue or not. 

We can build a prediction model using the given information to determine if the visit will end with an item being purchased.


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


## Key features that drove analysis 

This section contains information on key features that drove the analysis and subsequent modeling.

### Number of pages visited 

Visits which generated revenue had a marked increase in the number of informational pages and product related pages visited.

The higher the number of informational and product pages visited, the more likely the visit ended with a purchase





