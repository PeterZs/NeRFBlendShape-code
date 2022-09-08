# Reconstructing Personalized Semantic Facial NeRF Models From Monocular Video
PyTorch implementation for the paper "Reconstructing Personalized Semantic Facial NeRF Models From Monocular Video". This repository contains the inference code, data and released pretrained model.
![teaser](fig/teaser.png)
A semantic model for human head defined with neural radiance field is presented. In this model, multi-level voxel field is adopted as basis with corresponding expression coefficients, which enables strong representation ability on the aspect of rendering and fast training.

## Pipeline
We track the RGB sequence and get expression coefficients, poses and intrinsics. Then we use the tracked expression coefficients to combine multiple multi-level hash tables to get a hash table corresponding to a specific expression. Then the sampled point is queried in hash table to get voxel features, we use an MLP to interpret the voxel features as RGB and density. We fix the expression coefficients and optimize the hash tables and MLP to get our head model.

![pipeline](fig/pipeline.png)

## Monocular RGB Video Data and Pretrained models

[Data (Google Drive)](https://drive.google.com/drive/folders/1zNMLzp5XTIWlNouF4BpxnOFyI_Ey3CJ1?usp=sharing)
Some videos are from the dataset collected by [Neural Voice Puppetry](https://justusthies.github.io/posts/neural-voice-puppetry/). Since the expressions in these videos are mainly normal talking styles which are not very challenging, we didn't do evaluation on the whole dataset. We capture some monocular videos with exaggerated expressions and large head rotations. In each captured video, the subject is asked to perform arbitrary expressions. The last 500 frames serve as the testing dataset.

## Inference code
coming soon.
