Data transformation and reshaping:

Log-transforming gene expression data.

```R
log_transformed_data <- log2(gene_expression + 1)
```
Scaling and centering numeric variables.

```R
scaled_data <- scale(numeric_data)
```
Pivoting data from long to wide format.

```R
wide_format_data <- spread(long_format_data, key = variable, value = value)
```
Recoding categorical variables.

```R
recoded_data <- recode(factor_data, "1" = "Low", "2" = "Medium", "3" = "High")
```
Applying a custom function to transform data.

```R
transformed_data <- apply_function(raw_data, custom_transformation_function)
```
