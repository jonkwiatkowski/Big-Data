# big-data-challenge
My submission for Assignment 22

# Unit 22 Homework: “Alexa, Can You Handle Big Data?”

## Background

In this assignment, you will put your ETL skills to the test. Many of Amazon's shoppers depend on product reviews to make a purchase. Amazon makes these datasets publicly available. They are quite large and can exceed the capacity of local machines. One dataset alone contains over 1.5 million rows; with over 40 datasets, data analysis can be very demanding on the average local computer. Your first goal for this assignment will be to perform the ETL process completely in the cloud and upload a DataFrame to an RDS instance. The second goal will be to use PySpark or SQL to perform a statistical analysis of selected data.

This homework assignment contains two levels. The second level is optional but highly recommended.

1. Create DataFrames to match production-ready tables from two big Amazon customer review datasets.

2. Analyze whether reviews from Amazon's Vine program are trustworthy.

- - -

## Datasets

* [Video Game Review Dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz)

* [Mobile Electronic Review Dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Mobile_Electronics_v1_00.tsv.gz)

- - -

## Instructions

### Level 1

* Use the provided schema to create tables in your RDS database.

* Create two separate Google Colab notebooks and **extract** any two datasets from the list at [review dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt). Put each dataset into its own notebook.

  **Note:** You could ETL both data sources in a single Colab notebook, but it will be easier to work with these large S3 data sources in separate notebooks.

* Be sure to handle the header correctly. If you read the file without the header parameter, you may find that the column headers are included in the table rows.

* Complete the following steps for each notebook (one dataset per notebook).

  * Count the number of records (rows) in the dataset.

  * Transform the dataset to fit the tables in the [schema file](../Resources/schema.sql). Be sure that the DataFrames match in data type and in column name.

  * Load the DataFrames that correspond to tables into an RDS instance. **Note:** This process can take up to 10 minutes for each. Ensure that everything is correct before uploading.

### Level 2

In Amazon's Vine program, reviewers receive free products in exchange for reviews.

Amazon has several policies to reduce the bias of its Vine reviews: [https://www.amazon.com/gp/vine/help?ie=UTF8](https://www.amazon.com/gp/vine/help?ie=UTF8).

But are Vine reviews truly trustworthy? Your task is to investigate whether Vine reviews are free of bias. Use either PySpark or, for an extra challenge, SQL to analyze the data.

* If you choose SQL, first use Spark on Colab to extract and transform the data and then load it into a SQL table on your RDS account. Perform your analysis with SQL queries on RDS.

* While there are no strict requirements for the analysis, consider steps you can take to reduce noisy data, such as filtering for reviews that meet a certain number of helpful votes, total votes, or both.

* Submit a summary of your findings and analysis.


- - -

## References

* Amazon customer Reviews Dataset. (n.d.). Retrieved April 08, 2021, from: [https://s3.amazonaws.com/amazon-reviews-pds/readme.html](https://s3.amazonaws.com/amazon-reviews-pds/readme.html)
* Assignment 22 instructions.
* Dom's `CloudEtlDemo.ipynb`
