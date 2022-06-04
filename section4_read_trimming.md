### Read trimming is recommended to remove adapter sequences and low quality bases that can cause misalignments and lead to errors down-stream in the workflow.

We will use *Trim Galore!* to trim the adapter and low quality bases. Another good option is *Trimmomatic*. Repeat the same command for all of the file pairs.
```
 trim_galore --paired --length 18 --illumina --fastqc -q 30 SRX523343.sra_1.fastq SRX523343.sra_2.fastq
```

Options explained:

* --paired - the reads were paired as 2 separate files for Read 1 and 2.
* --length N - reads with length < N after trimming will be removed. Both reads from the pair are removed if one of them falls below the length threshold.
* --illumina - Trim Galore! will autodetect Illumina adapter.
* --fastqc - generate FastQC reports for trimmed reads.
* --q N - trim the bases with qualities below N.

Full list of options can be found with *--help* options.

We can also run this command in parallel:
```
parallel -j 4 --xapply "trim_galore --paired --length 18 --illumina --fastqc -q 30" ::: *.sra_1.fastq ::: *.sra_2.fastq
```
--xapply option in this case ensures that the files are processed in pairs, othewise every combination of files will be used as an input. 

Check fastqc results for the trimmed files and observe the improvements.

