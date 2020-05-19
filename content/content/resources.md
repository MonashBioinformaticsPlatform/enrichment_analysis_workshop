---
title: "Resources"
date: 2019-08-30
weight: 9
---

Please find a link to today's presentation slides [here](https://tinyurl.com/enrichment-material)


-----

The following tools might be useful for downstream functional analysis; this includes some not covered in todays workshop. 

<!-- https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/shsy5ydiff.png) 
http://localhost:1313/enrichment_analysis_workshop/img/david.png
--> 

Note that most of these tools do more than just enrichment tests, and some include their own databases. 

### g:Profiler / g:GOSt

https://biit.cs.ut.ee/gprofiler/gost

The g:GOSt 'functional profiling' tool of g:Profiler calculates 
It has a clean modern interface and a handy summary of which genes contribute to the enrichment. 

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/gprofiler.png)

### PANTHER 

http://www.pantherdb.org/

PANTHER performs overrepresentation tests across multiple databases; Gene ontology, reactome, PANTHER pathways and protein classes. Allows more control over the statistical test used and clearly summarises what was actually done.

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/panther.png)

### DAVID 

https://david.ncifcrf.gov/

Via its 'functional annotation' tool, DAVID allows you to calculate functional enrichment across a number of databases ; Gene Ontology, KEGG, reactome and others. Reliable, with a slightly clunky interface.

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/david.png)

### Enrichr

https://amp.pharm.mssm.edu/Enrichr/

Enrichr easily calculates enrichment across a wide range of databases. Currently does not allow for a background set. 

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/enrichr.png)



### Reactome

https://reactome.org/

The core of reactome is the reactome pathways and browser. ALthough other tools use the reactome database, the reactome website provides a means to browse enrichment within the pathway browser view.

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/reactome.png)



### Biocyc

https://biocyc.org/

Biocyc is another suite of tools for enrichment and pathway browsing, which is particularly useful for prokaryotic work. It is licensed, but Monash does have a license.

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/biocyc.png)



### STRINGdb

https://string-db.org/

STRING is not a functional enrichment tool, rather it is a convenient way to explore interactions within a genelist. Results are viewed as an interaction network. Best suited to smaller genelists.

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/string.png)


### Gene Ontology

http://geneontology.org/

Gene Ontology (GO) terms are the most widely use set of functional annotations, used by many enrichment tools. The gene ontology resource website itself provides several tools for browsing the GO term hierarchy.

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/go.png)

### KEGG

https://www.genome.jp/kegg/

A well known curated pathway database. It is used by many other tools but with a caveat - KEGG moved to a subscription model in 2011, and so enrichment tools need to use the last open release from 2011. However up to date KEGG pathways are browsable directly through their website. 

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/kegg.png)


### GSEA and MSigDB

http://software.broadinstitute.org/gsea/index.jsp

The desktop-based GSEA tool is (one of many) gene set enrichment approaches. It uses of gene rankings across all genes rather than hypogeometric or fishers-exact tests of genelist enrichment.  MSigDB (Molecular signatures database) is a suite of annotation databases suitable for GSEA analysis.

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/gsea.png)


### MetaboAnalyst
MetaboAnalyst is popular among the metabolomics community for statistical, functional and integrative analysis of metabolomics data. It has a feature called **Functional enrichment analysis**, which performs metabolite set enrichment analysis, metabolic pathway analysis, and pathway activity prediction from MS peaks.

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/metaboanalyst.png)

### Cytoscape

https://cytoscape.org/

Cytoscape is a desktop-based biological network analysis / visualization tool, rather than a functional enrichment tool (although plugins can change that). It is mentioned here because it is often useful as a next step when you need to create custom figures showing the interactions of an interesting biological pathway. 

![](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/img/cytoscape.png)

