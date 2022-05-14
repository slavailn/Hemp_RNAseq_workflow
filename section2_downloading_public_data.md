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

