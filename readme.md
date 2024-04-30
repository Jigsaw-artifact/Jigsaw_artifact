# Overview

This repository is for the paper "Jigsaw: Accelerating SpMM with Vector Sparsity on Sparse Tensor Core".

## Artifact Identifaction

**(i)** an abstract describing the main contributions of the article and the role of the computational artifact(s) in these contributions.

In this paper, we introduce *Jigsaw*, a novel approach designed to maximize the utilization of SpTC for accelerating vector-sparse SpMM computations. Our method comprises three essential contributions, including *multi-granularity sparsity reorder*, *reorder-aware storage format*, and corresponding optimizations.

Through the performance evaluation on the sparse matrices with different sizes and sparsity from DLMC on an NVIDIA A100 GPU, we demonstrate that *Jigsaw* achieves practical speedup compared to cuBLAS and SOTA SpMM implementations. We believe this work will motivate future research on accelerating various sparsity patterns and dynamic sparsity for deep learning models.



**(ii)** the abstract may include a software architecture or data models and its description to help the readers understand the computational artifact(s) and

Our experiments are conducted on a platform equipped with two NVIDIA A100 GPUs(108 Ampere SMs, 40GB). The CPU of the platform is Intel(R) Xeon(R) Gold 6336Y CPU. We use NVCC11.8 and -O2 to compile our code. 

We construct benchmarks from the DLMC sparse dataset, replacing each nonzero element with a 1-D vector with different width.  



**(iii)** a clear description on to what extent the computational artifact(s) contribute(s) to the reproducibility of the experiments in the article.

We use Nsight Compute to record the execution time of Jigsaw and other baselines. It will execute the program at a fixed frequency, thus guaranteeing the result reproducibility.

At the same time, we will provide test scripts and plotting scripts to ensure that the test results are plotted as experiments result images in the paper.


## Reproducibility of Experiments 

**(i)** a complete description of the experiment workflow that the computational artifact(s) can execute

First, download the dataset and install Jigsaw and other baselines at the same time;
Second, execute the test script and generate the test results;
Third, execute the plotting script to plot the test results into the images in the paper.

**(ii)** an estimation of the execution time to execute the experiment workflow.

Figure 1 in the paper: about 5 min.

Figure 10 in the paper: about 72h.

Figure 11 & Table 2 in the paper: Since we record the test results, they can be generated within 5 min.

Figure 12 in the paper: about 6h.

**(iii)** a complete description of the expected results and an evaluation of them, and most importantly.



**(iv)** how the expected results from the experiment workflow relate to the results found in the article.

Expected results are consistent with the results in the paper.

## Detailed workflow

### install

1. install *Jigsaw*

```
make
```

2. uninstall *Jigsaw*

```
make clean
```


### evaluation


