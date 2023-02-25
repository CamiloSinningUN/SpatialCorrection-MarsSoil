# Learning to Segment from Noisy Annotations: A Spatial Correction Approach

This is the official repository for the ICLR 2023 paper **[Learning to Segment from Noisy Annotations: A Spatial Correction Approach](https://openreview.net/forum?id=Qc_OopMEBnC&referrer=%5BAuthor%20Console%5D(%2Fgroup%3Fid%3DICLR.cc%2F2023%2FConference%2FAuthors%23your-submissions))**.

This paper proposed a Markov model for simulating segmentation label noise, and a Spatial Correction method to combat such noise. The outline of this repository is given as follows.

* [**Requirements**](#requirements)
* [**Noisy Label Generation**](#noisy-label-generation)
* [**Test with Trained Models**](#test-with-trained-models)
* [**Train on Your Own**](#train-on-your-own)
* [**Citing**](#citing)

## Requirements

Our code has been tested on Ubuntu 20.04.5 LTS with CUDA 11.4 (Driver Version 470.161.03), Python 3.9.7, and PyTorch v1.10.2. (Add .requirements)

## Noisy Label Generation

|![fig1](figs/noisetype.png)|
|:---|
|Comparison of different types of noise. Blue lines are true segmentation boundaries, and red lines are noisy boundaries (after removing random flipping noise). $S_E$ and $S_S$ are generated by the proposed Markov mode.|

The Markov noise generation follows Definition 1 in our paper. There are four parameters controlling this process, $T$ the number of steps, $\theta_1$ the noise preference, $\theta_2$ noise variance, $\theta_3$ random flipping noise rate. To generate the proposed Markov noise for you own dataset, run
```
python noise_generator.py --gts_root your/gt/root/ --save_root your/save/root/
```
To generate random dilation and erosion noise, add `--noisetype DE` to the above command.\
Other arguments can be set accordingly with detailed descriptions inside the function.

(Table of settings)

## Test with Trained models

We provide the *JSRT* dataset with noisy setting `A` we used in our experiments in `./Datasets` and a trained model with the proposed Spatial Correction method in `./trained`. If you use *JSRT* dataset in your work, please cite their original publications. More trained models will be uploaded later.

For testing on the provided model, simply run `python test.py`. To test other models, change the paths in `test.py` accordingly and run the same command.

## Train on Your Own

**Train with datasets in the paper.**

**Train with your own dataset.**

## Citing

If you find this code helpful, please consider citing as

```
@inproceedings{yao2023spatialcorrection,
   title={Learning to Segment from Noisy Annotations: A Spatial Correction Approach},
   author={Yao, Jiachen and Zhang, Yikai and Zheng, Songzhu and Goswami, Mayank and Prasanna, Prateek and Chen, Chao},
   booktitle={International Conference on Learning Representations},
   year={2023}
}
```



