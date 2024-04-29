# Overview

This repository is for the paper "Jigsaw: Accelerating SpMM with Vector Sparsity on Sparse Tensor Core".

## Artifact Identifaction

**(i)** an abstract describing the main contributions of the article and the role of the computational artifact(s) in these contributions.

In this paper, we introduce *Jigsaw*, a novel approach designed to maximize the utilization of SpTC for accelerating vector-sparse SpMM computations. Our method comprises three essential contributions, including *multi-granularity sparsity reorder*, *reorder-aware storage format*, and corresponding optimizations.

Through the performance evaluation on the sparse matrices with different sizes and sparsity from DLMC on an NVIDIA A100 GPU, we demonstrate that *Jigsaw* achieves practical speedup compared to cuBLAS and SOTA SpMM implementations. We believe this work will motivate future research on accelerating various sparsity patterns and dynamic sparsity for deep learning models.

**(ii)** software and hardward architecture, and dataset

Our experiments are conducted on a platform equipped with two NVIDIA A100 GPUs(108 Ampere SMs, 40GB). The CPU of the platform is Intel(R) Xeon(R) Gold 6336Y CPU. We use NVCC118 and -O2 to compile our code.

We construct benchmarks from the DLMC sparse dataset, replacing each nonzero element with a 1-D vector with different width.  


## Reproducibility of Experiments 

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


