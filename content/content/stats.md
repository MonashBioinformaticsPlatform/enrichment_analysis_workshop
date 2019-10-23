---
title: Enrichment Statistics
weight: 2
---


Enrichment statistics are based on a contingency table like so:

|        Gene        | ..in term | ..not in term | Total |
|:------------------:|----------:|--------------:|------:|
|     ..in gene list |        50 |           100 |   150 |
| ..not in gene list (but in background) |       200 |         15900 | 16100 |
|              Total |       250 |         16000 | 16250 |


This is based on the 16250 genes that were measured in your experiment. 

Note that there might be extra genes that weren't measured these are excluded from the calculations entirely. E.g. There might have been an extra 5000 terms (some of which might have been annotated with the term of interest), making for 21250 _annotated_ genes.



---

### Interactive Calculator

[*Link to open toy enrichment calculator*](https://bioinformatics3.erc.monash.edu/rsconnect/connect/#/apps/40/access). 

This calculates enrichment for a single hypothetical genelist (e.g. your RNAseq differentially expressed genelist) against a single hypothetical 'term' (some set of interesting genes, e.g. synaptic signaling genes). It makes a Venn diagram and a wordy description of what is being tested.

You can adjust various factors and see their effect on the enrichment p-values. 


> _Note:_ This is just a toy calculator for this training, it quite limited. Bonus points if you break it. There are online hypergeometric test or fishers exact test calculators available if you ever need to calculate this directly e.g. : https://keisan.casio.com/exec/system/1180573201  


---

##### Questions 

If 20 of the 300 differentially expressed genes are annotated with the 500-gene term of interest.

1. Is it significant at p=0.05? {{%expand Show%}}No, corrected pval=0.087{{%/expand%}}

2. What about with a smaller background of 5000 genes (e.g. proteomic datasets) {{%expand Show%}} Even less so - corrected pval=1 {{%/expand%}}

3. Or, testing against a smaller database of terms; 2000 terms instead of 10000? With the original 16000 gene background.
{{%expand Show%}} Yes, now corrected pval=0.017 {{%/expand%}}

4. 19 out of 200 differentially expressed genes (9.5%), need to hit for a 500-gene term (3.1% of all genes) to be significant at (p=0.048). How many hits would be needed for a more specific 30-gene term? 
{{%expand Show%}} 5 hits - 2.5% of the differentially expressed genes vs 0.19% of all genes {{%/expand%}}

