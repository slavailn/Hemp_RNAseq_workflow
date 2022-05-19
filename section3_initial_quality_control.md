## Initial quality control of sequencing data
Initial quality control is normally done with FastQC: https://www.bioinformatics.babraham.ac.uk/projects/fastqc/
FastQC manual: https://www.bioinformatics.babraham.ac.uk/projects/fastqc/Help/
FastQC page also contains example reports with different types of runs, good or bad: https://www.bioinformatics.babraham.ac.uk/projects/fastqc/

Some video guides:
https://www.youtube.com/watch?v=lUk5Ju3vCDM&t=54s
https://www.youtube.com/watch?v=bz93ReOv87Y

We will run FastQC from the command line in the *fastq/* directory that contains our *.fastq* files.
```
 fastqc *.fastq
```
I used \* to expand all of the files with .fastq extension. In this case FastQC will run them one-by-one in sequence.
We can also run them in parallel:
```
 parallel -j 4 "fastqc" ::: *.fastq
```

