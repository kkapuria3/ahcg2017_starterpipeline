# AHCG SNP Pipeline 2017 
Variant calling pipeline for genomic data analysis 


## Personal Details
Name: [Karan Kapuria](www.prism.gatech.edu/~kkapuria3)
Info: 2nd Year MS Bioinformatics student

## Mission Statement
To create adaptive computational pipeline using existing tools which can aid in early detection of cancer before symptoms emerge.   

## What is Liquid Biopsy ?
A test done on a sample of blood to look for cancer cells from a tumor that are circulating in the blood or for pieces of DNA from tumor cells that are in the blood. A liquid biopsy may be used to help find cancer at an early stage. It may also be used to help plan treatment or to find out how well treatment is working or if cancer has come back. 

## Alterations obeserved in Liquid Biopsy 
   1. Epigenetic modifications: Bisulfite sequencing to detect methylation
   2. Single nucleotide variants (SNV's): Variation in nucleotide that can be present in somatic cells
   3. Copy number alterations (CNA's): Changes in copy number of genes present in somatic tissue


## Requirements

1. [Python3 - version 3.4.1](https://www.python.org/download/releases/3.4.1/)
2. [Trimmomatic - version 0.36](http://www.usadellab.org/cms/uploads/supplementary/Trimmomatic/Trimmomatic-0.36.zip)
3. [Bowtie2 - version 2.2.9](https://sourceforge.net/projects/bowtie-bio/files/bowtie2/2.2.9/)
4. [Picard tools - version 2.6.0](https://github.com/broadinstitute/picard/releases/download/2.6.0/picard.jar)
5. [GATK - version 3.4](https://software.broadinstitute.org/gatk/download/)

## Reference genome

Reference genomes can be downloaded from [Illumina iGenomes](http://support.illumina.com/sequencing/sequencing_software/igenome.html)

## Test data

Use the following protocol to download and prepare test dataset from NIST sample NA12878

```{sh}
wget ftp://ftp-trace.ncbi.nih.gov/giab/ftp/data/NA12878/Garvan_NA12878_HG001_HiSeq_Exome/NIST7035_TAAGGCGA_L001_R1_001.fastq.gz
wget ftp://ftp-trace.ncbi.nih.gov/giab/ftp/data/NA12878/Garvan_NA12878_HG001_HiSeq_Exome/NIST7035_TAAGGCGA_L001_R2_001.fastq.gz
gunzip NIST7035_TAAGGCGA_L001_R1_001.fastq.gz
gunzip NIST7035_TAAGGCGA_L001_R2_001.fastq.gz
head -100000 NIST7035_TAAGGCGA_L001_R1_001.fastq > test_r1.fastq
head -100000 NIST7035_TAAGGCGA_L001_R2_001.fastq > test_r2.fastq
```

## Help

To access help use the following command:

```{sh}
python3 ahcg_pipeline.py -h
```
