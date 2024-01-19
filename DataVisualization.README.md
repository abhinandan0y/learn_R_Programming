#Data visualization with ggplot2:<br/>

Creating a scatter plot for gene expression.

```R
library(ggplot2)
ggplot(gene_expression, aes(x = condition, y = counts)) + geom_point()
```
Generating a bar plot for sample distribution.

```R
ggplot(sample_distribution, aes(x = sample_type, fill = condition)) + geom_bar()
```
Plotting a line chart for time-course gene expression.

```R
ggplot(time_course_data, aes(x = time_point, y = expression, group = gene)) + geom_line()
```
Creating a boxplot for comparing expression across conditions.

```R
ggplot(gene_expression, aes(x = condition, y = counts)) + geom_boxplot()
```
Visualizing genomic features using a genomic track plot.

```R
library(GenomicRanges)
plotTracks(genomic_features, from = start(genomic_features), to = end(genomic_features))
```
