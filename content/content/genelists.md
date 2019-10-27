---
title: "Defining the genelist"
date: 2019-08-30
weight: 6
---



Starting from those differential expression results [here](http://degust.erc.monash.edu/degust/compare.html?code=5b2c7805ab8f8c5f2dc8c72e61b049b0#?plot=mds), how do we go about getting a genelist to calculate enrichment on? 


##### Activities

1. Download the full table of data from either degust, or the tsv file here:
[Pezzini2016_SHSY5Ycelldiff_DE_table.tsv](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/data/Pezzini2016_SHSY5Ycelldiff_DE_table.tsv). Import into excel. <!-- File>Import -->


2. How many genes are differentially expressed? In these results the FDR Column contains the corrected p-value, and the 'differentiated' column shows the log2 fold-change of differentiated cells vs untreated cells (log2(diff)-log2(undiff)). 0 is unchanged.

    - Significant at 0.01? 
    - That's a particularly large number of genes - perhaps not unexpected given how much the cells are changed this experiment. How many significant genes also have 2-fold change in expression?

    - For this workshop, get the genes with a FDR <1x10^-4 and 2x fold change. Note that this is a ridiculous threshold - typically you would only filter at p<0.01 (and occasionally 2-fold change) but the difference between the two cell conditions is pretty extreme! However, this arbitrary threshold gives a more typical number of differentially expressed genes for downstream analysis. An alternative approach could be to take the top 500 genes.

    {{%expand Show%}} There are 4923 differentially expressed genes, 2149 of which have a 2-fold change in expression. With the aggressive filtering - there are 198 genes left {{%/expand%}}


3. How many genes are _tested_? This is your background.
{{%expand Show%}} 14420 genes tested. {{%/expand%}}

<!--But with ~20k human genes - why are there genes missing? **14420** --> 

---

##### Common gotcha

Can you find SEPT4? Because [_Gene name errors are widespread in the scientific literature_](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-1044-7)

You can't revert the gene names automatically (try converting it to text!). You have to avoid it in the first place by importing gene columns as 'text' columns in excel.  See video from HUGO : https://www.genenames.org/help/faq/#!/#tocAnchor-1-25-1

<!--NB: You can ignore these for this workshop, but you want this to be right for publication!-->
