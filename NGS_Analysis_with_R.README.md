NGS Analysis with R – RNASeq Analysis:

Aligning RNA-Seq reads to the reference genome.

```R
library(Rsubread)
aligned_reads <- align("path/to/reads.fastq", reference = "path/to/genome.fasta")
```
Counting gene expression using featureCounts.

```R
library(Rsubread)
count_matrix <- featureCounts(files = "path/to/aligned_reads.bam", annot.inbuilt = "hg38")
```
Differential gene expression analysis using DESeq2.

```R
library(DESeq2)
dds <- DESeqDataSetFromMatrix(countData = count_matrix, colData = sample_metadata, design = ~ condition)
result <- DESeq(dds)
```
Visualizing differential expression results with volcano plot.

```R
library(ggplot2)
volcano_plot <- ggplot(result, aes(x = log2FoldChange, y = -log10(pvalue))) + geom_point()
```
Clustering and heatmap visualization of gene expression.

```R
library(pheatmap)
heatmap_data <- assay(assay(result, "normalizedCounts"))
pheatmap(heatmap_data)
```
