---
title: Predicting Airbnb Prices
date: '2019-12-21'
slug: predicting-airbnb-prices
---

The rise of Airbnb has provided travelers with an alluring alternate method of accommodation. Instead of staying in traditional hotels, eager travelers now have the option of staying in other people's homes, making for somewhat of a more personal living experience. While we have since a meteoric rise in the number of Airbnb stays, hosts of Airbnb accommodations face the dilemma of setting optimal prices for charging travelers for their stay.

This project provides an exploration of different machine learning models in order to understand how best to predict Airbnb prices. This project was based on a dataset consisting of 90 features related to the property, the host and the reviews of over 35,000 rental properties.

A link to the source code and the methodology can be found on GitHub  [here](https://github.com/Charlie-Mei/predict-airbnb-prices).

## What is meant by the best price model?

There are many factors to take into consideration when identifying the best model for predicting Airbnb prices. 

If we are purely looking for a model with the highest level of accuracy, then this becomes a simple statistical problem - identifying the model the performs best against some predefined evaluation metric. As is often the case, however, the best performing models are often statistically complex and difficult to interpret. Machine learning models are often great at identifying unique patterns within the data, however those patterns are often difficult to comprehend due to the complex math behind its calculations.

If instead the purpose was to create a customizable machine learning tool that Airbnb hosts could use to price accommodations based on the unique features of their own accommodations, having a more easily interpretable model could be more beneficial to promote usage.

Since this project focused on the exploration of various machine learning tools, the best price model was based purely from a statistical point of view. Therefore, the best price model was the one that yielded the lowest root mean squared error (RMSE).


## What models were tested?

The following supervised machine learning models were tried and tested as part of this project:

- linear regression
- penalized linear regression (ridge and lasso)
- random forest.

## What were the final takeaways?

Efforts were made to ensure that any additional features coming out of the original data were captured through feature engineering. Even though, it was found that linear regression models reached a level of RMSE that plateaued upon adding additional features into the model. This does make sense, as the more features that are added to such models, the higher likelihood of collinearity issues creeping in, giving rise to potential bias with the end modeling results. Additionally, penalized regression models will indeed place less emphasis on such correlated features, and so it is difficult to achieve any great leaps in RMSE using linear regression models.

Random forest modeling resulted in an RMSE that was around 2x lower than the linear regressions tested. Random forests use the advantage of, at its core, decision trees that divide the original data into useful subcategories. These subcategories are then selected at random based on which features reduce RMSE the most after repeatedly sampling the data a specified number of times. It appears that this approach performs better than simple linear regression models that enforce simple relationships between features and price.
