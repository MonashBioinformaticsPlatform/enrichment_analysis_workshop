---
title: "Example Data Preparation"
date: 2019-08-29T12:17:28+10:00
weight: 10
#draft: False
---


SH-SY5Y is a widely-used neuroblastoma cell line. 
With approriate treatment, they can be readily differentiated from their base state 
into a more neuronal phenotype. 

In their paper [_Transcriptomic Profiling Discloses Molecular and Cellular Events Related to Neuronal Differentiation in SH-SY5Y Neuroblastoma Cells_](https://link.springer.com/article/10.1007%2Fs10571-016-0403-y) 
Pezzini et al induced differentiation of the SH-SY5Y Neuroblastoma cell line and measured transcriptomic changes via RNAseq (Pezzini et al. 2017).

-----------

This document describes a simple reanalysis of their raw data, to produce the 
results browseable through degust [here](http://degust.erc.monash.edu/degust/compare.html?code=5b2c7805ab8f8c5f2dc8c72e61b049b0#?plot=mds)


# Methods


## Sequence data download

Data is available in SRA with accession [GSE77383](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE77383).

```sh
# With SRA toolkit 2.8.0
# module load sratoolkit/2.8.0
mkdir fastq
cd fastq
fastq-dump -I --split-files -A SRR3133925_nodiff_rep1 --gzip SRR3133925
fastq-dump -I --split-files -A SRR3133926_nodiff_rep2 --gzip SRR3133926
fastq-dump -I --split-files -A SRR3133927_nodiff_rep3 --gzip SRR3133927
fastq-dump -I --split-files -A SRR3133928_diff_rep1 --gzip SRR3133928
fastq-dump -I --split-files -A SRR3133929_diff_rep2 --gzip SRR3133929
fastq-dump -I --split-files -A SRR3133930_diff_rep3 --gzip SRR3133930
```

## Reference data download

Also downloaded reference genome and genes gtf from [ensembl](http://www.ensembl.org/info/data/ftp/index.html) 
(GRCh38, ensembl release 96).

```sh
mkdir ref_data
cd ref_data
wget ftp://ftp.ensembl.org/pub/release-96/gtf/homo_sapiens/Homo_sapiens.GRCh38.96.gtf.gz
wget ftp://ftp.ensembl.org/pub/release-96/fasta/homo_sapiens/dna/Homo_sapiens.GRCh38.dna_sm.primary_assembly.fa.gz
gunzip Homo_sapiens.GRCh38.96.gtf.gz
```


## Align and count 

Using [RNAsik](https://monashbioinformaticsplatform.github.io/RNAsik-pipe/) (Tsyganov et al. 2018)
pipeline to run QC, alignment and gene counting on these fastqs.

This runs [fastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/), 
[multiQC](https://multiqc.info/) (Ewels et al. 2016), [picard](https://broadinstitute.github.io/picard/), STAR alignment (Dobin et al. 2013) and featureCounts (Liao et al. 2014).

```sh
# Using RNAsik version 1.5.0
RNAsik -fqDir fastqs -counts -paired -qc -multiqc -align star -fastaRef ref_data/Homo_sapiens.GRCh38.dna_sm.primary_assembly.fa.gz -gtfFile ref_data/Homo_sapiens.GRCh38.96.gtf -pairIds _1,_2
```

## Differential expression

The counts table was uploaded to [Degust](http://degust.erc.monash.edu/) for 
processing. 
Genes with at least 10 reads in at least one sample were included,
and limma/voom used for differential expression 
analysis (Ritchie et al. 2015, Law et al. 2014). 

Dataset results acccessible :  http://degust.erc.monash.edu/degust/compare.html?code=5b2c7805ab8f8c5f2dc8c72e61b049b0#?plot=mds

# References

Dobin, Alexander, Carrie A. Davis, Felix Schlesinger, Jorg Drenkow, Chris Zaleski, Sonali Jha, Philippe Batut, Mark Chaisson, and Thomas R. Gingeras. 2013. “STAR: Ultrafast universal RNA-seq aligner.” Bioinformatics 29 (1): 15–21. https://doi.org/10.1093/bioinformatics/bts635.

Ewels, Philip, Måns Magnusson, Sverker Lundin, and Max Käller. 2016. “MultiQC: Summarize analysis results for multiple tools and samples in a single report.” Bioinformatics 32 (19): 3047–8. https://doi.org/10.1093/bioinformatics/btw354.

Law, Charity W, Yunshun Chen, Wei Shi, and Gordon K Smyth. 2014. “voom: Precision weights unlock linear model analysis tools for RNA-seq read counts.” Genome Biology 15 (2): R29. https://doi.org/10.1186/gb-2014-15-2-r29.

Liao, Yang, Gordon K. Smyth, and Wei Shi. 2014. “FeatureCounts: An efficient general purpose program for assigning sequence reads to genomic features.” Bioinformatics 30 (7): 923–30. https://doi.org/10.1093/bioinformatics/btt656.

Pezzini, Francesco, Laura Bettinetti, Francesca Di Leva, Marzia Bianchi, Elisa Zoratti, Rosalba Carrozzo, Filippo M. Santorelli, Massimo Delledonne, Maciej Lalowski, and Alessandro Simonati. 2017. “Transcriptomic Profiling Discloses Molecular and Cellular Events Related to Neuronal Differentiation in SH-SY5Y Neuroblastoma Cells.” Cellular and Molecular Neurobiology 37 (4). Springer US: 665–82. https://doi.org/10.1007/s10571-016-0403-y.

Ritchie, Matthew E., Belinda Phipson, Di Wu, Yifang Hu, Charity W. Law, Wei Shi, and Gordon K. Smyth. 2015. “limma powers differential expression analyses for RNA-sequencing and microarray studies.” Nucleic Acids Research 43 (7): e47. https://doi.org/10.1093/nar/gkv007.

Tsyganov, Kirill, Andrew James Perry, Stuart Kenneth Archer, and David Powell. 2018. “RNAsik: A Pipeline for complete and reproducible RNA-seq analysis that runs anywhere with speed and ease.” Journal of Open Source Software 3 (28): 583. https://doi.org/10.21105/joss.00583.



