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

## Main features of pipeline

   1. Takes configuration file of parameters as input
   2. Automatic project sample retrieving from SRA website
   3. Filters variants by quality (QUAL>=30) and depth (DP>=25)
   4. Calculates median, average, and max coverage of certain genes
   5. Detects copy number variants (CNVs) and plots summary results

## Requirements

### Programming Languages:

    Python3, Version 3.6.2
    R language, Version 3.3.2

### Pre-processing and alignment:

    Read quality trimming: Trimmomatic, Version 0.36
    Reference-based read aligner: Bowtie2, Version 2.3.2
    Process SAM/BAM alignment files: Samtools, Version 1.6

### Call variants and post-processing:

    Manipulate genomic data files: Picard tools, Version 2.11.0
    Detect variants with HaplotypeCaller: GATK, Version 3.8.0

### Analyze and evaluate somatic variants:

    Detect copy-number changes: Control-FREEC, Version 11.0


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
