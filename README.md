# Speech to Phoneme: Deep Learning Automatic Phone Recognition

Authors: Kip McCharen, Pavan Kumar Bondalapati, Siddarth Surapaneni

SYS 6016: Deep Learning

University of Virginia

School of Data Science

May 13, 2021

## Overview

Adapted from [SpeechBrain](https://github.com/speechbrain/speechbrain/tree/develop/recipes/TIMIT/ASR/seq2seq).

Link to our [paper](./docs/paper.pdf).

## TIMIT ASR with seq2seq Models

This folder contains the scripts to train a seq2seq RNN-based system using TIMIT, a speech dataset that is available from University of Pennsylvania's [Lingusitic Data Consortium](https://catalog.ldc.upenn.edu/LDC93S1).

## Usage

Run this command to train the model:

`python train.py train/train.yaml`

## Results

| Release | hyperparams file | Val. PER | Test PER | Model link | GPUs |
|:-------------:|:---------------------------:| -----:| -----:| --------:| :-----------:|
| 21-04-08 | train_with_wav2vec2.yaml |  7.11 | 8.04 | https://drive.google.com/drive/folders/1-IbO7hldwrRh4rwz9xAYzKeeMe57YIiq?usp=sharing | 1xV100 32GB |

## Bash Commands to Run in Google Colab

1. `!pip install speechbrain`

2. `!pip install transformers`

3. `!git clone https://github.com/kipmccharen/sys6016_DL_project`

4. `%cd ..`

5. `!gdown --id '1EIfBmwiT0RF3-U81-Qu5K4J27N31BdB5' ## --output /content/speechbrain_s2s_wav2vec_ckpt.zip`

6. `!unzip speechbrain_s2s_wav2vec_ckpt.zip`

7. `!rm speechbrain_s2s_wav2vec_ckpt.zip`

8. `%cd /content/data/trainwav2vec/save/`

9. `!gdown --id '1oZunuiwhMLfwtMeKAYJwr4DMjvE1LUIN'  --output label_encoder.txt`

10. `%cd /content/`

11. `!python sys6016_DL_project/train_with_wav2vec2.py sys6016_DL_project/hparams/train_with_wav2vec2.yaml --data_folder /content/data/ --output_folder /content/data/trainwav2vec/ --new_json /content/sys6016_DL_project/data/new_train.json`
