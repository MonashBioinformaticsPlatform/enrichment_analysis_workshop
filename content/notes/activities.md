---
title: "Activities"
date: 2019-09-30T16:30:37+10:00
draft: false
weight : 21
---


This is to be merged into sections by topic.


## Activity - Getting a list of DE genes


SH-SY5Y is a widely-used neuroblastoma cell line. 
With approriate treatment, they can be readily differentiated from their base state 
into a more neuronal phenotype. 

In their paper [_Transcriptomic Profiling Discloses Molecular and Cellular Events Related to Neuronal Differentiation in SH-SY5Y Neuroblastoma Cells_](https://link.springer.com/article/10.1007%2Fs10571-016-0403-y) 
Pezzini et al induced differentiation of the SH-SY5Y Neuroblastoma cell line and measured transcriptomic changes via RNAseq (Pezzini et al. 2017).


Here are some differential expression results from their raw data:
http://degust.erc.monash.edu/degust/compare.html?code=5b2c7805ab8f8c5f2dc8c72e61b049b0#?plot=mds


1.  Download the full table of data from degust.  Import into excel. <!-- File>Import -->

2.  QUESTION: How many genes are differentially expressed?

    - Significant at 0.01? (FDR Column = Corrected P-value)   **6391 ( this is massive )**
    - And because there are so many in this experiment (its a massive change to cells) -  At 2-fold up/down regulated? **2412 (still very large!)**    
    - And (Just for this exercise!) -  take significance at p<1x10^-7, with 2x fold change? This is a ridiculous threhsold - typically you would only filtere at p<0.01 (and occasionally 2fold change) but the difference between the two cell conditions is pretty extreme! This threshold gives a more normal number of differentially expressed genes for downstream analysis. **168**
    NB: The 'differentiated' column shows the log2 fold-change of differentiated cells vs untreated cells (log2(diff)-log2(undiff)). 0 is unchanged.

3. QUESTION: How many genes are _tested_? This is your background.
    - But with ~20k human genes - why are there genes missing? **14420**

4. COMMON GOTCHA: Can you find SEPT4?
    - Because [_Gene name errors are widespread in the scientific literature_](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-1044-7)
    - You can't fix it automatically (try converting it to text!). You have to avoid it by importing gene columns as 'text' columns in excel. See video from HUGO : https://www.genenames.org/help/faq/#!/#tocAnchor-1-25-1
    - NB: You can ignore these for this workshop, but you want this to be right for publication!



## Enrichment stats interactively

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


## End of session Challenge : Dr Dodge's Experiment

There's quite a few ways you can calculate functional enrichment - so there's always a risk of [p-hacking](https://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1002106), wheather accidental or deliberate. 

_So lets go deliberate..._

Dr Dodge is convinced that your experiment should turn out with relevants to GO term 'segmentation' (don't ask why..) but p=0.06! But they must be significant, the paper has to be submitted by Friday! 

What hacky and statsticically questionable approaches could you apply to call these results ''significant''?
