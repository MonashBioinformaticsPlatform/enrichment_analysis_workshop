---
title: "Enrichment Tools"
date: 2019-08-30
weight: 7
---


We're going to use the small 168-gene set for all these enrichment tools. If you don't have them already, they are available here:

As gene symbols (CD2, DLG4 e.t.c).

* [168-gene differentially expressed gene list](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/data/Pezzini2016_SHSY5Ycelldiff_DE_genelist_as_genenames.txt)
* [Background list](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/data/Pezzini2016_SHSY5Ycelldiff_bg_genelist_as_genenames.txt)

As ensemble gene ids (e.g. ENSG00000183654). Harder to read, but some tools need unambiguous IDs like this for performance reasons when working with larger geneslists; e.g. PANTHER or DAVID background or STRING without a specified organism.  

* [168-gene differentially expressed gene list](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/data/Pezzini2016_SHSY5Ycelldiff_DE_genelist_as_ensemblID.txt)
* [Background list ](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/data/Pezzini2016_SHSY5Ycelldiff_bg_genelist_as_ensemblID.txt)

---

### Enrichment in gProfiler?

Try gProfiler GOSt for functional enrichment: https://biit.cs.ut.ee/gprofiler/gost

Use the 168 differentially expressed gene list. Check out the results, and keep them open for the next step. 

Note: Set the background gene list with  _Advanced Options_ > _Statistical Domain scope_ > _Custom over annotated Genes_ . This includes anything in your background that has any annotation. 

1. Whats the most enriched GO Biological process term? 

> Note: Under advanced options there is also an option to calculate _underrepresentation_ - a lack of a certain term in the query list. There's not enough statistical power to show anything for this example.



### Enrichment in PANTHER

Next try PANTHER :  https://david.ncifcrf.gov/

Under _Select Analysis_ choose the _Statistical Overrepresentation test_ , with the 
'GO Biological Process (BP) complete' annotation set. 

PANTHER prompts for the background set after hitting next. Under _Upload List_ Browse for the text file (linked above) that contains background genes in *ensemblID* format.


##### Question

2. Look at the results for the GO terms. How does it compare to gProfiler? What about the GO-slim annotation?


### Explore in String

Explore protein-protein interactions with STRING: https://string-db.org

Paste the 168 differentially expressed genes into the 'Multiple proteins' option, and select human. You can accept gene mappings on the next screen with 'continue'.

 No background needed for this one, since we're not interested in calculating the enrichment.

##### Question

3. Click through on the interactions lines to see what the evidence for a interaction is. Do you trust that interaction?


### Explore in Reactome

Explore enrichment in the the pathway browser of reactome : https://reactome.org/

Go to 'analyse data' and paste the 168 differentially expressed genes. No background.

Click through 'Syndecan Interactions', expand it one the left hand tree, then click one of the subpathways to zoom in on the pathway view. 


##### Question

4. Go back to https://reactome.org/ and search for your favourite pathway or process. Is it covered?




### Enrichment in DAVID 

Try calculating functional enrichment in DAVID:  https://david.ncifcrf.gov/

NB: Need to use ensembl Ids (e.g. ENSG00000170075) for a background in DAVID, it won't allow gene names due to potential ambiguity. Select "ENSEMBL_GENE_ID" for id type.

##### Question

5. Look at the KEGG results for Cellular adhesion molecules. Its not significant, but is it useful?

<!--
P-value isn't everything. Those few genes are hitting interactiving molecules within the neural system. The immune system is irrevant to this experiment.
--> 
