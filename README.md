# MitoHPC2_LongReads_UCL

This is set up on Myriad.  I created a new conda environment:

```
conda create -n MitoHPC_LR -y python=3.9 \
bwa=0.7.17 \
minimap2=2.28 \
htslib=1.21 \
samtools=1.21 \
bcftools=1.21 \
samblaster=0.1.26 \
bedtools=2.31.1 \
fastp
plink2

```