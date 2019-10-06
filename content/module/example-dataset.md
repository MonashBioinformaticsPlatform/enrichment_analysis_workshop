---
title: "Example Analysis: SH-SY5Y Differentiation"
date: 2019-08-30
---

## SH-SY5Y Differentiation

SH-SY5Y is a commonly used neuroblastoma cell line. 
With appropriate treatment, it can be induced to differentiate into a ‘more neuronal’ form. 
Differentiated cells look quite different, growing thin neurites out from the body of the cell.


![shsy5](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/shsy5ydiff.png)
<!-- seems to point to content dir not commo root : ![shsy5](/img/shsy5ydiff.png)-->

_Image from Figure 4 (Pezzini et al. 2017)_


## The question: What pathways are involved in SH-SY5Y Differentiation?

In their paper [_Transcriptomic Profiling Discloses Molecular and Cellular Events Related to Neuronal Differentiation in SH-SY5Y Neuroblastoma Cells_](https://link.springer.com/article/10.1007%2Fs10571-016-0403-y) 
Pezzini et al induced differentiation of the SH-SY5Y Neuroblastoma cell line and measured transcriptomic changes via RNAseq (Pezzini et al. 2017). 
They then looked at functional enrichment of differentially expressed genes.


## The data : Differentially expressed genes

The example dataset for today is the differential expression results.  

They can be accessed via this link: 
http://degust.erc.monash.edu/degust/compare.html?code=5b2c7805ab8f8c5f2dc8c72e61b049b0#?plot=mds

This has been reanlysed from the published raw data, via the degust tool. 

NB: Other tools and approaches will have different looking results - but generally you will end up with a table of genes with some measure of statitical confidence. 
The methods for functional enrichment analysis should be similar.

















