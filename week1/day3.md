# Day 3 - Today I learn

Date : 11/19/2024

As a student, even as a graduate student, I never fully appreciated the value of holidays, but as a mid-20s 9-5 corporate weapon, I cannot wait for Thanksgiving/Christmas to see family and friends. 

## Polars

Like yesterday, I spent some time running through the polars example notebook mainly focusing on the DataTypes and the Polars Dataframe. 

### Data Types 
When you operate a function on datatypes in the same category - i.e. Int32 and Int64 - the polars will cast the output to the larger super set data types. This characteristic is called Supertypes. 

You can use `df.schema()` function to see the data types, although you can see the datatypes when you call the `df.head()` function. 

### Polars DataFrame and Its Compatibility
The polars dataframe is very similar to the pandas dataframe counterpart. For example, the concept of DataFrame vs. Series are the same; you can always convert them to different formats like np.array or list using `to_{array}()` functions. 

One main difference conceptually is that the polars dataframe refers to Apache Arrows array per column. This enables faster calculation and optimized memory savings, and it also means that the sharing data can be done without any copy. You just point the new dataframe to the existing Apache Arrows array. 

The main downside of this format is that linear algebra functionalities will be naturally limited; this can become a major downside in Machine Learning model training where the linear algebraic calculations are musts. That makes sense why the current model training libraries require the polars dataframe to be converted back to the numpy arrays. 