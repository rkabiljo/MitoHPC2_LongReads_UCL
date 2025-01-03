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
```


Something like this to run it:
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


