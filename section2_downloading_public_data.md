## How to download public sequencing data with sra toolkit:
1. Go to ncbi https://www.ncbi.nlm.nih.gov/ , select SRA database next to the *search* bar and look for enter relevant search words. In our case it is a title of a study: Whole genome-widWhole genome-wide expression profiles of hemp (Cannabis sativa L.) in response to drought stresse expression profiles of hemp (Cannabis sativa L.) in response to the drought stress. This search will produce the list of sampples related to the project, send the search result to file to produce a table of the accession numbers. Copy the accession numbers to a separate file like this:

SRX523346<br/>
SRX523345<br/>
SRX523344<br/>
SRX523343<br/>

I names this file *access_list.txt* and that the names used going forward.

2. Download the SRA files using *prefetch* command and a file with the list of accession numbers.
```
prefetch --option-file access_list.txt
```
Note, that SRA files will be downloaded to ncbi home directory. You can use this command:
```
 vdb-config -i
```
to invoke a configuration panel and check what that directory is, the same command allows to change it. 

3. For convenience we will create *fastq* directory and move SRA files there. Next we will convert SRA to fastq:
```
 fasterq-dump --split-files SRX523343.sra
```
Run this command for every file, --split-files option is used for paired-end data. The output of this consists of 2 fastq files - one for read 1 and another for read 2.


