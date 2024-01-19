Data Wrangling and Cleaning:

Selecting specific columns from a genomic data frame.

R
Copy code
selected_columns <- genomic_data[, c("GeneID", "Expression")]
Merging two datasets based on a common identifier.

R
Copy code
merged_data <- merge(dataset1, dataset2, by = "common_id")
Reshaping data from wide to long format.

R
Copy code
long_format_data <- melt(wide_format_data, id.vars = "SampleID")
Aggregating data to summarize values by group.

R
Copy code
summarized_data <- aggregate(counts ~ condition, data = gene_expression, FUN = mean)
Creating a new variable based on conditional logic.

R
Copy code
gene_expression$high_expression <- ifelse(gene_expression$counts > 10, "high", "low")
