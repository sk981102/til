# Day 2 - Today I learn

Date : 11/18/2024

D-32 until the EOY vacation. I am very looking forward to seeing my parents and visit Austria & Portugal this Christmas. I am thinking of an effective way to integrate my learnings with work schedule, so that I can create a consistent habit.


## Polars

Today, I went through the course material & notebooks from `Data Analysis with Polars` on Udemy.

### Initial Impression
I liked that they show you the data types on the column, and can customize dataframe show functions. This can help the user to skip a step of explicitly printing out the datatypes. 
You can still use indexing such as `dataframe[row,columns]` like Pandas dataframe, though those are not very parallelizable by nature.
As mentioned in the previous TIL, the function chain style is very similar to pyspark. 

You can also batch compute using `streaming=True` in the `collect()`.

### Lazy DataFrame
Lazy evaluation is essentially a query plan for Polars to optimize the queries. Using `explain()`, you can see how the query is getting optimized, and further optimize as you see fit. 

The main limitation of the lazy mode is that the evaluation must know the column names and dtypes of each step of the query plan, meaning functions like `pivot` must be evaluated immediately.

#### Query Optimization in Polars
Though I conceptually knew of these optimization techniques, it was nice to have a framework around it and consider them as I write my own code. 
- `Projection Pushdown`: limit the number of columns required
- `Predicate Pushdown` : filter as much as possible early on
- `Slice Pushdown`: limit the number of rows required
- `Column Subplain Elimination`: run duplicate transformation once
- `Common Subexpression Elimination`: duplicate expressions are cached
    - This was the example given after the `explain()` function where the output will tell you the list of expressions that were cached.