#NGS-related plots along with example R code<br/>

Quality Score Distribution Plot:

```R
library(ShortRead)
fastq_file <- "path/to/your/sequencing_data.fastq"
quality_scores <- quality(FastqFile(fastq_file))
plot(quality_scores, main="Quality Score Distribution", xlab="Quality Score", ylab="Frequency")
```
Base Composition Plot:

```R
library(seqinr)
fastq_file <- "path/to/your/sequencing_data.fastq"
base_composition <- alphabetFrequency(readFastq(fastq_file))
barplot(base_composition, main="Base Composition", xlab="Nucleotide", ylab="Frequency")
```
Read Length Distribution Plot:

```R
library(Bioconductor)
fastq_file <- "path/to/your/sequencing_data.fastq"
read_lengths <- sapply(getSeq(readFastq(fastq_file)), nchar)
hist(read_lengths, main="Read Length Distribution", xlab="Read Length", ylab="Frequency", col="skyblue")
```
Coverage Plot using Gviz:

```R
library(Gviz)
bam_file <- "path/to/your/aligned_reads.bam"
genome_annotation <- "path/to/your/genome_annotation.gff"
track <- DataTrack(range=import.gff(genome_annotation), type="gene")
plotTracks(alignments=bam_file, genome=genome_annotation, chromosome="chr1", name="Alignment", tracks=list(track))
```
Volcano Plot for Differential Expression:

```R
library(DESeq2)
dds <- DESeqDataSetFromHTSeqCount(sampleTable=sample_metadata, directory="path/to/your/counts_directory", design=~condition)
dds <- DESeq(dds)
res <- results(dds)
plotMA(res, main="Volcano Plot", ylim=c(-2, 2), pvalThreshold=0.05)
```
Principal Component Analysis (PCA) for Gene Expression:

```R
gene_expression <- read.csv("path/to/your/gene_expression_data.csv")
pca_result <- prcomp(gene_expression[, -1], scale.=TRUE)
summary(pca_result)
```
Heatmap for Gene Expression:

```R
library(pheatmap)
gene_expression <- read.csv("path/to/your/gene_expression_data.csv")
pheatmap(gene_expression[, -1], main="Gene Expression Heatmap", cluster_rows=TRUE, cluster_cols=TRUE)
```
Correlation Matrix Plot for Gene Expression:

```R
gene_expression <- read.csv("path/to/your/gene_expression_data.csv")
correlation_matrix <- cor(gene_expression[, -1])
image(correlation_matrix, main="Correlation Matrix", xlab="Genes", ylab="Genes")
```
Read Distribution across Genomic Features:

```R
library(Rsubread)
bam_file <- "path/to/your/aligned_reads.bam"
annotation_file <- "path/to/your/genome_annotation.gtf"
feature_counts <- featureCounts(bamfile=bam_file, annot.ext=annotation_file)
print(feature_counts)
```
Gene Set Enrichment Analysis (GSEA) Plot:

```R
library(clusterProfiler)
gene_list <- results_table$gene
enrich_result <- enrichGO(gene_list, OrgDb="org.Hs.eg.db", keyType="ENSEMBL", ont="BP", pvalueCutoff=0.05)
dotplot(enrich_result, showCategory=15)
```
