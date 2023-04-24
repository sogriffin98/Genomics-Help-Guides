# Genomics-Help-Guides
A help guide repository created by PhD students Sarah Griffin and Rachel Gray in the Dr Evelyn Jensen Lab at Newcastle University, UK. We made these guides to help fellow students and others get started on their servers for their genomics research projects.


## Installing Anaconda
1. Log onto the server as normal using your credentials
2. Navigate to your home directory. Make sure to change the * to match your c number
```
cd /mnt/nfs/home/c*********
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
2. programme you are installing or the name of your project, whichever is easiest for you. e.g., conda create -n fastqc
```
conda create -n <environment_name>
```
3.	Activate your newly created conda environment. e.g., conda activate fastqc
```
conda activate <environment_name>
```
4.	Find the line of code to install the required programme by typing into google ‘programme name conda’. The top result will give you a website called Anaconda.org which has install instructions for your required programme. e.g., https://anaconda.org/bioconda/fastqc 
```
conda install -c bioconda fastqc
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



