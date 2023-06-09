# Genomics-Help-Guides
A help guide repository created by PhD students Sarah Griffin and Rachel Gray in the Dr Evelyn Jensen Lab at Newcastle University, UK (http://www.eljensen.ca/). We made these guides to help fellow students and others get started on the Rocket server at Newcastle University for their genomics research projects. The guides also includes lines of code for students not using the Rocket server. The guides can be used by anyone installing Anaconda, using conda to install programmes and doing genomic analysis for the first time. 

## Registering for the Rocket HPC (Newcastle University Students/Staff Only)
### Step 1 (Dr Evelyn Jensen will do this):
Add new member to a project: https://services.ncl.ac.uk/itservice/research/hpc/hpcmembership/
### Step 2: Register self 
1. This can only be done once you know the project name you are registered with: https://services.ncl.ac.uk/itservice/research/hpc/hpcregistration/
2. Project name should be ejwg or something similar (will be told to Evelyn when she registers you). Funding can be left blank.
3. Then log into here with your student ID and password: https://nuservice.ncl.ac.uk/HEAT/Modules/SelfService/#home
4. Then, click on “service catalogue” and search for “unix”. Then it is the unix timeshare service request (below) and I think in here you just type that you want an account to access Rocket HPC and that you are registered to the “ejwg” project.
### Step 3: Logging in on campus for first time
Follow the steps on this webpage: https://services.ncl.ac.uk/itservice/research/hpc/access-connecting/
### Step 4: Enabling off campus log in
Follow the steps on these webpages to enable off campus log in:
https://services.ncl.ac.uk/itservice/research/hpc/access-connectingfromoff-campus/
https://services.ncl.ac.uk/itservice/technical-services/unix-time-sharing/
https://services.ncl.ac.uk/itservice/technical-services/unix-time-sharing/ssh/
### Step 5: Access and Installing Programmes
Once you have got access to the Rocket HPC or another HPC follow the steps below to install Anaconda so that you can install programmes needed for your genomics project.

## Installing Anaconda
1. Log onto the server as normal using your credentials
2. Navigate to your home directory. Make sure to change the * to match your c number. This line of code is Rocket specific. 
```
cd /mnt/nfs/home/c*********
```
If your server is not the Rocket server the line of code to change to your home directory will be:
```
cd ~ or cd /path/to/your/home/directory/
```
3. Download conda using the below commands. Click enter and y/yes for all the prompts that appear on the terminal
```
wget "https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh"
bash Anaconda-latest-Linux-x86_64.sh
```
## Installing Programmes on the Server
### Getting Programmes Installed Using Conda
1.	Source your .bashrc using the command below. Your .bashrc was created during the installation of conda. It is a hidden folder, so don’t worry about not being able to see it in your home directory it is there. The c******** is your C number which needs to be replaced by your own numbers, it may be a different letter depending on when you started at the university. This number is what you use to log into the computer normally or what you can see on the server.
```
source /mnt/nfs/home/c********/.bashrc
```
or if your server is different to Rocket the line will have to be changed to the path to your home directory:
```
source /path/to/your/home/directory/.bashrc
```
2. Create a conda environment using the command below. The name of this can either be the name of the programme you are installing or the name of your project, whichever is easiest for you. e.g., conda create -n fastqc
```
conda create -n <environment_name>
```
3.	Activate your newly created conda environment. e.g., conda activate fastqc
```
conda activate <environment_name>
```
4.	Find the line of code to install the required programme by typing into google ‘programme name conda’. The top result will give you a website called Anaconda.org which has install instructions for your required programme. e.g., https://anaconda.org/bioconda/fastqc 
```
conda install -c bioconda <name_of_programme>
```
5.	If you want to keep the same conda environment for you project you can keep installing the programmes you would like into that environment using the method mentioned in step 5.
6.	After you have finished installing your required programme(s), deactivate the conda environment if you are not going to use that programme straight away.
```
conda deactivate 
```
7.	If you are using a new conda environment for each programme, you need to create a new conda environment for each programme using the method mentioned in steps 4, 5 and 7 or follow the steps below. 
```
conda create -n <environment_name>
conda activate <environment_name>
conda install -c bioconda ...
conda deactivate
```

### Using Conda to Run Programmes:
1.	To keep track of the conda environments you have, you can list them using the command below.
```
conda env list
```
2.	If you accidentally make an environment that you no longer need you can remove it using the below command.
```
conda env remove -n <environment_name>
```
3.	In order to use the programme you want, you need to activate the associated conda environment using the following command. e.g., conda activate fastqc
```
conda activate <environment_name>
```
4.	If you want to use a different programme, ensure to deactivate the current conda environment before you activate the next conda environment using the following commands.
```
conda deactivate
conda activate <environment_name>
```

### Installing Programmes Using Pip
1.	Ensure your .bashrc file is sourced using the command below. Your .bashrc was created during the installation of conda. It is a hidden folder, so don’t worry about not being able to see it in your home directory it is there. The c******** is your C number which needs to be replaced by your own numbers, it may be a different letter depending on when you started at the university. This number is what you use to log into the computer normally or what you can see on the server. You can tell it is sourced as you will see (base) at the start of your command line.
```
source /mnt/nfs/home/c********/.bashrc
```
or if your server is different to Rocket the line will have to be changed to the path to your home directory:
```
source /path/to/your/home/directory/.bashrc
```
2.	Create a conda environment using the command below. The name of this can either be the name of the programme you are installing or the name of your project, whichever is easiest for you.
```
conda create -n <environment_name>
```
3.	Activate your newly created conda environment.
```
conda activate <environment_name>
```
4.	Ensure you have pip installed in your conda environment using the line below.
```
conda install -c anaconda pip
```
5.	Find the line of code to install the required programme by typing into google ‘programme name github’. e.g., https://github.com/wdecoster/nanopack 
```
pip install nanopack
```
6.	If you want to keep the same conda environment for you project, you can keep installing the programmes you would like into that environment using the method mentioned in step 5 or install using conda (see conda instructions)
7.	After you have finished installing your required programme(s), deactivate the conda environment if you are not going to use that programme straight away.
```
conda deactivate 
```
8.	If you are using a new conda environment for each programme, you need to create a new conda environment for each programme using the method mentioned in steps 2-7 or follow the steps below. 
```
conda create -n <environment_name>
conda activate <environment_name>
conda install -c bioconda ... or pip install ...
conda deactivate
```
9.	To keep track of the conda environments you have, you can list them using the command below.
```
conda env list
```
10.	If you no longer need an environment, remove it using the below command.
```
conda env remove -n <environment_name>
```
11.	In order to use the programme(s) you want, you need to activate the associated conda environment using the following command, e.g., conda activate fastqc
```
conda activate <environment_name>
```
12.	If you want to use a different programme, ensure to deactivate the current conda environment before you activate the next conda environment using the following commands.
```
conda deactivate
conda activate <environment_name>
```
## Using R on Rocket HPC
On most high performance computer clusters, R can be started by simply typing R into the terminal. 
For rocket the following commands should be ran: 
```
Module load R 
R
```
This will open up the R environment. Bear in mind this is not Rstudio so the enviornment and figure panels cannot be viewed. 
Figure results can be saved as a pdf as follows: 
```
pdf("pdfExample.pdf")
plot(results)
dev.off()
```
To save results that are in a dataframe as a csv: 
```
write.csv(DataFrame Name, "File Name.csv", row.names=FALSE)
```
To save R objects:
```
saveRDS(R_ojbect, file = "R_oject.RDS") 
```
This can then be read back into R later with:
```
R_ojbect <- readRDS("R_oject.RDS")
```

## Quality Control of Raw Reads
Checking the quality of your raw reads is an important step before moving forward to the trimming stage. This can be done using the following programmes:
* NanoStat (https://github.com/wdecoster/nanostat)
* FastQC (https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)
* NanoQC for Oxford Nanopore Technologies only (https://github.com/wdecoster/nanoQC)

Make sure you have installed the programmes before you start. An example of the code needed for these programmes is below:
```
conda activate fastqc
fastqc <read_1.fq.gz>
conda deactivate
```
```
conda activate NanoStat
NanoStat --fastq read_1.fq.gz -o /path/to/file/ -n read_1_Raw_StatReport
conda deactivate
```
```
conda activate nanoQC
nanoQC ONT_read.fq.gz -o ONT_read_Raw_NanoQC -1 500
conda deactivate
```

## Trimming of Illumina Reads
### Trim Galore
Trim Galore is a wrapper around Cutadapt and FastQC to consistently apply adapter and quality trimming to FastQ files, with extra functionality for RRBS data (https://github.com/FelixKrueger/TrimGalore).
The user guide is here: https://github.com/FelixKrueger/TrimGalore/blob/master/Docs/Trim_Galore_User_Guide.md

Example of code:
```
conda activate trimgalore
trim_galore --paired read_1.fq.gz read_2.fq.gz
conda deactivate
```

## Trimming of Oxford Nanopore Technologies Reads
### NanoFilt
NanoFilt is a programme for trimming and filtering long read data (https://github.com/wdecoster/nanofilt). NanoFilt does not work for .gz files, so you first have to unzip the file before using the programme. 
Example of code:
```
gunzip -c ONT_read.fq.gz | NanoFilt -q 10 | gzip > ONT_read_trimmed.fq.gz
```
### Prowler
Prowler is a trimming and filtering programme used for long read data (https://github.com/ProwlerForNanopore/ProwlerTrimmer). Prowler does not work for .gz files, so you first have to unzip the file before using the programme. Before using the programme you need to move to your home directory and then change into the Prowler Trimmer folder for the programme to work. 
An example of the code needed to do the above steps is below:
```
gunzip -c ONT_read.fq.gz
cd ~
cd ProwlerTrimmer
python3 TrimmerLarge.py -f "ONT_read.fq" -i "/path/to/data/folder/" -o "/path/to/data/folder/" -w 100 -l 1000 -c LT -g U0 -m S -q 7 -d 0 -r .fastq
cd /path/to/data/folder/
gzip ONT_read_trimmed.fq
```
## Quality Control of Trimmed Reads
Checking the quality of your trimmed reads is an important step before moving forward to the genome assembly stage to check that your reads are trimmed enough. This can be done using the same programmes as above:
* NanoStat (https://github.com/wdecoster/nanostat)
* FastQC (https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)
* NanoQC for Oxford Nanopore Technologies only (https://github.com/wdecoster/nanoQC)

Make sure you have installed the programmes before you start. An example of the code needed for these programmes is below:
```
conda activate fastqc
fastqc <read_1_trimmed.fq.gz>
conda deactivate
```
```
conda activate NanoStat
NanoStat --fastq read_1_trimmed.fq.gz -o /path/to/file/ -n read_1_trimmed_StatReport
conda deactivate
```
```
conda activate nanoQC
nanoQC ONT_read_trimmed.fq.gz -o ONT_read_trimmed_NanoQC -1 500
conda deactivate
```
## Genome Assembly

## Genome Assembly Analysis
### Busco
#### Plotting Busco Scores
It is common to plot BUSCO scores as a bar chart from a single run, or from different runs side-by-side to visualize like-for-like comparisons, e.g., of different species/strains or assembly versions. To encourage the use of a standard and distinctive colour scheme in publications, BUSCO includes a dedicated R (R Core Team, 2020) script to produce a figure and its source code that can be further edited, allowing one to customize the resulting bar chart (labels, fonts, axes, etc.). To run the script, Python is required. To produce the image, R and the ggplot2 library need to be available on the system. To plot the scores of one or multiple runs, it is sufficient to provide in a single folder the short_summary.txt files of each BUSCO run.
Collect the short_summary*.txt files in one folder, e.g.: 
```
mkdir BUSCO_summaries/
cp OUT1/short_summary.*.lineage_odb10.OUT1.txt ./BUSCO_summaries/
cp OUT2/short_summary.*.lineage_odb10.OUT2.txt ./BUSCO_summaries/
```
Then, simply run the generate_plot.py script available in the BUSCO repository (https://gitlab.com/ezlab/busco/scripts), providing the path to the directory containing the summary files: 
```
python3 generate_plot.py -wd BUSCO_summaries
```
A *.png image file and the corresponding R source code file, which can be further edited to make cosmetic adjustments to the plot, will be produced in the same folder containing the BUSCO summaries. By default, the run name is used as the label for each plotted result, and this is automatically extracted from the short summary file name: so, for short_summary.generic.lineage_odb10.OUT1.txt, the label would be “OUT1”. You can modify this in the file name as long as you keep the naming convention, e.g.: short_summary.generic.lineage_odb10.[edit_name_here].txt, or you can simply edit the R source code file to change any plotting parameters and produce a personalized bar chart by running the code manually in your R environment. However, we suggest keeping the same color scheme. By adding the --no_r flag to the command, the script will simply produce the R script required to reproduce the plot, which can then run on any system with R and ggplot2 installed. Figure 1 shows an example of the resulting default plot.



