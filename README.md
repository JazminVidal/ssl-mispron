# Mispronunciation detection using self-supervised speech representations

:card_file_box: This repository contains the code to replicate the experiments in the paper ["Mispronunciation detection using self-supervised speech representations"]() presented at the [SLaTE Workshop] () held in Dublin 2023.

:bulb: We study the use of different self-supervised models (SSL) for the task of mispronunciation detection for second language learners. We compare two downstream approaches: 

1. **PR**: Training the model for phone recognition using native data from TIMIT.
2. **MD**: Training the model directly for the target task using non-native Enligsh data from [EpaDB]() and [L2Arctic](). 

We also compare the performance of each approach using representations extracted from a traditional HMM-DNN system. 
The SSL models that we compare are: HuBERT, LightHuBERT small, WavLM large and WavLM+.

:gear: We implement the SSL models using the s3prl toolkit. The code consists of two directories containing two different pronunciation scoring downstreams, the PR and the MD approach. Directory XXX contains the PR approach and the directory XXX contains the MD approach. Both directories contain: 

- Data folders: there is one data folder for each database used. Data folders contain the splits of the data, the 
the phone lists and the corresponding time alignments and phones. The data preprocessing stage is explained in section XXX of the paper. 
- Configuration files: 
- Scripts: 

## Prerequisites
1. The EpaDB dataset downloaded. You can ask it at jvidal@dc.uba.ar
2. The L2Arctic dataset downloaded. You can download it from this [link](https://psi.engr.tamu.edu/l2-arctic-corpus/).
3. The [s3prl](https://github.com/s3prl/s3prl) toolkit downloaded or cloned.

## How to install
1. Link databases to... The frozen version of the data uses for this paper is [here]().
2. Clone s3prl. We used s3prl version XXX:
´´´
´´´
2. Clone this repository: 
 ´´´
 ´´´
 Once done, move the XXX and the XXX directories to the downstream directory in s3prl.  

## How to run PR

## How to run MD














