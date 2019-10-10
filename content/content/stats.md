---
title: Enrichment analysis statistics
weight: 2
---


Check out the toy enrichment calculater [here](https://bioinformatics3.erc.monash.edu/rsconnect/connect/#/apps/40/access)


1. QUESTION: If 17 of the 168 differentially expressed genes are annotated with the 500-gene term of interest. Is it significant?
    - Smaller backround (e.g. proteomic dataset) 
    - Fewer annotation terms tested?

2. QUESTION : How many of the of the 168 differentially expressed genes have to be annotated with a 500-gene term of interest for it to be significant at p=0.05?
    - What about a term with 30 annotated genes?


ANSWER 
    - No, corrected pval=0.217 
    - 19 genes == 11% bs the 3.5% of bg 
    - 5 / 30 genes = ~3% vs 0.2% of bg
    

NB: This is just a toy calculator for this training, it is quite constrained. Bonus points if you break it. There are likely many better ones online e.g. : https://keisan.casio.com/exec/system/1180573201

