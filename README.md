BTECH 610 Final Project

Differential gene expression and gene coexpression in Arabidopsis thaliana exposed to three levels of humidity.

## Background information on data used for the project

The gene expression profiling (RNA-seq) dataset titled "Genome-wide expression analysis of Arabidopsis Col-0 plants under different air humidity"  (series number GSE236463), was made public on October 17, 2023. This research, conducted by Yao L, Jiang Z, and Xin X from the Chinese Academy of Sciences in Shanghai, examines the global expression profile of Arabidopsis thaliana Col-0 wild type plant leaves in response to varying humidity levels. The particular strain of A. thaliana chosen for this study is a model organism for research ; “Col-0” indicates this is a strain of the organism found in Colombia.

The overall design of the experiment involved treating four-week-old Col-0 plants with three different humidity levels - low, moderate, and high - for one hour. It includes twelve biological replicates, with four replicates under each of three treatment levels. The biological replicates were derived from different individual plants or groups of plants, which is a crucial aspect of experimental design in biological research, as it helps to ensure that the results are not specific to a single plant but are representative of a general response in the species to the given treatment.

Following the treatment, leaves were collected for RNA extraction. The extraction process used Trizol Reagent for isolating total RNA, and DNaseI was employed to remove any genomic DNA contamination. The RNA was further purified using the RNeasy MinElute Cleanup kit. Library construction and RNA sequencing were carried out by Majorbio company. 

Twelve runs (one for each plant) of paired-end sequencing were performed using the Illumina NovaSeq 6000 platform. Paired-end sequencing achieves higher accuracy and coverage by sequencing both forward and reverse strands. The data processing for this study involved basecalling using Illumina Casava1.8 software, followed by trimming and quality control of the raw paired-end reads using fastp. Fastp performs tasks like trimming of adapter sequences, filtering out low-quality reads, and correcting for sequencing errors (other common sequence processing tools include Trimmomatic or Cutadapt). 

The clean reads were then aligned to the Arabidopsis reference genome (TAIR 10) using HISAT2 software. HISAT2 is used for aligning sequencing reads to a reference genome. It's a crucial step in identifying where in the genome each read originated from. HISAT2 is known for its speed and efficiency, especially in handling large genomes and datasets. It uses an advanced graph-based algorithm to handle genetic variations and splicing, which is particularly important in eukaryotic organisms like Arabidopsis thaliana. While Bowtie2 and BWA are other commonly used alignment tools, they are not splice-aware, which is required for aligning RNA-seq data. These aligners can recognize and properly align reads that span exon-exon junctions, which are typical in mRNA sequences. HISAT2, STAR, and TopHat2 are examples of splice-aware aligners that are commonly used for RNA-Seq data analysis. They are specifically designed to handle the complexities of RNA splicing, allowing for accurate mapping of reads that span across spliced junctions.

Gene expression levels were quantified using the TPM (Transcripts Per Million reads) method.  TPM is a method for normalizing gene expression levels in RNA-Seq data, accounting for both the depth of sequencing and the length of the gene. This makes comparisons of gene expression levels more meaningful across samples, as it mitigates biases introduced by these two factors.  Other normalization methods include FPKM (Fragments Per Kilobase of transcript per Million mapped reads) and RPKM (Reads Per Kilobase of transcript per Million mapped reads), though TPM is often preferred for its ability to facilitate more direct comparisons across samples.  

RSEM software was used for quantifying gene abundances. RSEM (RNA-Seq by Expectation-Maximization) is used for quantifying gene and isoform abundances from RNA-Seq data using a statistical model to assign reads to specific genes or isoforms.  Tools like Kallisto and Salmon offer similar functionalities, often with faster processing times due to different underlying algorithms (like pseudo-alignment).


## Description of repository contents


/all_gene_lengths.csv	

/atgenes.txt

/gene_expression.Rmd

/gene_lengths_dp.Rmd

/fc_minimal.csv

/repeated_normalization_check.Rmd

/unmatched_genes.txt

/data/GSE236463_all_rawcount.xlsx	



