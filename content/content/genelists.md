---
title: "Defining the genelist"
date: 2019-08-30
weight: 6
---

SH-SY5Y is a widely-used neuroblastoma cell line. 
With approriate treatment, they can be readily differentiated from their base state 
into a more neuronal phenotype. 

In their paper [_Transcriptomic Profiling Discloses Molecular and Cellular Events Related to Neuronal Differentiation in SH-SY5Y Neuroblastoma Cells_](https://link.springer.com/article/10.1007%2Fs10571-016-0403-y) 
Pezzini et al induced differentiation of the SH-SY5Y Neuroblastoma cell line and measured transcriptomic changes via RNAseq (Pezzini et al. 2017).


Here are some differential expression results from  their raw data:
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
