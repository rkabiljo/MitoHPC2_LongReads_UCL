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

To run:
```
cd ~/MitoHPC2
conda activate MitoHPC_LR
module load java
```
Activating this conda environment and loading java can be done one the node and the main script can also run one the node for a few samples only.
If submitting to HPC, these two lines need to be in the submission script

Something like this to run it - check more in MitoHPC github:
Change infile and out folder.  Infile must be in this format, and must have tabs and not spaces:
```
IC_RP_0008.recal	/home/skgtrk2/Scratch/tempBam/IC_RP_0008.recal.bam	/lustre/home/skgtrk2/MitoHPC2/outIC_RP_0008/IC_RP_0008.recal/IC_RP_0008.recal
NAME_WITHOUT_BAM TAB LOCATION_OF_BAM TAB OUTPUT_DIR_FROM_INIT_FILE_AND_TWICE_SAMPLE_NAME
```
easiest is to prepare this in.txt first, with one line for each sample in the format above
```
echo $HP_SDIR
cp $HP_SDIR/init.hifi.sh .
nano init.hifi.sh 
. ./init.hifi.sh
$HP_SDIR/run.hifi.sh > run.KB.sh
bash ./run.KB.sh 
```

or
```
# edit:run.hifi.all.ONT.sh
# edit inONT.txt
#mkdir the output directory you defined
bash ./run.hifi.all.ONT.sh 
(base) [skgtrk2@login12 MitoHPC2]$ conda activate MitoHPC_LR
(MitoHPC_LR) [skgtrk2@login12 MitoHPC2]$ bash ./run.hifi.all.ONT.sh 

```

For short reads use the same, just init.sh instead of init.hifi.sh
edit init.sh and prepare in.txt and create output directory
```
$HP_SDIR/run.sh > run.all.sh
bash ./run.all.sh
```


