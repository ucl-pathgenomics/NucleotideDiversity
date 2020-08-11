# Nucleotide Diversity Calculations

## Overview
This program estimates the nucleotide diversity of genomic sequences.

## Usage

#### Step 1 - BAM Files Conversion
Convert the BAM files using [Samtools](http://www.htslib.org).
```sh
samtools view -h -G69 to.convert.bam | samtools view -h -G133 > file.bam
```
For every sample, generate a strandcount.csv from the BAM file.
```sh
java -cp /your-path-to/HAROLD/lib/htsjdk-unspecified-SNAPSHOT.jar:
/Your-path-to/HAROLD/lib/picocli-4.1.2.jar:
/Your-path-to/HAROLD/lib/pal-1.5.1.jar:
/Your-path-to/HAROLD/lib/cache2k-all-1.0.2.Final.jar:
/Your-path-to/HAROLD/lib/commons-math3-3.6.1.jar:
/Your-path-to/HAROLD/jar/MakeReadCount.jar makereadcount.MakeReadCount file.bam
```

#### Step 2 - Diversity Estimations
```sh
java -jar MultiFileDiversity.jar -dataFileList sample.txt > diversity.txt
```


## Getting help
If you have any questions, please feel free to contact [Juanita Pang](mailto:juanita.pang.16@ucl.ac.uk) or [Richard Goldstein](mailto:r.goldstein@ucl.ac.uk).
