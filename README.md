# QIIME2 - 2024 protocol


## Set up working area

### Anaconda environment

Create a conda environment to install QIIME2. Only make conda environments in your personal scratch directory. To do this on the TAMU HPRC, follow the below instructions.

```
cd $SCRATCH                                     # Make scratch your current directory
module load Anaconda3/2024.02-1                 # Load Anaconda module (you can use the latest version)
conda config --set auto_activate_base False     # run once to disable auto Anaconda loading
```

You only need to do the above once.

### Install QIIME2

Execute the below set of commands. This may take some time. *wget* downloads the latest version of QIIME2 that is available. This is an *environment* file, which ends in _.yml_. Then use anaconda to create your environment. The name of this environment will be ```qiime2-amplicon-2024.5```.

```
wget https://data.qiime2.org/distro/amplicon/qiime2-amplicon-2024.5-py38-linux-conda.yml
conda env create -n qiime2-amplicon-2024.5 --file qiime2-amplicon-2024.5-py38-linux-conda.yml
```
Once the environment is "solved", and completed, you can remove the .yml file.
```
rm qiime2-amplicon-2024.5-py38-linux-conda.yml
```

**Alternatively, see if your HPC has it installed with ```module load QIIME2```.**

On the TAMU HPRC, use ```module load QIIME2/2023.2```

Once you have QIIME2 installed and activated, test it by calling the help menu.

```
qiime --help
```

### Import raw sequences

Always review the importing protocol for qiime2, as the format sometimes changes for the manifest file.

This site: https://docs.qiime2.org/2024.5/tutorials/importing/

The most common fastq file type you will get back is an already de-multiplexed set of files. You should have an R1 and R2 for each sample you submitted for sequencing. 

To learn QIIME2, see ```/scratch/group/hu-lab/code-club-test/amplicon-qiime2-intro```.

#### Make a **manifest file**

This can be done manually if needed, but I'd recommend becoming familiar with how to create this at the command line. 

Run this R script and modify for your specific sample list.
```/scratch/group/hu-lab/code-club-test/amplicon-qiime2-intro/create-manifest.R```
