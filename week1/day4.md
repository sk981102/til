# Day 4 - Today I learn

Date : 11/20/2024

First rainy day in awhile. I wonder if burnout is inevitable regardless of work-life balance. I desire some change and challenge career wise right now though any new job or a change will result in more work - hence, worse work-life-balance. 

## Polars
The main takeaway is that join, column modification, filtering, and groupby functions are all similar to that of Pandas Dataframe and PySpark. One learning is that on both Pandas and Polars library, you can map 1:m relationship using `validate` parameter in `join()`.

The parquet files portion of I/O was quite interesting. A Parquet File is made for Apache Arrow framework, so naturally, the Polars library had many ways to optimize the data load. For example, you can lazy load the data using `scan_parquet()` function and apply the `explain()` to further optimize. 

Polars reads a Parquet file in parallel. It can do this by either reading columns in parallel or row groups in parallel. 

We can instead tell Polars to do parallelism by `columns` or `row_groups` by setting the `parallel` argument in the `scan_parquet` function. For example, to read columns in parallel

```
(
    pl.scan_parquet(statistics_parquet_file, parallel='columns')
    .collect()
    .head()
)
```

I am getting tired of reading through notebooks, might need to do hands on work to apply the learnings. 

## Time Series
I want to really nail all the statistical concept as the knowledge is quickly fading for me. As my next learning, I will read through this [online material](https://otexts.com/fpp3/index.html), particularly on the section about the Dynamic Linear Regression.