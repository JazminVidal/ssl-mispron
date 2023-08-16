# Mispronunciation detection using self-supervised speech representations

:card_file_box: This repository contains the code to replicate the experiments in the paper ["Mispronunciation detection using self-supervised speech representations"](https://arxiv.org/abs/2307.16324) presented at the [SLaTE Workshop](https://sites.google.com/view/slate2023) held in Dublin 2023.

:bulb: We study the use of different self-supervised models (SSL) for the task of mispronunciation detection for second language learners. We compare two downstream approaches: 

1. **PR**: Training the model for phone recognition using native data from TIMIT database.
2. **MD**: Training the model directly for the target task using non-native Enligsh data from EpaDB and L2Arctic databases. 

We also compare the performance of each approach using representations extracted from a traditional HMM-DNN system.  The SSL models that we compare are: HuBERT, LightHuBERT small, WavLM large and WavLM+.

:gear: We implement the SSL models using the s3prl toolkit. The code consists of two directories containing two different pronunciation assessment downstreams, the PR and the MD approach in the paper. Directory ```pr``` contains the PR approach and directory ```md``` contains the MD approach. Both directories contain: 

- Data folders: there is one data folder for each database used (i.e data_epa contains the data for EpaDB database). We use TIMIT, EpaDB and L2Arctic in the PR approach and only the last two in the MD approach. Data folders contain alignement files for phones and labels, a lengths file used for bucketing, the splits of the data used for the experiments, the list of phones and the weights for each phone in this experiments.
- Config file: the config file contains the parameters of the experiment. 
- Scripts for running the experiments as required by s3prl. 

## Prerequisites
1. The EpaDB dataset downloaded. You can ask for the most updated version at jvidal@dc.uba.ar.
2. The L2Arctic dataset downloaded. You can download the most updated version from this [link](https://psi.engr.tamu.edu/l2-arctic-corpus/). 
3. The [s3prl](https://github.com/s3prl/s3prl) toolkit downloaded or cloned.

An exact frozen version of the databases we used in this experiments can be downloaded from [this link](). 

## How to install 
1. Clone s3prl
```
git clone https://github.com/s3prl/s3prl.git
```
2. Clone this repository: 
```
 git clone https://github.com/JazminVidal/ssl-mispron.git
```
and move or link the pr and the md directories to the downstream directory inside s3prl.  
3. Download the databases. Copy or link them to the corresponding data folder inside the downstream folder. 

## How to run PR
To obtain results for the PR systems. From the root of the s3prl directory run the following command: 
```
python3 run_downstream.py -m train -n TEST -u upstream -d pr
```
 where upstream can be any of the upstreams implemented in s3prl, for example hubert. 

## How to run MD
To obtain results for the MD systems. From the root of the s3prl directory run the following command: 
```
python3 run_downstream.py -m train -n TEST -u upstream -d md
```
 where upstream can be any of the upstreams implemented in s3prl, for example hubert. 












