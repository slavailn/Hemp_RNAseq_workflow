# Section 1. Software installation and environment management.
Going forward we will use Conda environment management system to install the software used in the project and all of the associated software dependencies.

1. Install Conda:
Download the installer
```
 wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
 bash Miniconda3-latest-Linux-x86_64.s
```
Run the installer and follow the prompts.
Restart the session for the changes to take effect.
Create new conda environment names 'plant_rnaseq'.

```
conda create -n plant_rnaseq
```
Activate the newly created environment.

```
conda activate plant_rnaseq
```

2. Install SRA toolkit
```
 conda install -c bioconda sra-tools
```
