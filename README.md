# Learning to Segment from Noisy Annotations: A Spatial Correction Approach

This is the official repository for the ICLR 2023 paper **[Learning to Segment from Noisy Annotations: A Spatial Correction Approach](https://openreview.net/forum?id=Qc_OopMEBnC&referrer=%5BAuthor%20Console%5D(%2Fgroup%3Fid%3DICLR.cc%2F2023%2FConference%2FAuthors%23your-submissions))**.

This paper proposed a Markov model for simulating segmentation label noise, and a Spatial Correction method to combat such noise.

## Requirements

Our code has been tested on Ubuntu 20.04.5 LTS with CUDA 11.4 (Driver Version 470.161.03), Python 3.9.7, and PyTorch v1.10.2.

## Noisy Label Generation

The Markov noise generation follows Definition 1 in our paper. There are four parameters controlling this process, $T$ the number of steps, $\theta_1$ the noise preference, $\theta_2$ noise variance, $\theta_3$ random flipping noise rate. To generate the proposed Markov noise for you own dataset, run
```
python noise_generator.py --gts_root your/gt/root/ --save_root your/save/root/
```
To generate random dilation and erosion noise, add `--noisetype DE` to the above command.\
Other arguments can be set accordingly by detailed descriptions inside the function.


## Citing

If you find our work helpful, please consider citing as

```
@inproceedings{yao2023spatialcorrection,
   title={Learning to Segment from Noisy Annotations: A Spatial Correction Approach},
   author={Yao, Jiachen and Zhang, Yikai and Zheng, Songzhu and Goswami, Mayank and Prasanna, Prateek and Chen, Chao},
   booktitle={International Conference on Learning Representations},
   year={2023}
}
```



