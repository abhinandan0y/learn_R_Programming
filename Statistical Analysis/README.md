#Common statistical analyses Codes

Descriptive Statistics for Read Lengths:

```R
library(Bioconductor)
fastq_file <- "path/to/your/sequencing_data.fastq"
read_lengths <- sapply(getSeq(readFastq(fastq_file)), nchar)
summary_stats <- summary(read_lengths)
print(summary_stats)
Description: Computes basic descriptive statistics (mean, median, min, max) for read lengths.
```
Quality Score Statistics:

```R
library(ShortRead)
fastq_file <- "path/to/your/sequencing_data.fastq"
quality_scores <- quality(FastqFile(fastq_file))
summary_stats <- summary(quality_scores)
print(summary_stats)
Description: Provides summary statistics for quality scores, including mean, median, and quartiles.
```
Differential Expression Analysis with DESeq2:

```R
library(DESeq2)
dds <- DESeqDataSetFromHTSeqCount(sampleTable=sample_metadata, directory="path/to/your/counts_directory", design=~condition)
dds <- DESeq(dds)
results_table <- results(dds)
write.csv(results_table, file="differential_expression_results.csv")
Description: Performs differential expression analysis using DESeq2 and exports the results to a CSV file.
```
Correlation Analysis of Gene Expression:

```R
gene_expression <- read.csv("path/to/your/gene_expression_data.csv")
correlation_matrix <- cor(gene_expression[, -1])  # Assuming the first column is gene names
print(correlation_matrix)
Description: Computes the correlation matrix for gene expression data.
```
Principal Component Analysis (PCA) for Gene Expression:

```R
gene_expression <- read.csv("path/to/your/gene_expression_data.csv")
pca_result <- prcomp(gene_expression[, -1], scale.=TRUE)
summary(pca_result)
Description: Performs PCA on gene expression data and displays summary statistics.
```
Gene Set Enrichment Analysis (GSEA):

```R
library(clusterProfiler)
gene_list <- results_table$gene
enrich_result <- enrichGO(gene_list, OrgDb="org.Hs.eg.db", keyType="ENSEMBL", ont="BP", pvalueCutoff=0.05)
print(enrich_result)
Description: Conducts gene set enrichment analysis using clusterProfiler on the differential expression results.
```
Read Distribution across Genomic Features:

```R
library(Rsubread)
bam_file <- "path/to/your/aligned_reads.bam"
annotation_file <- "path/to/your/genome_annotation.gtf"
feature_counts <- featureCounts(bamfile=bam_file, annot.ext=annotation_file)
print(feature_counts)
Description: Counts the number of reads mapped to different genomic features using featureCounts.
```
Chi-Square Test for Nucleotide Composition:

```R
library(seqinr)
fastq_file <- "path/to/your/sequencing_data.fastq"
base_composition <- alphabetFrequency(readFastq(fastq_file))
chisq_result <- chisq.test(base_composition)
print(chisq_result)
Description: Performs a chi-square test to assess if the nucleotide composition is significantly different from the expected.
```
