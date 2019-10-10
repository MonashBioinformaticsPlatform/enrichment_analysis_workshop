---
title: "Enrichment Tools"
date: 2019-08-30
weight: 7
---


## Enrichment in gProfiler?

Try gprofiler GOSt for functional enrichment: https://biit.cs.ut.ee/gprofiler/gost

Using the 168 differentially expressed gene list.

NB: Set the background gene list with _Advanced Options > Statistical Domain scope > Custom : Paste in genelist _


## Enrichment in DAVID 

_(Maybe skip?) Main point is that different tools give different results despite using the same databases! Though david has some nice features._

Try calculating funtional enrichment in DAVID:  https://david.ncifcrf.gov/

Use the 168 differentially expressed gene list and the background set.

NB: Need to use ensembl Ids (e.g. ENSG00000170075) for a background in DAVID, it won't allow gene names due to potential ambiguity. Select "ENSEMBL_GENE_ID" for id type.

1. QUESTION : Look at the results for the GO terms. Why is it different to gProfiler?

2. QUESTION : Look at the KEGG results for Cellular adhesion molecules. Its not significant, but is it useful?

ANSWER:
  - Same DB, different tools. GO is a tree and gets carved in differen ways.
  - P-value isn't everything. Those few genes are hitting interactiving molecules within the neural system. The immune system is irrevant to this experiment.



## Explore in String?

Exlore protein-protein interactions with STRING: https://string-db.org

Use the 168 differentially expressed genes. No background needed for this one, not interested in calculating the enrichment.

QUESTION: Click through on the interactions to see what the evidence for a protein-protein interaction is. Do you trust that interaction?


## Explore in Reactome?

Expore enrichment in the the pathway browser of reactome : https://reactome.org/

Go to 'analyse data' and paste the 168 differentially expressed genes. No background. 

QUESTION: Click through 'Syndecan Interactions' And expand it one the left hand tree. 

QUESTION: Go back to https://reactome.org/ and search for your favourite pathway/process/gene. Is it covered?
