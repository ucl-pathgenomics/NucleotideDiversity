### Step 1 - For every sample, generate a strandcount.csv from the bam file using MakeReadCount.jar in the HAROLD repository ###
java -cp /your-path-to/HAROLD/lib/htsjdk-unspecified-SNAPSHOT.jar:/Your-path-to/HAROLD/lib/picocli-4.1.2.jar:/Your-path-to/HAROLD/lib/pal-1.5.1.jar:/Your-path-to/HAROLD/lib/cache2k-all-1.0.2.Final.jar:/Your-path-to/HAROLD/lib/commons-math3-3.6.1.jar:/Your-path-to/HAROLD/jar/MakeReadCount.jar makereadcount.MakeReadCount file.bam

### Step 2 - Calculate the diversity ###
### sample.txt is a list of strandcount filenames ###
java -jar MultiFileDiversity.jar -dataFileList sample.txt > diversity.txt

### Step 3 - Extract results from the output file ###
grep "^sample'*'"'*' diversity.txt 

### This command grep the row which starts with the word "sample". Replace the word "sample" with the first few characters of your csv file name. ###

### The diversity value is in the 5th column, i.e. 0.006949492435242967 for this run. ###
