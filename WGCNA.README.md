Weighted Gene Co-expression network Analysis with R:<br/>

Building a weighted gene co-expression network.

```R
library(WGCNA)
network_data <- blockwiseModules(expression_data, power = 6, TOMType = "unsigned", minModuleSize = 30)
```
Visualizing the network modules.

```R
plotDendroAndColors(network_data$dendrograms$merge, network_data$colors)
```
Identifying hub genes within modules.

```R
hub_genes <- moduleEigengenes(network_data)$eigengenes
```
Enrichment analysis of gene modules.

```R
module_genes <- network_data$colors$module
enriched_terms <- enrichGO(module_genes, universe = all_genes, OrgDb = org.Hs.eg.db)
```
Visualizing module-trait relationships.

```R
plotModuleTrait(network_data, "condition")
```
