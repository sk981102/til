# Day 1 - Today I learn

Date : 11/17/2024

Got a new mac mini from the Apple store. and I am very motivated to start this journey again. Wonder if I will stick to it this time around. 

Here are the list of things I want to learn...

- Polars
- Rust Programming
- Large Language Model Applications
- Out of Distribution Generalization 
- SMOTE for Imbalanced Data
- AWS Architecture/Credentials

## Polars

I main want to learn Polars because 1) it has been getting a lot of hype 2) it apparently is much faster than the regular pandas dataframe. I wonder how applicable the Polars dataframe will be for my work. 

Here are the observations so far from my brief skimming through various blogs. 

### Fast Run time
Polars fundamentally employ Apache Arrow model, similar to Spark, which is columnar and optimized for efficient data storage and processing. This allows for vectorized operations and reduces memory overhead compared to Pandas' row-based storage.

Lot of people bring up the fact that Polars enable Lazy Evaluations, but I wonder how much difference that makes realistically. From my experience of working with Dask Dataframe, which also supports the Lazy Evaluation framework. However, I wasn't able to reap a real meaningful outcome from the framework for my applications/problems.

Because the dataframe is columnar, it inherently allows the user to have parallelization in mind. 

### Syntax & Learning Curve
So far, I do not see any big hurdles when it comes to implementation to my work. One downside is that since the library is relatively new, for it to be integrated with ML training libraries like Sklearn or XGboost, the pl dataframes need to be converted to numpy arrays. 

Syntatically, I noticed that they are quite similar to pyspark. Presumably because both frameworks are made to deal with tabular data in columnar matter. For a frequent spark user like myself, the learning curve does not seem too bad, but will update as I continue to learn. 