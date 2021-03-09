---
layout: post
title: Where I started 
subtitle: My first Kaggle competition -- Home credit default risk (Light Gradient boosting)
gh-repo: fyfserena/kaggle_home_credit_default_risk
cover-img: /assets/img/hcdr.JPG
thumbnail-img: /assets/img/hcdr.JPG
tags: [Kaggle, data mining, fun]
comments: false

---

[Competition hosted at Kaggle](https://www.kaggle.com/c/home-credit-default-risk)

This is where I began my journey as a data miner /not a scientist :(

This is a Kaggle competition (the very first Kaggle competition) I have accomplished when I was a sophomore. Still remember clearly it was a Friday night I sat on the 4th floor stair in the dorm building waiting for my teammate to begin this whole data things. I know nothing back then. 

It feels so great to take a look back at it again! I learnt so much from dealing with really messy data in industries these years. A clean and well-prepared dataset is a bless!

There are so many methods I keep reusing in almost every data-driven project I have done in the past few years. 


* #### EDA methods: missing_values_table(df) and all kinds of plots in EDAonTrainandTest.ipynb:

```python
    def missing_values_table(df):
        # Total missing values
        mis_val = df.isnull().sum()
        # Percentage of missing values
        mis_val_percent = 100 * df.isnull().sum() / len(df)
        # Make a table with the results
        mis_val_table = pd.concat([mis_val, mis_val_percent], axis=1)
        # Rename the columns
        mis_val_table_ren_columns = mis_val_table.rename(
        columns = {0 : 'Missing Values', 1 : '% of Total Values'})
        # Sort the table by percentage of missing descending
        mis_val_table_ren_columns = mis_val_table_ren_columns[
            mis_val_table_ren_columns.iloc[:,1] != 0].sort_values(
        '% of Total Values', ascending=False).round(1)
        # Print some summary information
        print ("Your selected dataframe has " + str(df.shape[1]) + " columns.\n"      
            "There are " + str(mis_val_table_ren_columns.shape[0]) +
              " columns that have missing values.")
    # Return the dataframe with missing information
    return mis_val_table_ren_columns
    
    
```



* #### Early stopping concept in Light Gradient boosting:

  * Training until the validation error does not decrease for a specified number of iterations

  * Commonly applied to the GBM and to deep neural networks. 

  * One of many forms of regularization that aims to improve generalization performance on the testing set by not overfitting to the training data.

  ```python
  # Get default hyperparameters
  model = lgb.LGBMClassifier()
  default_params = model.get_params()
  
  # Cross validation with early stopping
  cv_results = lgb.cv(default_params, train_set, num_boost_round = 10000, early_stopping_rounds = 100, metrics = 'auc', nfold = N_FOLDS, seed = 42)
  
  
  ```
   
   

* #### XGBOOST and Light GBM ([Here is a great article!](https://www.analyticsvidhya.com/blog/2017/06/which-algorithm-takes-the-crown-light-gbm-vs-xgboost/)):

  * Light GBM is a fast, distributed, high-performance gradient [boosting](https://courses.analyticsvidhya.com/courses/ensemble-learning-and-ensemble-learning-techniques?utm_source=blog&utm_medium=which-algorithm-takes-the-crown-light-gbm-vs-xgboost) framework based on **decision tree** algorithm.

  * It splits the tree leaf-wise whereas other boosting algorithms split the tree depth-wise. 
  
  * So when growing on the same leaf in Light GBM, the leaf-wise algorithm can reduce more loss than the depth-wise algorithm and hence results in much better accuracy.(Leaf-wise splits lead to increase in complexity and may lead to overfitting and it can be overcome by specifying another parameter max-depth which specifies the depth to which splitting will occur.)
 ![image](https://user-images.githubusercontent.com/46977839/110224956-680ca300-7eae-11eb-8952-77a6da0ba98f.png)

## Advantages of Light GBM

1. **Faster training speed and higher efficiency**: Light GBM use histogram based algorithm i.e it buckets continuous feature values into discrete bins which fasten the training procedure. (Don't know what is means by "discrete bins", combine features together? [check this](https://towardsdatascience.com/what-makes-lightgbm-lightning-fast-a27cf0d9785e))

2. **Lower memory usage:** Replaces continuous values to discrete bins which result in lower memory usage.

3. **Better accuracy than any other boosting algorithm:** It produces much more complex trees by following leaf-wise split approach rather than a level-wise approach which is the main factor in achieving higher accuracy. 

4. **Compatibility with Large Datasets:** It is capable of performing equally good with large datasets with a significant reduction in training time as compared to XGBOOST.

5. **Parallel learning supported.**(like a random forest)



Quote from a algorithm engineer from Tencent Music who interviewed me (I did not get the job because I am in New York and Tencent is in Shenzhen(time zone conflict), plus I did not do so well in the coding test), "We don't spend too much time on model tuning or searching for hyperparameters. There are more important things to do such as finding the key features! (or pre-train model if we don't have enough data)" 

Yeah, domain knowledge counts a lot. When I was a quant research intern in Guolian Security, I tried hard to learnt as much as possible about the stock market to include more important features in my model (by asking my tutors and reading articles). Coding just a skill, but the curiosity to know about your product is the key (indeed, sometimes I think it is waste of time because I feel like it is not my job! I am a coder! What I want to learn is how to build a better model and write efficient code! But, no! What is a better model? Quote from Andrew Ng, "applied machine learning is feature engineering" ).

Yeah, that is pretty much it. You can view the codes and outcome analysis in those .ipynb files (I use Jupyter notebook).
